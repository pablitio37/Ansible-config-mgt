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
