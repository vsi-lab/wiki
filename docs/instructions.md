

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