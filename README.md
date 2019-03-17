### Deploying SS and BBR by Ansible, once you deployed, it can start automatically with you server rebooting. Just supporting CentOS now. 

**1. Create SSH keys.**<br>
    Run the command and save the keys under the sshkey folder:
    
        $ ssh-keygen -t rsa 
    
**2. Copy the public key to the server you set up.(you can set it when you at the server building panel if you use Vultr)**

**3. Replacing the xx.xx.xx.xx with your server ip at the hosts file.**

**4. Run:**

        $ chmod 400 sshkey/*

**5. Run the ansible command.**
- Run the command on your local server with default values:

        $ ansible-playbook -i hosts deploySS.yml
        
    The default values:<br>
    ```
        username: loveuser
        password: 12345676
        port1: 1314
        port2: 19001
        port3: 19002
        port4: 19003 
        
    # The username is set for ssh login.
    # The password is set for ssh login and the SS.
    ```

- Run the command on your local server with the values replaced the xxx :

        $ ansible-playbook -i hosts -e "username=xxx password=xxx port1=xxx port2=xxx" deploySS.yml
        
        with -vvv or -vvvv option you can see the deploying process

**6. You can register a [Vultr server](https://www.vultr.com/?ref=7940489-4F)**
