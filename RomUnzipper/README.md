# RomUnzipper

## Description
This tool helps you to unzip roms and rename them using the zip file name in one fast execution. In the past if you used a rom-renamer program on your zipped roms, the program renamed only the file name of the zip files and not the actual rom file name (the compressed file), because they don't unzip and zip again the roms. So, when for some reason you want to unzip your roms, you will notice that some of them doesn't have the correct name given by the rom-renamer program, and that's the issue that this script helps you to manage.


With this script, you can unzip the roms and rename them using the name of the zip file, obviously not replacing the extension of the rom. __Please notice that this script expects zip files with only one rom file and no folders__, so if execptions of these two rules are found, the zip file is moved to a folder (**ZipFilesWithFolders** or **ZipsWithMoreThan1File** depending of the exception) and ignored from the process, so you can later unzip them manually.

## Usage
**REMEMBER: Always backup your roms before running this or any other process!!!**


1. First create a new folder where the script can work, for example `/home/diego/ROMS`, where "diego" is the name of the user for this use case


2. Go to that folder using a Terminal window:

   ```bash
   cd /home/diego/ROMS
   ```

3. Download the script inside that folder:

   ```bash
   wget https://github.com/BrosMakingSoftware/Roms-Management/raw/master/RomUnzipper/RomUnzipper.sh
   ```

4. Give execution permissions to the script using:

   ```bash
   chmod a+x RomUnzipper.sh
   ```

5. Now on that same folder, copy the folder (or folders) where your roms are stored, for this use case the folder copied to this location is called *SNESRen* (it can have any name, but a name without spaces is recomended)


6. Execute the script with the name of the roms folder as parameter, in this case:

   ```bash
   bash RomUnzipper.sh SNESRen
   ```

   Also notice that script and rom-folder(s) don't need to be on the same folder, they can have different locations, check this following example:

   ```bash
   bash RomUnzipper.sh /media/sf_shared/ROMS/NESRen/
   ```


7. The script will print information about the process, save this output for future reference. At the end, the script will make an small diagnostic to determinate if all files where extracted and will print a report indicating the final status

## Outputs
Here are some examples of the outputs of the script:

* When calling the script without parameters, the help is printed:
   ```
   ------------------------------
   ROM UNZIPPER SCRIPT V1.0
   ------------------------------

   Description:
   Use this script when you want to unzip all the roms of a given path.
   Besides unzip them, the roms are renamed using the zip file name (extension is not replaced).
   Zips containing more than one file or folders are excluded and moved to new folders.
   The folders are called ZipsWithMoreThan1File or ZipsWithFolders, they are created inside the given path.
   As a result, the folder UnzippedRoms is created with all the roms renamed.
   For more information, go to https://github.com/BrosMakingSoftware/Roms-Management/tree/master/RomUnzipper

   REMEMBER: Always backup your roms before running this or any other batch process!!!

   Syntax:
   bash RomUnzipper.sh [folder_path]

   Where:
   [folder_path] is the path of the folder that contains the zipped roms

   Example:
   If your [folder_path] is /home/diego/ROMS/SNES then call the script using
   bash RomUnzipper.sh /home/diego/ROMS/SNES
   ```

* This is a successful execution (a small one in order to not put too much text on this readme):

   ```
   ------------------------------
   ROM UNZIPPER SCRIPT V1.0
   ------------------------------

   ------------------------------
   Starting to check zip files on folder: /media/sf_shared/ROMS/snes/
   Please wait...
   ----------
   Found a name missmatch
   Zip Name: Super Mario All-Stars + Super Mario World (U) [o1+1C]
   Rom Name: Super Mario All Stars + Super Mario World (U)
   Renamed rom to: Super Mario All-Stars + Super Mario World (U) [o1+1C].smc
   ----------
   Found a name missmatch
   Zip Name: Super Mario World 2 - Yoshi's Island (U) (M3) (V1.0) [!]
   Rom Name: Yoshi's Island (V1.0) (U)
   Renamed rom to: Super Mario World 2 - Yoshi's Island (U) (M3) (V1.0) [!].smc


   ------------------------------
   ------------------------------
   Report:
   Ignored zips (with folders inside)    : 0
   Ignored zips (with more than 1 files) : 0
   Total ignored files                   : 0
   ----------
   Processed zips : 6
   Extracted roms : 6
   Renamed roms   : 2
   Count of zips processed matches the count of roms extracted.
   ------------------------------
   ------------------------------


   ----------End of script----------
   ```
