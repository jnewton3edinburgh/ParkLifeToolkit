# Parklife Toolkit

This is a quick-start guide for setting up your own instance of botpress and using the template chatbots created in the Parklife project.
For more information and more details documentation, please visit https://botpress.com/docs.

## Setup

### Downloading the toolkit
Download botpress for your operating system from here: https://botpress.com/download and unzip the folder to a sensible location.

Download the toolkit from here: https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/Parklife%20toolkit.tar.gz and unzip the folder to a sensible location.

### Starting up botpress
Open a terminal window. (Alternatively named Console/Command prompt, depending on your operating system).
Navigate to your botpress folder. (In windows type `cd` followed by the path to the botpress folder.)

Type `./bp` to run botpress.
You will see text appearing displaying the startup of the chatbot.

Navigate to `http://localhost:3000` in your web browser. You will be shown a login window.

*Note that if you have anything already running on your machine that uses this port, botpress will attempt to use the next available one. This should be noted on the startup text.*

It will ask you to sign up. All you need to provide is an email and passsword. These can be anything you choose as they are purely for login security. Remember these credentials as you will need them again to log back in.

## Usage

### Logging into botpress
Once you are logged in, you are provided with a list of bots, which should just display the test bot. Which you are welcome to play around with to get to grips with botpress. However, if all you want to do is to use the example bots and change the questions, I would advice skipping this for now.

### Importing the chatbots
To import the chatbots, click the dropdown ‘create bot’ and select ‘import existing’.
 
The window you are given allows you to create the bot ID for the chatbot. This will be used as part of the web address the end users will visit when they use the bot. So this should be something succinct and meaningful.

Then select the bot archive. Choose one of the parklife chatbots to import.

Once imported, the chatbot will appear in the bot list.
Now selected ‘configure’ next to this newly imported bot.
Here, you can change the Name of the bot, description and more details such as website and contact details.

You can also change the Bot avatar, which will be displayed to end users, and the cover picture.

The database is by default in SQLite. You can change to using PostGres, but this is more advanced and you can refer to the botpress documentation on how to do so.

### Using the chatbot on a remote server
If you intend on running this on a remote server, like the parklife chatbot which runs on the parklife website, you will need to connect to the remote server and upload your botpress folder to it.

From the remote server, then run the bp file and botpress will be running on the remote machine the same way as it runs on your local machine.

If connecting from a terminal window, this window must remain open for botpress to continue running. To have it run it the background, without needing this window open - refer here: 

### The database
The SQLite database is one file, named `botpressDatabase.db` in the botpress folder.

To read the database you need SQLite installed on your system, or at least software capable of reading SQLite databases.

*The database is by default in SQLite. You can change to using PostGres as the database, but this is more advanced and you can refer to the botpress documentation on how to do so.*