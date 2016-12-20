# RomUnzipper

## Description
This tool helps you to unzip roms and rename them using the zip file name in one fast execution. In the past if you used a rom-renamer program on your zipped roms, the program renamed only the file name of the zip files and not the actual rom file name (the compressed file), because they don't unzip and zip again the roms. So, when for some reason you want to unzip your roms, you will notice that some of them doesn't have the correct name given by the rom-renamer program, and that's the issue that this script helps you to manage.


With this script, you can unzip the roms and rename them using the name of the zip file, obviously not replacing the extension of the rom. __Please notice that this script expects zip files with only one rom file and no folders__, so if execptions of these two rules are found, the zip file is moved to a folder (**ZipFilesWithFolders** or **ZipsWithMoreThan1File** depending of the exception) and ignored from the process, so you can later unzip them manually.

## Usage
**REMEMBER: Always backup your roms before running this or any other process.**


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

5. Now on that same folder, copy the folder (or folders) where your roms are stored, for this use case the folder copied to this location is called *NESRen* (it can have any name, but a name without spaces is recomended). So in ROMS folder you now have _RomUnzipper.sh_ script and _NESRen_ folder


6. Execute the script with the name of the roms folder as parameter, in this case:

   ```bash
   bash RomUnzipper.sh NESRen
   ```


7. The script will print information about the process, save this output for future reference. At the end, the script will make an small diagnostic to determinate if all files where extracted and will print a report indicating the final status
