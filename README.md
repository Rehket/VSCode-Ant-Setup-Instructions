# Setting Up VS Code with Ant for SFDC Development.

## Requirements
- Vs Code - Any recent version should work.
- Java - Any recent version should work.
- Apache Ant v1.10.~ - Link: https://ant.apache.org/index.html
- SFDC Ant Migration Tool - Link: https://gs0.salesforce.com/dwnld/SfdcAnt/salesforce_ant_44.0.zip

## Getting Everything Setup
### Installation
For VS-Code and Java, just download the installers.
- Install Vs-Code
- Install Java 

### Configuration

#### Configuring Vscode
- Once vscode is installed, you open the estensions pane on the left side with ``` Ctrl+Shift+X``` and sesach for SalesForce.

- You should see the SalesForce Extension Pack. Click Install.

- Once the extension is installed, reload vscode. 

#### Configuring Ant

For Apache Ant, Download the zip file, extract it and make a note of the extracted location.
- Download and unzip Apache Ant
- Set the variable ANT_HOME to the location where you unzipped Apache Ant.
- Download the the Ant Migration Tool from SalesForce and make a note of the location.

Restart the computer, open a terminal, and type: ```ant -version```

You should see something like:

```Apache Ant(TM) version 1.10.5 compiled on July 10 2018```

#### Configuring SFDC Migration Tool

- Unzip the file you downloaded from salesforce earlier, it should be something like salesforce_ant_{version}.zip. At the time of making these instructions, it was salesforce_ant_44.0.zip

- In the zip file are some examples of package files and build files like thos included in this repo. The main file we need to worry about is the ant-salesforce.jar, as it is what lets us use ant to push and pull code from sfdc.

- The ant-salesforce.jar file can be placed anywhere as long as the build file references it in the correct location. So you can place in in the ant libraries directory or your user directory, or anywhere really so long as you update the build file. 

- Once you have saved the updated build file, open vscode in the directory repo directory.

- Once vscode is running, open a terminal with ``` Ctrl + Shift + ` ``` and type ``` ant break ``` . This command disconnects the repo 




