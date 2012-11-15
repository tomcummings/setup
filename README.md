#Develop With Passion® - .Net Developer BootCamp Setup

##The following setup should take between 30-90 minutes to complete depending on your skill level and familiarity with unix based environments.

##The three main programs you will be installing in this setup are:

* Ruby - please install to the default path it provides
* MingW - please install to a folder named C:\utils\mingw
* Git - please install to a folder named C:\utils\git

##Make sure you are running at least one of the following:

  * VS 2010 Professional or higher
  * VS 2012 Professional or higher

I will be running VS2012 Professional.

#Required Setup

The following is the setup that you WILL need to perform to configure all necessary prerequisites to be able to enjoy the week. If you have any questions, please do not hesitate to ask!!

##Make sure that you have configured windows to show all hidden files and folders

##Get setup at [Github](http://github.com)

* [Sign up](https://github.com/signup/free) for a free account at github.com. My recommendation is to use an all lowercase username.

##Install Ruby

* Install the latest version of Ruby from [here](http://rubyforge.org/frs/download.php/76054/rubyinstaller-1.9.3-p194.exe)
* Make sure you select the following options:
  * Add Ruby Executables to your path
  * Associate .rb and .rbw files with this Ruby installation
* Once the install has completed, verify your installation by opening up a command prompt and typing in: ruby -v. You should see:
  * ruby 1.9.3 [version and date information]

##Install Git for windows

1. Install the latest version of Git for windows from [here](http://code.google.com/p/msysgit/downloads/detail?name=Git-1.7.11-preview20120710.exe&can=2&q=)

* Configure according to the following screenshots:

![git_setup_part_1](http://github.com/deltadental2012/setup/raw/master/images/git_setup_part_1.png)
![git_setup_part_2](http://github.com/deltadental2012/setup/raw/master/images/git_setup_part_2.png)

##Setup your git ssh authentication key

1. Open up a git bash prompt
2. Enter the following command:    
   ssh-keygen -t rsa -C your_email_address  
   Accept the defaults for the remaining prompts  (leave the passphrase blank).  
3. Navigate to the folder where your ssh key was created (by default your profile folder C:\Users\your_user_name)
4. Open the file id_rsa.pub and copy the contents to the clipboard.
5. Login to your account at [github](https://github.com/login).
6. Navigate to your [ssh settings](https://github.com/account/ssh)
7. Click on the link: Add Another Public Key:
8. Give your key a title and paste the public key that is in your clipboard from step 4 into the Key text entry:

![ssh key entry](http://github.com/deltadental2012/setup/raw/master/images/add_ssh_key.png)

##Verify that your git ssh authentication works

1. Open up a git bash prompt
2. Enter the following command:
   ssh -v git@github.com

3. You may be prompted to cache the server identity (type yes)
4. If you have setup your ssh settings correctly the bottom part of the command output should look similar to the following:

![successful authentication](http://github.com/deltadental2012/setup/raw/master/images/git_authentication.png)

##Clone this setup repository

1. Open up a git bash prompt and type the following commands:
  * cd /c [enter]
  * mkdir course [enter]
  * cd course [enter]
  * git clone http://github.com/deltadental2012/setup.git [enter]

At the completion of the last command you should have a copy of this repository on your local machine.

##Update git and bash configuration details

The following steps will ensure that you have your git environment configured in the correct way for class. If you already have existing git configuration that you use on a regular basis, either make your changes manually to match the recommended settings, or create a backup of your existing configuration and restore it after the class.

Open up a git bash prompt and type in the following commands:

1. cd /c/course/setup [enter]
2. ./copy_config [enter]
3. notepad ~/.gitconfig [enter]
    * change the email and name settings under the [user] section. Save your changes
4. notepad ~/.bash_ssh [enter]
    *  If you named your keyfile diffently than the default (id_rsa), then change line 10 of this file to reflect the name of your private keyfile that you created when generating your ssh key. Save your changes.


##Fork the project repositories for the week

1. Login to your account at [github](https://github.com/login)
2. Search for the username deltadental2012: (Username in screenshot is for example purposes only)<br>![Search for deltadental2012](http://github.com/deltadental2012/setup/raw/master/images/github_search_for_develop_with_passion.png)
3. Click on the deltadental2012 user (screenshot is for example purposes only)<br>![deltadental2012 user](http://github.com/deltadental2012/setup/raw/master/images/github_developwithpassion_user.png)
4. Click on the prep repository: ![repository](http://github.com/deltadental2012/setup/raw/master/images/github_shawaugp.png)
5. Click on the fork button to create your own copy of this repository <br>![fork](http://github.com/deltadental2012/setup/raw/master/images/github_fork.png)
6. Repeat steps 2-5 for the app repository.

## Checkout your local copies of the code

1. Open up a git bash prompt and type the following commands:
  * cd /c/course [enter]
  * git clone git@github.com:[your github user name]/prep.git prep [enter]
    
    Assuming your github username is jp the command would look as follows:

    git clone git@github.com:jp/prep.git prep [enter]

  * git clone git@github.com:[your github user name]/app.git app [enter]
    
    Assuming your github username is jp the command would look as follows:

    git clone git@github.com:jp/app.git app [enter]

4. Once you have completed steps 3 and 4 your course folder should look as follows:

![checked out directory](http://github.com/20121022aprimo/setup/raw/master/images/checked_out_directory.png)

##Install Mingw

Open up a git bash prompt and type the following commands:

1. cd /c/course/setup [enter]
2. explorer . [enter]

Double click the mingw-get-inst-20111118.exe installer and install using the following screenshots:

![mingw_setup_part_1](http://github.com/deltadental2012/setup/raw/master/images/mingw_setup_part_1.png)
![mingw_setup_part_2](http://github.com/deltadental2012/setup/raw/master/images/mingw_setup_part_2.png)
![mingw_setup_part_3](http://github.com/deltadental2012/setup/raw/master/images/mingw_setup_part_3.png)
![mingw_setup_part_4](http://github.com/deltadental2012/setup/raw/master/images/mingw_setup_part_4.png)
![mingw_setup_part_5](http://github.com/deltadental2012/setup/raw/master/images/mingw_setup_part_5.png)

##Configuring MingW Paths

Open up a git bash prompt and type the following commands:

1. cd /c/course/setup [enter]
2. notepad dev_tools/mingw/profile [enter]
3. Change lines 20 and 23 so that the location of your ruby bin directory and git bin directory match up with where you installed the programs. I would strongly recommend using spaceless paths so that you won't have to fiddle around with escaping spaces. The default values of the lines are where I have installed those tools to.
4. Run the following command
   * ./copy_mingw_config [enter]

The above step copies the modified config file into the folder where you should have installed mingw (c:\utils\mingw). 

##Test Your Mingw Install

Open up a git bash prompt and type the following commands:

1. ruby -v [enter]
You should see a ruby version, if you don't see anything, you will have to repeat the Configuring MingW Paths section above, and make corrections as necessary.

2. git --version [enter] 
You should see a git version, if you don't see anything, you will have to repeat the Configuring MingW Paths section above, and make corrections as necessary.

##Install IIS Express

Install iis_express following these steps:
  1. Download from [here](http://www.microsoft.com/en-us/download/confirmation.aspx?id=1038)
  2. Run the regular installer. If you already have IIS Express - skip this step
  3. Navigate to you IIS Express install directory and copy the entire folder
  4. Paste the iis express folder into your C:\utils folder.
  5. Rename the pasted IIS Express folder to iis_express.
  6. Rerun the installer and remove the installed version of IIS Express. This will just leave your copied, registry-less version on the system.
  
##Install TestDriven .Net

* Download and install the latest student version of [TestDriven.Net](http://testdriven.net/download_release.aspx?LicenceType=Personal)


#Optional Setup

##Devtools

If you want the same environment setup that I use (including autohotkey scripts, multi platform shell scripts etc), follow along with the setup outlined here (use the MSys instructions): [devtools](http://github.com/developwithpassion/devtools)
