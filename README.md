# ansible-config-mgt
ANSIBLE CONFIGURATION MANAGEMENT – AUTOMATE PROJECT 7 TO 10

# INSTALL AND CONFIGURE ANSIBLE ON EC2 INSTANCE

Update Name tag on your Jenkins EC2 Instance to Jenkins-Ansible. We will use this server to run playbooks.
In your GitHub account create a new repository and name it ansible-config-mgt.
Instal Ansible

![text1](https://user-images.githubusercontent.com/108102087/197759770-5e9618f6-dccf-4f09-a2a4-533526808e0f.PNG)

Configure Jenkins build job to save your repository content every time you change it – this will solidify your Jenkins configuration skills acquired in Project 9.
Create a new Freestyle project ansible in Jenkins and point it to your ‘ansible-config-mgt’ repository.
Configure Webhook in GitHub and set webhook to trigger ansible build.
Configure a Post-build job to save all (**) files, like you did it in Project 9.
Test your setup by making some change in README.MD file in master branch and make sure that builds starts automatically and Jenkins saves the files (build artifacts) in following folder

![text2](https://user-images.githubusercontent.com/108102087/197763753-6ac8d126-5432-4eb5-a438-815a94ca3411.PNG)
After updating the build, the third build was successfully initiated.

![text3](https://user-images.githubusercontent.com/108102087/197764167-4d647cc1-736c-4242-a4bc-201af13b275a.PNG)

![text4](https://user-images.githubusercontent.com/108102087/197764877-03c22088-2099-4c6a-9fb5-6f4d8e105839.PNG)

Prepare your development environment using Visual Studio Code
First part of ‘DevOps’ is ‘Dev’, which means you will require to write some codes and you shall have proper tools that will make your coding and debugging comfortable – you need an Integrated development environment (IDE) or Source-code Editor. There is a plethora of different IDEs and Source-code Editors for different languages with their own advantages and drawbacks, you can choose whichever you are comfortable with, but we recommend one free and universal editor that will fully satisfy your needs – Visual Studio Code (VSC), you can get it here.

After you have successfully installed VSC, configure it to connect to your newly created GitHub repository.

Clone down your ansible-config-mgt repo to your Jenkins-Ansible instance

git clone <ansible-config-mgt repo link>

  # BEGIN ANSIBLE DEVELOPMENT
In your ansible-config-mgt GitHub repository, create a new branch that will be used for development of a new feature.
  
  
  Checkout the newly created feature branch to your local machine and start building your code and directory structure
Create a directory and name it playbooks – it will be used to store all your playbook files.
Create a directory and name it inventory – it will be used to keep your hosts organised.
Within the playbooks folder, create your first playbook, and name it common.yml
Within the inventory folder, create an inventory file (.yml) for each environment (Development, Staging Testing and Production) dev, staging, uat, and prod respectively.
  
  
 # Set up an Ansible Inventory
An Ansible inventory file defines the hosts and groups of hosts upon which commands, modules, and tasks in a playbook operate. Since our intention is to execute Linux commands on remote hosts, and ensure that it is the intended configuration on a particular server that occurs. It is important to have a way to organize our hosts in such an Inventory.

Save below inventory structure in the inventory/dev file to start configuring your development servers. Ensure to replace the IP addresses according to your own setup.
  
  ![text5](https://user-images.githubusercontent.com/108102087/197803576-cc3c81e8-07f0-4e6e-88d6-118e4e5eac9b.PNG)
  
  
I was able to ssh from the ansible-jenkins server to the load balancer and NFS server
  
  ![text6](https://user-images.githubusercontent.com/108102087/197806137-38cff41c-00e4-44d1-b515-6837233d0eeb.PNG)
  
  Update your inventory/dev.yml file with this snippet of code
  
  ![text7](https://user-images.githubusercontent.com/108102087/197808446-37d6713e-400c-42f0-b4ae-a701a20046f1.PNG)
  
   # Create a Common Playbook
It is time to start giving Ansible the instructions on what you needs to be performed on all servers listed in inventory/dev.

In common.yml playbook you will write configuration for repeatable, re-usable, and multi-machine tasks that is common to systems within the infrastructure.

Update your playbooks/common.yml file
  
  Update GIT with the latest code
Now all of your directories and files live on your machine and you need to push changes made locally to GitHub.

In the real world, you will be working within a team of other DevOps engineers and developers. It is important to learn how to collaborate with help of GIT. In many organisations there is a development rule that do not allow to deploy any code before it has been reviewed by an extra pair of eyes – it is also called "Four eyes principle".

Now you have a separate branch, you will need to know how to raise a Pull Request (PR), get your branch peer reviewed and merged to the master branch.
  
  ![text8](https://user-images.githubusercontent.com/108102087/197814197-107f3112-b16b-4f48-9887-aacc1cc7c5db.PNG)
  
  ![text9](https://user-images.githubusercontent.com/108102087/197815792-4c72a0d3-b395-42f1-8799-c5d2ebee27ca.PNG)
  
  # Run first Ansible test
Now, it is time to execute ansible-playbook command and verify if your playbook actually works
  
  ![text10](https://user-images.githubusercontent.com/108102087/197862648-f4f3fd14-4072-4939-955d-b0fa4154d59f.PNG)
  
  I go to each of the servers and check if wireshark has been installed by running
  
  ![text11](https://user-images.githubusercontent.com/108102087/197863080-c512869d-f449-4621-8016-3d73d954a713.PNG)
  
  ![image](https://user-images.githubusercontent.com/108102087/197864492-574be008-da78-40a1-9f58-cf260302ee52.png)
