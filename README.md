# redage_v3
1. Node.JS version requirements
We need a specific version of Node.JS that includes the desired version of npm.
Node.JS version: 16.14.0
npm version: 8.3.1

You can download the official release of the desired version of Node.js from here:
Index of /download/release/v16.14.0/

2. Database installation
You need to install the MySQL service, if you don't have one, you can use XAMPP, which will install everything you need yourself.
Using the GUI for interacting with the database, which is convenient for us (I use HeidiSQL), we need to fill in all 3 databases that are in the database folder.

3. Assembly of the server part
To edit the server side, we need an IDE that allows us to edit and build C# code - we can use Visual Studio (for example, the Community 2022 version).
Opening server-main open NeptuneEvo.sln (using our previously installed IDE) and search in the solution explorer for NeptuneEvo, open it and find the Database folder with the Config and Server folders inside.
By clicking on the Config.tt file inside the Config folder, we need to configure the connection of the script to the "mainconfig" database on line 24.
The same must be done with the ServerStruct.tt file inside the Server folder, but the connection must be before the "main" database, also on line 24.
After the changes have taken effect, the IDE will automatically generate the necessary files for the server part, after which you can build the project using the "Build" -> "Rebuild project" button.
In the output window (below) you will be able to see the path where the files will be successfully built.

4. Building the client side
You need to open the client-master folder and open PowerShell in it.
Then we write the following command:
npm i
This command will install all required build dependencies.
This command needs to be written only 1 time - for the very first time, since in the future all the necessary dependencies will already be installed.
When the dependencies are successfully installed, we need to write the following command:
npm run build
This command will collect the entire client script into 1 file in the client_packages folder, which is next to the client-master folder.

5. Assembly of CEF parts
You need to open the cef-master folder and open PowerShell in it.
Then we write the following command:
npm i
This command will install all required build dependencies.
This command needs to be written only 1 time - for the very first time, since in the future all the necessary dependencies will already be installed.
When the dependencies are successfully installed, we need to write the following command:
npm run build
This command will compile the entire CEF into several files in the client_packages/interfaces folder, which is next to the cef-master folder.

6. Server settings files
The server_files archive contains 2 folders that need to be placed next to the ragemp-server.exe executable file.
Inside the settings folder, you need to open the mainDB.json file and configure the connection to the "main" database.

7. Bottom line
After successfully completing all the points above, it's up to you, everything is ready for use and editing.


(Harlands files)
