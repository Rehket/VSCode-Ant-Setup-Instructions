# Setting Up VS Code with Ant for SFDC Development.

## Requirements
- You need to have admin permissions on your computer. 
- Vs Code - Link: https://code.visualstudio.com/
- Java - Any recent version should work.
- Apache Ant v1.10.~ - Link: https://ant.apache.org/index.html
- SFDC Ant Migration Tool - Link: https://gs0.salesforce.com/dwnld/SfdcAnt/salesforce_ant_44.0.zip

## Getting Everything Setup
### Installation
For VS-Code and Java, just download and run the installers.
- Install Vs-Code
- Install Java 


#### Installing Ant
1. Download the Zip File from https://ant.apache.org/bindownload.cgi
2. Unzip the contents to a directory you will remember. For example, C:/Users/{Your Username}/Ant
3. Next,  Open a Run prompt and enter ```sysdm.cpl ,3```  .
4. Click on Environment Variables
5. You will need to define and new System Variable and add an entry to the path variable. 
6. Create a variable called ```ANT_HOME``` and assign it the value of the directory where ANT was unzipped. 

        C:/Users/{Your Username}/Ant

7. Next, you will need to add an entry to the ```path``` variable that points to the bin folder within the ant home.

        C:/Users/{Your Username}/Ant/bin

8. Restart the computer to make sure the changes are applied.

#### Installing SFDC Ant Migration Tool
1. Download the Zip File from https://gs0.salesforce.com/dwnld/SfdcAnt/salesforce_ant_44.0.zip

2. Unzip the contents to a place you will remember. Ex: ``` C:/Users/{Your Username}/SFDC_ANT ```

3. run ```ant -version``` in powershell to verify your installation. If you see the version printed, you are all set. 
        
```shell 
Apache Ant(TM) version 1.10.5 compiled on July 10 2018
```

4. Within this repo, navigate to the build.xml file and change the ant lib resource to migration tool we unzipped. 
```xml 

<taskdef resource="com/salesforce/antlib.xml" uri="antlib:com.salesforce">
        <classpath>
            <!-- Change the relative reference to point ath the unzip location. -->
            <!-- <pathelement location="../ant-salesforce.jar" /> -->  	
            <pathelement location="C:/Users/{Your Username}/SFDC_ANT/ant-salesforce.jar" />	
        </classpath>
</taskdef> 

```

5. Save the build.xml file.

6. Rename the ```example-build.properties``` file to ```build.properties```.

7. Open the ```build.properties``` file and set your credentials. ```build.properties``` is set to be ignored by git so your credentials are not committed. Additionally, you can set the credentials as environment variables or pass them as parameters if you do not wish to save them in the file. 

```python
# Specify the login credentials for the desired Salesforce organization
sf.username = yourSFDC_Username@domain.com.SandBoxName
sf.password = yourSFDC_sfdcPassword+token
# Example sf.password = myPasswordMyToken323422525hb45g4

```

### Configuration

#### Configuring Vscode
1.  Once vscode is installed, you open the extensions pane on the left side with ``` Ctrl+Shift+X``` and search for SalesForce.

2. You should see the SalesForce Extension Pack. Click Install. Once the extension is installed, reload vscode. 

3. Open VSCode's settings with ```Ctrl+,``` and type ```Shell: Windows``` in the search bar. 

4. Change the default shell to Powershell. The installation location can be found by searching for powershell and selecting ```Open File Location``` from the right click menu until you get to the executable. 

        Ex: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe






