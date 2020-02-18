# Parklife Toolkit

This is a quick-start guide for setting up your own instance of botpress and using the template chatbots created in the Parklife project.
For more information and more details documentation, please visit https://botpress.com/docs.

## Setup

### Downloading the toolkit
Download botpress for your operating system from here: https://botpress.com/download and unzip the folder to a sensible location.

Download the toolkit from here: https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/Parklife%20toolkit.tar.gz and unzip the folder to a sensible location.

Place the contents of the toolkit folder into the botpress folder. Your boitpress folder should looksomethihg like this:
![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20folder.png "Botpress folder contents")

The contents:

*Do not worry if you are missing the `Data` folder, as this is not included in the Windows download.*

* bindings folder
* modules folder
* bp / bp.exe

These are included by default in the botpress download. They are used to run and manage the chatbot server.

* botpressDatabase.db

This is an empty database file used by the chatbot to store interactions with it. This has been provided by the Parklife toolkit so you don't have to create one. This will become populated with data as the chatbot is used.

* .env

This is the environmentfile that points the chatbot at the database it should use. This points to a file named 'botpressDatabase.db', which is the previously mentioned file.

* getCSV.sql

This is an sqlite script to extract a list of questions and answers in CSV format from the database. 

* ParklifeChatbot.tgz

This is the parklife chatbot. It has been provided so that it can be imported into a new instance of botpress and immediately used.

* images folder

This folder contains the chat bot images used in the Parklife project. It contains an image of Alfred the owl, used as the chatbot iamge, and background of four parks.

*Folders and files may be created as the chatbot(s) are used.*

### Starting up botpress
Open a terminal window. (Alternatively named Console/Command prompt, depending on your operating system).
Navigate to your botpress folder. (In windows type `cd` followed by the path to the botpress folder. e.g. `cd C:\botpress`)

Type `./bp` to run botpress.
You will see text appearing displaying the startup of the chatbot. Botpress will now be up and running!

In your web browser, navigate to `http://localhost:3000`. You will be shown a login window.
![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20login.png "Botpress login window")

*Note that if you have anything already running on your machine that uses this port, botpress will attempt to use the next available one. This should be noted on the startup text.*

It will ask you to sign up. All you need to provide is an email and passsword. These can be anything you choose as they are purely for login security. Remember these credentials as you will need them again to log back in.

## Usage

### Logging into botpress
Once you are logged in, you are provided with a list of bots, which should just display the test bot. Which you are w![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

### Importing the chatbots
To import the chatbots, click the dropdown ‘create bot’ and select ‘import existing’.
 
The window you are given allows you to create the bot ID for the chatbot. This will be used as part of the web address the end users will visit when they use the bot. So this should be something succinct and meaningful.

Then select the bot archive. Choose one of the parklife chatbots to import.

Once imported, the chatbot will appear in the bot list.
Now selected ‘configure’ next to this newly imported bot.
Here, you can change the Name of the bot, description and more details such as website and contact details.

You can also change the Bot avatar, which will be displayed to end users, and the cover picture.

### Using the chatbot on a remote server
If you intend on running this on a remote server, like the parklife chatbot which runs on the parklife website, you will need to connect to the remote server and upload your botpress folder to it.

From the remote server, then run the bp file and botpress will be running on the remote machine the same way as it runs on your local machine.

If connecting from a terminal window, this window must remain open for botpress to continue running. To have it run it the background, without needing this window open - refer here: 

### The database
The SQLite database is one file, named `botpressDatabase.db` in the botpress folder.

To read the database you need SQLite installed on your system, or at least software capable of reading SQLite databases.

*The database is by default in SQLite. You can change to using PostGres as the database, but this is more advanced and you can refer to the botpress documentation on how to do so.*

### The SQL script

The `getCSV.sql` file included in the toolkit is a script to extract a list of questions and answers from the botpres database. This requires sqlite installed.