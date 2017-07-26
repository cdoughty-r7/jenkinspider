# Jenkinspider
Jenkinspider is a plugin developed to be used in Jenkins to scan builds

### Prerequisite
Things that are needed:
* AppSpider Enterprise Rest URL
* Username and password for any clients in AppSpider Enterprise

### Version
2.0.0

### Steps
1. Build the hpi file (See How to build the hpi file section below)

2. In the browser, go to your jenkins server

3. Navigate to Manage Jenkins > Manage Plugins 

4. Navigate to the Advance tab

5. In the Upload Plugin section, click on the 'Choose file' button

6. Navigate to where the hpi file was created

7. Click on the Upload button

### How to build the hpi file
1. Clone the git repository
    ```sh
    $ git clone https://github.com/rapid7/jenkinspider.git
    ```
    
2. Change directory to the jenkinspider repository
    ```sh
    $ cd jenkinspider
    ```
    
3. Build the hpi file. For first time build run: 
    ```sh
    $ mvn hpi:run
    ```
    when the build is complete, kill the session by CTRL + C. This is needed to generate the necessary folder. 
    Then run the command to build the package.
    ```sh
    $ mvn hpi:hpi
    ```
    
5. The hpi file is located at target/jenkinspider.hpi

### Usage and Configuration
After installation of the plugin make sure you do the following:

1. Navigate to Jenkins System Settings

2. Add the REST URL for AppSpider Enterprise
    ```
    ex. https://<AppSpiderEnterpriseFQDN>/AppSpiderEnterprise/rest/v1/
    ```

3. Click `Add` to add credentials to use for AppSpider (one for each client).  Make sure you add the word `appspider` in the description of the credential.  This is required for credentials to show up.

4. Save system settings and add the Post Build process to a jenkins item.