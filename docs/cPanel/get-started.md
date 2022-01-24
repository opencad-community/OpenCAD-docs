# Getting Started
===============

To jump-start your installation of OpenCAD on your web host, head to the [OpenCAD website](https://opencad.io) or directly to the [Github Repo](https://github.com/opencad-app/OpenCAD-php/releases) to grab the latest release. At the time of this document, the latest release is version 0.3.2, therefore we will be utilizing this in our examples.

Once you have the **.zip folder** downloaded to an easily accessible directory, proceed to your web host service by entering cPanel and navigating to the "public\_html" directory. Typically the upload is completed by uploading the .zip folder and extracting the contents. We recommend doing this as well to prevent upload issues. Extract the files then navigate to the newly created folder. Select all of the contents and move them to the **public\_html** directory. The SQL folder will be utilized in a later portion of the walkthrough, but it is recommended to use the SQL files from the download stored on your computer.

Now that you have uploaded a significant portion of OpenCAD, head back out to your cPanel and configure a database user, utilizing the wizard tool. Ensure this user has the full permissions to access the database. _**Keep track of these credentials! You will need them in the OpenCAD Installation Wizard.**_

## Open the Installation Wizard
----------------------------

Navigate to the installation wizard by going to your domain and adding “/oc-install/start.php” to the end of the URL. As an example, navigate in a new tab to `http://www.yourdomain.com/oc-install/start.php` This will initialize the Installation wizard for OpenCAD. Follow the steps to get started and heed all warnings.

### Connect to the Database

The first step in this installation process is connecting OpenCAD to your created database. Recall the credentials utilized above when starting the database and fill out the appropriate fields. **Note the Database Prefix field is automatically filled in.** **DO NOT CHANGE IT.** Keep note of this for the next step. 

Do **NOT** press “test connection” - this will endlessly spin.

### Edit SQL Files

**THERE HAS BEEN A FILE PATH UPDATE! YOU NOW HAVE SELECTIONS FOR DIFFERENT GAMES.** 

Before importing your SQL files to your database, we will need to do some editing. Open the file **oc\_GTAV\_data.sql** in a text editor and perform a Find + Replace search for <DB\_PREFIX> to replace that phrase with your database prefix as found in the prior step. 

 Make sure you change all of them and **SAVE** the files!

You will need to repeat these steps for the oc\_install.sql and oc\_update.sql files as well.

Upload the “**oc\_install.sql**” and “**oc\_GTAV\_data.sql**” files to your database.

The “oc\_update.sql” file is only used for updating. Keep this file around in the event you need to perform an update down the road.

### Administrator Account

Now that you can connect to your database, the wizard is establishing the “owner” account to log in. Make sure that you have access to the email you use and that you remember the credentials you configure - there is no reset function written in yet! (If you forget your password, you will have to do a fresh install again.)

### Core Settings

In this section, you will be setting up core settings for your community.

**Community Name** - the name of your roleplay community!

**Application URL** - the URL of your installation. 

Valid Examples include:

*   //example.com - Root domain, no subdirectory
*   //subdomain.example.com - subdomain, no subdirectory
*   //subdomain.example.com/subdir - subdomain with subdirectory
*   //example.com/subdir - root domain with subdirectory

The OpenCAD team does not recommend including the trailing / on any of the above examples. It won't necessarily break anything but just makes reference look strange having two slashes that aren't needed.

**CAD From Email** \- the email address for outbound emails from the application.

**CAD To Email** - the email address for inbound emails to the application.

### Department Settings

This section configures what the three core departments have access to. All of these True/False toggles determine what is visible in the MDT for each department. 

### Civilian Settings

Similar to Department Settings, this section governs permissions for Civilians.

*   Civilian Maximum Identities: Maximum number of characters per user, 0 for no limit.
*   Civilian Maximum Vehicles: Maximum number of vehicles allowed to be registered, 0 for no limit.
*   Civilian Maximum Weapons: Maximum number of weapons allowed to be registered, 0 for no limit.

### Administrative Configuration

Control what moderators are allowed to do and see within the application.

### Extra Settings

*   Demo Mode - If it is set to true, some administrative features will be locked down. If it is set to false, you are given the full functionality of the application.
*   Gravatar - Allow OpenCAD to find each user's Gravatar profile image as their profile picture. If it does not exist, it will default to OpenCAD's configuration.

Ready to Install
----------------

At this point, the installation wizard has enough data to create the necessary content as you have provided. Press continue to run the installation.

Follow the advisory direction of removing the **oc-install** folder from your server.

Congrats! Log into your application!