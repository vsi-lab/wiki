

## Lambda server usage

* Log in to the Lambda Cloud servers:
    - Visit [Lambda Cloud](https://cloud.lambdalabs.com/login) and log in.

* Create a private SSH key
    - Click on SSH Keys on the left side and create a private SSH key. A private key with the extension `.pem` will be downloaded. This key will be used for connecting to the server.

* Launch an instance:
    - Click on Instances on the left menu, then click on Launch Instance.
    - Multiple GPU options will be displayed. Click on the required GPU and follow the instructions to create the file system.
    - Wait until the status of the instance changes from booting to running.
* Change the permissions of the private key:
    - While the instance is booting, change the permissions of the private key to public with the following command: `chmod 600 path/to/key.pem`
* Connect to the server:
    - Once the status turns running, open your terminal, VS Code, or any SSH client of your choice, and use the following command to connect to the server: `ssh -i /path/to/key.pem ubuntu@xxx.xxx.xxx`
    - The `ubuntu@xxx.xxx.xxx` address can be found on the Lambda website near the status.
    - You have now successfully connected to the server!
### Note
- Ensure that the region where the file system is created matches the region of the instance. For example, if the file system is created in the California region, the instance must also be created in the California region so that they can be properly mapped.
- Please terminate the instances once the experiments are completed and saved to the file system. Instances will incur charges from the time they are started. You can start a new instance and map it to the same file system to resume your work.
- The billing policy for the file system is based on the data size you utilize and the number of hours the data is stored in their file system.


## Guidelines for accessing VSI Lab Server

Before attempting to connect to the lab server, ensure that you have received permission. Contact **Dr. Eung-Joo Lee** at `eungjoolee@arizona.edu` for access, and once you have permission, follow the
instructions below.

1.  ### Establish VPN Connection

    Use the **Cisco AnyConnect** application to connect to the VPN. If you dont have AnyConnect, you
    can follow the instructions here to download and install it in your laptop

    - **VPN Address**: `vpn.arizona.edu/Engineering`
    - Open the AnyConnect app, enter the VPN address, and authenticate using your university credentials

2. ### Test the Connection to the Server

    To test the server connection, follow these steps:
    
    1. Open a terminal or command prompt.
    2. Connect to the server with the following command:  
    ``` ssh username@server-ip-address```
    3. Verify that your user account appears by listing the directory contents.  
    ``` ls -la /data ```
    If you do not see your username, contact IT support at `support@engr.arizona.edu`

3. ### Connect VS code to the Server.

    Once the VPN and server connection are verified, you can use VS Code for development.


    1. Install the **Remote-SSH** extension in VS-code.
    2. Open the extension and click the plus sign (+) to add a new remote.
    3. Use the following SSH command:  
        ```ssh username@server-ip-address -A```
    4. Enter your password when prompted.


4. ### Clone a Git Repository
    You can now, clone your Git repository to the server and start coding:
    1. Click **Clone Git Repository** in VS Code
    2. Provide the repository URL:  
        ```https :// github.com/github -username/your_repo_name.git```
    3. When prompted, choose to save it under `/data/username/mydirectory`
    4. Trust the workspace by clicking **Yes** when asked by VS Code

5. ### Create a Virtual environment
    1. Press `Cmd + Shift + P` (or `Ctrl + Shift + P`) to open the command palette.
    2. Search for and select **Python: Select Interpreter**.
    3. Choose **Create Virtual Environment**, then select **venv** and the desired Python version.
### (Optional) Create a `.gitignore` file

You may want to create a `.gitignore` file to prevent unnecessary files from being pushed to the
repository. For example, to exclude the .venv directory, add the following to your `.gitignore`:  
```/.venv```


    