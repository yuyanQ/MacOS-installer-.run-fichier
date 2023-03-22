# MacOS download and run Unitex/GramLab 3.3

When I download Unitex/GramLab in `MacOS Vendura 13.1`, I don't know how to open the file `Unitex-GramLab-3.3-osx.run` and add the icon in Launchpad.

This is how I solve the problem of running the file :

Open Terminal and use the following command :

```
  cd ~/Download 
  chmod +x  filename.run
  ./filename.run
```
Please note that the paths "~/Download" in the above commands may need to be changed to your actual paths.

And now you can open the `/YourUserName/Unitex-GramLab-3.3`. Click the file "App" and choose ``Unitex.jar`` or ``GramLab.jar`` to run Unitex/GramLab.


-----------------------
# How to Add the Icon to an Application in Launchpad
When I finished the installation, I continued to add the icon in Launchpad.

If you find that an application in Launchpad doesn't have an icon or the icon is incorrect, you can manually add or replace the icon using the following steps.


## Prerequisites

- You need to have the icon file in the `.icns` format.

  The icon file in `/YourUserName/Unitex-GramLab-3.3/App` is in `.ico` format (Image icône Windows). 

  There are many ICO to ICNS free converters online.

## Steps

1. Open Terminal and use the following command to create Unitex's package directory :
    ```
    sudo mkdir /Applications/Unitex.app
    ```
2. Copy the "App" file to this application package and change the file name to `Contents`. So you will have all the contents in path `/Applications/Unitex.app/Contents/`. 

3. Create a file `Resources` in the file `Contents` and copy the .icns file to the following location: 
    ```
    /Applications/Unitex.app/Contents/Resources/
    ```
4. Update the `Info.plist` File :
    - Open Terminal and navigate to your application's package directory by running the following command :
    ```
    cd /Applications/Unitex.app/Contents/
    ```
    - Open the Info.plist file in a text editor by running the following command :
    ```
    nano Info.plist
    ```
    - Add the following key-value pair to the file and save the change :
    ```
    <dict>
        <key>CFBundleExecutable</key>
        <string>Unitex</string>
        <key>CFBundleIconFile</key>
        <string>Unitex.icns</string>
    </dict>
    ```
    - In the nano editor, press "Ctrl" and "O" keys, then press "Enter" to save the file. 

    - Then, press "Ctrl" and "X" keys to close the editor.

5. Restart the Dock process. Use the following command to restart the Dock process :
    ```
    killall Dock
    ```
6.Check if the icon is displayed. After completing the above steps, you should be able to see the icon of your application in Launchpad.
