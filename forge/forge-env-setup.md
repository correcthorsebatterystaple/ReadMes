# Forge 1.12.2
## Eclipse
It is assumed that Eclipse is already installed

### 1. Install the JDK
The jdk1.8.0_181 seems to work fine with this dev env. Note that you might have to set System Variable `JAVA_HOME` to the `.../jdk1.8.0_181/bin` after installation. This is expected in the gradle task later.

### 2. Install Forge 1.12.2
First install the corresponding version of forge which in this case is 1.12.2.

This can be found on the forge website. The file you are looking for is the [Mdk (mod development kit)](https://files.minecraftforge.net/maven/net/minecraftforge/forge/1.12.2-14.23.5.2838/forge-1.12.2-14.23.5.2838-mdk.zip "Forge 1.12.2 Mdk") it will be a simple zip file.

Extract this zip file to a root folder, `root`, of your choosing within your folder that you have chosen to be your Eclipse workspace.

### 3. Setup workspace
Open powershell with the `root` directory. Run the following commands and expect a `BUILD SUCCESSFUL` text to suffix the commands.
``` 
PS > .\gradlew setupDecompWorkspace
```
Note: This might result in `BUILD FAILED` if this is due to the gradle version being incompatible, feel free to change the distribution url in `root/gradle/wrapper/gradle-wrapper.properties` to `4.8.1`
```
PS > .\gradlew eclipse
```

Now, Load Eclipse and select `import project...` and select the `root`. At this point you will have a working(but useless) mod.

### 4. Running the mod
In Eclipse click on the dropdown beside the run symbol then 
```
Run Configurations > Java Applications > root_client
```
Select `root_client` and select `Run`.

If this throws an error of the sort `java.lang.ClassCastException` This may be due to the jre that is being used, ensure that the jre is from the jdk downloaded above. You can easily check this by looking at the `JRE System Library` in the `Package Explorer`. 

If all goes well, then you will have a Minecraft client open, which says `5 mods loaded` somewhere on the welcome screen, but more importantly when you view the list of mods this is will show `Example Mod` listed amongst them.
