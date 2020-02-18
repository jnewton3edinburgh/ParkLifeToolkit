# Parklife Toolkit

This is a quick-start guide for setting up your own instance of botpress and using the template chatbots created in the Parklife project.
For more information and more details documentation, please visit https://botpress.com/docs.

## Setup

### Downloading the toolkit
Download botpress for your operating system from here: https://botpress.com/download and unzip the folder to a sensible location.

Download the toolkit from here: https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/Parklife%20toolkit.tar.gz and unzip the folder to a sensible location.

Place the contents of the toolkit folder into the botpress folder. Your botpress folder should look something like this:

![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20folder.png "Botpress folder contents")

**The contents**:

* bindings folder
* modules folder
* bp / bp.exe

These are included by default in the botpress download. They are used to run and manage the chatbot server.

* botpressDatabase.db

This is an empty database file used by the chatbot to store interactions with it. This has been provided by the Parklife toolkit so you don't have to create one. This will become populated with data as the chatbot is used.

* .env

This is the environment file that points the chatbot at the database it should use. This points to a file named `botpressDatabase.db`, which is the previously mentioned file.

* getCSV.sql

This is an sqlite script to extract a list of questions and answers in CSV format from the database.

* ParklifeChatbot.tgz

This is the parklife chatbot. It has been provided so that it can be imported into a new instance of botpress and immediately used.

* images folder

This folder contains the chat bot images used in the Parklife project. It contains an image of Alfred the owl, used as the chatbot iamge, and background of four parks.

*Do not worry if you are missing the `data` folder, as this is not included in the Windows download.*

*Folders and files may be created as the chatbot(s) are used.*


### Starting up botpress
Open a terminal window. (Alternatively named Console/Command prompt, depending on your operating system).
Navigate to your botpress folder. (Type `cd` followed by the path to the botpress folder. e.g. `cd C:\botpress` in windows, or `cd /home/username/botpress` in linux or `cd /Applications/botpress` in MacOS.)

Type `./bp` to run botpress.
You will see text appearing displaying the startup of the chatbot. Botpress will now be up and running!

In your web browser, navigate to `http://localhost:3000`. You will be shown a login window.

![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20login.png "Botpress login window")

*Note that if you have anything already running on your machine that uses this port, botpress will attempt to use the next available one. This should be noted on the startup text.*

It will ask you to sign up. All you need to provide is an email and passsword. These can be anything you choose as they are purely used for login security. Remember these credentials as you will need them again to log back in.

## Usage

### Logging into botpress
Once you are logged in, you are provided with a list of bots, which should just display the test bot.

### Importing the chatbots
To import the chatbots, click the dropdown ‘create bot’ and select ‘import existing’.

![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20import%20bot.png "Botpress import chatbot")
 
The window you are given allows you to create the bot ID for the chatbot. This will be used as part of the web address the end users will visit when they use the bot. So this should be something succinct and meaningful.

Then select the bot archive. Choose the parklife chatbot to import.

Once imported, the chatbot will appear in the bot list.
Now selected ‘configure’ next to this newly imported bot.
Here, you can change the Name of the bot, description and more details such as website and contact details.

You can also change the Bot avatar, which will be displayed to end users, and the cover picture.

### Editing the chatbot

*I will only give basic instructions on changing and editing questions here, as you should consult the botpress documentation for more complex and detailed guidance and instructions.*

#### Overview

The chatbot is built as a flow diagram:

![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20flow.png "Botpress import chatbot")

Each box (named a `node` by botpress) is where the chatbot will perform an action.
Once the action is complete, the chatbot moves to the linked box as illustrated by the black lines.

The chatbot starts where the `start` green dot is indicated, on the very top, left, of the flow. When the chatbot has performed its action, in this case introducing itself, it goes to the next node where it asks a question.

*Use the scrollwheel to zoom in and out. Note that this may be time consuming on larger chatbots!*

#### How it works

Click on a box to see its contents on the left panel of the page.

A `node` has 3 things it does:
1. On Enter - what it does immediately
2. On Recieve - What it does
3. Transitions - What node it goes to next

![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20node.png "Botpress node")

* An example of `On Enter` - Say some text
* An example of `On Recieve` - Wait for user input
* An example of `Transitions` - Go to next question

#### Change a questions

Click on a question
Click on the `On Enter` section in ther left panel
Hover over the text and click `edit`.
Click the pencil icon to edit the text
Click `Submit` then ¬Update action` to update the wording.

Some questions have information about the park following them.
To change this, do the exact same as above, but change the text in the `On recieve` section.

#### Add a free text question

Drag and drop `Node` under `Tools` on the left panel onto the flow diagram in an open space.

Make sure this new `node` is selected and press the plus button under the `On Enter` srection and select `Text` > `Add new text` to add the question you want. Type it in and select`Save` and `Update node`.

#### Wait for user feedback

Select the node you created
Click on `On Recieve` on the left panel.
Tick the `Wait for user feedback` box.

#### Add question transition

This is adding the link to the next question after this question is answered. This is required for the chatbot to continue after this question.
Make sure this new `node` is selected
Click on `Transitions` on the left panel
Click the Plus icon button
Select `Always` and `Transition to node` to always go to another question after this one is answered.
Click `Create`

#### Add a multiple choice question

Drag and drop `Choice` under `Tools` on the left panel onto the flow diagram in an open space.

In the pop-up window, select the folder button, then `Create new single choice`. Now enter your question and the answers you want.

The message and values for each choise are what is dispalyed to the user, and what will be saved to the database, respectively. These can be the same for simplicity.
Now select`Save` and `Insert`.
`Wait for user feedback` and transition points are already created for you.

#### Connect the new question

Connect the question to a previous and next question in the flow by dragging the small square at the top of the node to the previous questions bottom.

![alt text](https://github.com/jnewton3edinburgh/ParkLifeToolkit/raw/master/documentation%20images/botpress%20node%20connection.png "Botpress node connection")

#### Copy an existing question

To make the question creation process easier, rightclick and copy an existing node then right click and paste. Edit as before.

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