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
