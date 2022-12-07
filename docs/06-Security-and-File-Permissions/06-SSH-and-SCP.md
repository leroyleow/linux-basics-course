# SSH and SCP
  
  You already know how to copy files from one location to another on the same system using the
  cp command. But what if you want to copy files from your local workstation to a Linux server or
  between Linux servers? For that you can use SCP or SFTP.

  SCP is secure copy and SFTP is SSH file transfer protocol. Sometimes SFTP is referred to as
  secure file transfer protocol. SCP and SFTP are both extensions of the secure shell (SSH)
  protocol. This means that if you have SSH key authentication configured for SSH, it will also
  work with SCP and SFTP.

  In order to use SCP or SFTP you need a client. Mac and Linux come with scp and sftp
  command line utilities. If you are running Windows, you can use the PuTTY Secure Copy Client
  (pscp.exe ) and the PuTTY Secure File Transfer client (psftp.exe ) programs.

  - Take me to the [Tutorial](https://kodekloud.com/topic/ssh-and-scp/)
  - In this lecture we will learn about SSH and SCP commands.
  - SSH is used to login to the remote computer.
  - SCP is used to copy of files/directories within the file system also can copy data to remote computer.

  #### SSH

  - To login to the remote server use **`ssh`** command with hostname or IP address.

    ```
    ssh <hostname OR IP Address>
    ```

  - To login to the remote server with specific username and password.

    ```
    ssh <user>@<hostname OR IP Address>
    ```

    **`-l`** attribute can also be used as 

    ```
    ssh –l <user> <hostname OR IP Address>
    ```

  #### Password-Less Authentication

  - Passwordless authentication can be setup via key-pair authentication in order to login to the remote server with password.

  - Public and Private key are stored at below location.
    
    ```
    Public Key: /home/bob/.ssh/id_rsa.pub
    ```

    ```
    Private Key: /home/bob/.ssh/id_rsa
    ```

  - To generate a keypair on the **`Client`** run this command

    ```
    bob@caleston-lp10 ~]$ ssh-keygen –t rsa
    ```

    ![key](../../images//key.PNG)

  - To copy the Public key from the client to the remote server

    ```
    bob@caleston-lp10 ~]$ ssh-copy-id bob@devapp01
    ```

    ![copy](../../images//copy.PNG)

 
  - Now **`Bob`** can login to remote server without password

    ```
    [bob@caleston-lp10 ~]$ ssh devapp01
    ```

    ![pless](../../images//pless.PNG)

  - Public Key is copied to the remote server at :

    ```
    [bob@caleston-lp10 ~]$ cat /home/bob/.ssh/authorized_keys
    ```
   
    ![auth](../../images//auth.PNG)

  #### SCP

   - To copy a compresses file to a remote server

     ```
     bob@caleston-lp10 ~]$ scp /home/bob/caleston-code.tar.gz devapp01:/home/bob
     ```
 
   - To copy a directory to a remote server

     ```
     [bob@caleston-lp10 ~]$ scp –pr /home/bob/media/ devapp01:/home/bob
     ```
     
     ![scp](../../images//scp.PNG)