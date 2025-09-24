# manifest-writer-non-ui-b4j

Write or update manifest.txt for b4xlib distribution

## How to use
1. Add the #Macro tag to call *manifest-writer-non-ui.jar* from B4X additional libraries folder
   e.g
   ```B4X
   #Macro: Title, Version, ide://run?file=%JAVABIN%\java.exe&Args=-jar&Args=%ADDITIONAL%\..\B4X\manifest-writer-non-ui.jar&Args=%PROJECT%\..\release&Args=%PROJECT%\..\release&Args=Version&Args=add.1
   ```
2. This tool expects at least 2 arguments
3. First argument is source folder contains the manifest.txt
4. Second argument is the destination folder where the updated manifest.txt is saved (in my practice I use a release folder)
5. Adding 2 more arguments to update the entry \
   e.g Version add.1 \
   So the Macro tag will call a command like:
   ```
   java.exe -jar manifest-writer-non-ui.jar *source_path* *release_path* Version add.1
   ```
   This will auto increment the version by 0.1
6. More arguments can be added in pairs
7. Click the title button to activate the action

## Tips:
1. The manifest.txt file in source folder can be a template with empty values
2. The source folder can be the same as destination folder
3. Use %20 or + for blank space in key or value \
    e.g. Supported Platforms=B4J (the keys contains a blank space) \
    The command should look like: \
```
java.exe -jar manifest-writer-non-ui.jar source_path destination_path Version 2.00 Supported+Platforms B4J
```
