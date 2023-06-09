# jneedle
Yet another jar malware detection tool

---
## How to find the needle in a haystack? - Use a strong enough magnet

The detection tool is parsing jar `.class` files looking for signature instruction sequences.
It is actually similar to string search:

Is the following sequence: `"jump into the well"`
in the program:
```text
exit house and lock door,
get the bus and to the shop to buy milk
jump into the well then get the bus
come home
```

## See the **light** at the end of the tunnel
### Add to PrismLauncher

### Extra jar // recommended but harder to set-up
1. Check current launch classpath in the Version menu:  
Select the Fabric/Forge/Quilt/Minecraft (most bottom of these) and on the right menu, click Customize then Edit
2. This will open a text-editor, look for the `mainClass` entry in the class  
Fabrc for example: `"mainClass": "net.fabricmc.loader.impl.launch.knot.KnotClient",`
3. Save (copy) the entry value: `net.fabricmc.loader.impl.launch.knot.KnotClient`
4. close the editor and optionally click Revert in Prismlauncher
5. click `Add to Minecraft.jar` button and select jneedle.jar
6. Click edit while jneedle.jar is selected
7. Add the following to the json:  
`"+jvmArgs": ["-Ddev.kosmx.jneedle.launchClass={launchClass}"],` where you replace `{launchClass}` with the earlier saved class.
8. Add the following to the json:  

8. Save the file and have fun!

--- 

**The lines for specific launchers:  
Quilt: `"+jvmArgs": ["-Ddev.kosmx.jneedle.launchClass=org.quiltmc.loader.impl.launch.knot.KnotClient"],`  
Fabric: `"+jvmArgs": ["-Ddev.kosmx.jneedle.launchClass=net.minecraft.launchwrapper.Launch"],`   
Forge up to 1.12.2: `"+jvmArgs": ["-Ddev.kosmx.jneedle.launchClass=net.minecraft.launchwrapper.Launch"],`  
Forge from 1.13.2: `"+jvmArgs": ["-Ddev.kosmx.jneedle.launchClass=io.github.zekerzhayard.forgewrapper.installer.Main"],`  

### Easy path // slow but easy-to-setup
1. In the game version menu, click `Add agents`:  
2. Select jneedle.jar
3. Done. (It will be slow in large modpacks)

