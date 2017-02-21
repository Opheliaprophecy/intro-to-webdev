# Github Setup

Github is essentially a social network for users of git. Most of the worlds open source projects are hosted on github. It is important to note that git is not github. Github uses a collection git repositories to create a social network where users can collaborate on projects. It is totally free for any public project and costs a fee if you want your code to be private

Sign up: [https://github.com](https://github.com)

## Set credentials

You need to set your github credentials as your default credentials for your local copy of git.

Run these two commands replacing `YOUR-USERNAME` with your github username and `YOUR-EMAIL-ADDRESS` with the e-mail address you used to register for github.

```
git config --global user.name "YOUR-USERNAME"
git config --global user.email YOUR-EMAIL-ADDRESS
```
## Create SSH Key

An ssh key serves a similar function as a password. It allows you to securely connect to a remote server and is used to prove who you are.

An ssh key consists of pieces a public and a private key. Anything encrypted using the public key (which you can openly share with others) can only be decrypted using the private key (which you should keep secret). For the purpose of github we generate a public and private key and upload the public key to github. When you try to connect the encrypt a message using the public key which only you can view (Because you're the only one with the matching private key). This is all possible because of magic ([aka math](http://www.onebigfluke.com/2013/11/public-key-crypto-math-explained.html)).

**Create an ssh key.** Open git bash and type `ssh-keygen`. You will see several prompts for now you can just hit enter for each to use the default values all the way through.

To check the key was created successfully type `ls ~/.ssh` this will list the files in your `.ssh` directory. The `~` is a shortcut for your home directory aka `C:\Users\[yourname]`. The `.ssh` is a directory in your home directory which is the default location to store ssh keys. You should see two files `id_rsa` (private key) and `id_rsa.pub` (public key).

## Register your SSH key with github

* Go to github: [https://github.com](https://github.com)
* [User pic - top right corner] > Settings > SSH and GPG keys
* Click `New SSH Key`
* Open git bash and type `cat ~/.ssh/id_rsa.pub | clip` - this puts the contents of your public key file into your clipboard
* Back on github
    * paste (CTRL+V) in the `Key` field
    * type whatever you want in the `title` field (this key is unique to this computer so name it something so you know which computer this key belongs to)
    * click `Add SSH Key`
    * It should appear in the list after it saves

## Test your connection

* Run `ssh -T git@github.com`
* You will get a prompt about the authenticity of the host. This is because this is the first time you've connected. You should never see this prompt again (type yes)
* After that you should see a message saying you've successfully authenticated.

See also: [Guide on github](https://help.github.com/articles/testing-your-ssh-connection/#platform-windows)

## Fork / clone your first repo

* Go to this repo on github: [https://github.com/itslenny/intro-to-webdev](https://github.com/itslenny/intro-to-webdev)
* Click `fork` (top right corner). This will create a fork of the repo which is a complete duplicate of this repository exactly as it stands today. Any updates to the source repo (commonly called `upstream`) will not effect the fork, but you can manually pull from the source repo this is commonly called "pulling from upstream", and is a common practice when working on open source projects.
* Click `clone and download`
* Click the copy to clipboard button (right of the url field)
* Open git bash and type `git clone CLONE_URL` (replace `CLONE_URL` with the url you copied)
* Press enter and a new directory will be created
* Move into that directory by typing `cd DIRETORY_NAME`
* Run `code .` to open the folder in VS Code
* Look at the files and get a feel for markdown. This is a simple language used in readme files on github among other places.

