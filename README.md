# Jekyll VM

## What

This is a project to help you set up a [Jekyll](http://jekyllrb.com/) 
environment easily if you don't want to go through the trouble of manually 
installing it (especially on Windows), don't want to pollute your OS, for 
testing things, or whatever other reasons you might have.

The VM is using 64-bit [Ubuntu](http://www.ubuntu.com/)
[Trusty (14.04)](http://releases.ubuntu.com/14.04/). 


## What you need

You need to have the following installed:
 * [VirtualBox](https://www.virtualbox.org/)
 * [Vagrant](https://www.vagrantup.com/downloads) 
 

## How to manage the VM

Simply clone this repository, or download the ZIP (look on the right), and 
open your command prompt. Then change to the directory where the files are
 located, so e.g. if you extracted the zip to `C:\jekyllvm` you would run 
 `cd \jekyllvm`.
 
Then boot up the VM with:
```
vagrant up
```
This will download the base VM and install the latest version of Jekyll on 
it. It will likely take a couple of minutes so give it some time. The 
terminal should give you (sometimes rather technical) details on what's 
going on during that.

Once you are done with the VM, you can shut it down (frees memory and 
other resources):
```
vagrant halt
```

If you want to totally destroy the VM, freeing disk space, run:
```
vagrant destroy
```


## Communication with the VM

To access the files on your computer from the VM, place them under the 
folder with the repository contents in them, and in the VM you can access 
them from under `/vagrant`.
 
To get started, SSH into the machine (not for Windows):
```
vagrant ssh
```

Alternatively (e.g. on Windows) get your favorite SSH client (e.g. [KiTTy]
(http://www.9bis.net/kitty/)) and use it to connect to the VM. You can get 
the connection information via:
```
vagrant ssh-config
```

The username and password are both: `vagrant`


## Using Jekyll on the VM

Jekyll will be installed globally on the system, meaning that you can just 
run `jekyll` anywhere you wish.

What you probably want to do is to be able to access the files from your 
computer, e.g. with your favorite editor, so you'll want to use the shared 
`/vargant` filesystem for that.

So, first thing you'll want to do after SSH-ing in, is switch to the shared 
filesystem:
```
cd /vagrant
```

Next, you might want to start a new project:
```
jekyll new my-project-name
```

Then, go into that project and start watching it with Jekyll and rebuild it 
when anything changes:
```
cd my-project-name
jekyll build --watch
```

At some systems file change detection detection will not work unless you use:
```
jekyll build --watch --force_polling
```

Your result files will end up under `my-project-name/_site`.

That's pretty much it. Of course all Jekyll commands are available, so you 
can check the [Jekyll documentation](http://jekyllrb.com/docs/home/) for 
more information. 


# Financial support

This project has been made possible thanks to [Cocreators](https://cocreators.ee) and [Lietu](https://lietu.net). You can help us continue our open source work by supporting us on [Buy me a coffee](https://www.buymeacoffee.com/cocreators).

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/cocreators)
