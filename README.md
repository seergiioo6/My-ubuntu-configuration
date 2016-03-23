My Ubuntu Configuration
=========

Basic Aplications
----

<pre>
sudo apt-get install -y curl vim vim-gnome
</pre>

Git
----

<pre>

sudo apt-get update
sudo apt-get install git	
sudo add-apt-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install git
</pre>

Here are my favorite Git aliases:

<pre>
git config --global alias.s 'status -s'
git config --global alias.log 'log --all --graph --oneline --decorate'
git config --global alias.l 'log --all --graph --oneline --decorate'
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit" # pretty format log
git config --global alias.b 'branch -vv'
git config --global alias.fp 'fetch --prune'
</pre>

Git - Gnome keyring integration:

Reference: http://stackoverflow.com/questions/13385690/how-to-use-git-with-gnome-keyring-integration

<pre>
sudo apt-get install libgnome-keyring-dev
cd /usr/share/doc/git/contrib/credential/gnome-keyring
sudo make
git config --global credential.helper /usr/share/doc/git/contrib/credential/gnome-keyring/git-credential-gnome-keyring
</pre>

Links to Good Git Documentation:

* [Well written commits guide](https://github.com/alphagov/styleguides/blob/master/git.md)
* [Contributing / Signing your work guide](https://github.com/docker/fig/blob/master/CONTRIBUTING.md)

oh-my-zsh
----

Reference: https://github.com/robbyrussell/oh-my-zsh

Install:

<pre>
sudo apt-get install zsh
curl -L https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh | sh

</pre>

Aliases:
<pre>
alias cl="clear"
alias s="subl"
export ANDROID_HOME="/opt/android-sdk"
export PATH=${PATH}:$ANDROID_HOME/tools:$ANDROID_HOME/platform-tools
export PATH=$HOME/.node/bin:$PATH	
</pre>


Node JS
----

Install latest version of Nodejs from: https://nodejs.org/en/ 

NPM
----

<pre>
sudo apt-get install npm	

</pre>

RVM
---

Execute as root (to install it globally):

<pre>
curl -L https://get.rvm.io | bash -s stable --ruby
</pre>

Puppet
----

<pre>
wget http://apt.puppetlabs.com/puppetlabs-release-precise.deb; dpkg -i puppetlabs-release-precise.deb
apt-get update
apt-get install -y puppet
</pre>

Oh-my-zsh
----

<pre>
wget --no-check-certificate https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
</pre>

XBMC
-----

<pre>
sudo apt-get install python-software-properties pkg-config
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:team-xbmc/ppa
sudo apt-get update
sudo apt-get install xbmc
</pre>

Synapse
----

See: http://www.noobslab.com/2013/06/indicator-synapse-alternative-of-mac.html

<pre>
sudo add-apt-repository ppa:noobslab/apps
sudo apt-get update
sudo apt-get install indicator-synapse
</pre>

Google Chrome
-----

<pre>
sudo apt-get install -y libxss1
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome*.deb
</pre>

Spotify
-----

<pre>
sudo sh -c "echo deb http://repository.spotify.com stable non-free > /etc/apt/sources.list.d/spotify.list"
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 94558F59
sudo apt-get update
sudo apt-get install -y spotify-client
</pre>

Sublime Text 3
-----

<pre>
sudo add-apt-repository ppa:webupd8team/sublime-text-3
sudo apt-get update
sudo apt-get install sublime-text-installer
</pre>
Install Package Installer:
<pre>
import urllib.request,os,hashlib; h = '2915d1851351e5ee549c20394736b442' + '8bc59f460fa1548d1514676163dafc88'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)	
</pre>

Plugins:
<ul>
	<li>Brogrammer Theme</li>
	<li>HTML Beauty</li>
	<li>SFTP</li>
	<li>Babel</li>
	<li>Normalize Identation</li>
	<li>...</li>
</ul>



To create unity launcher create `/usr/share/applications/sublime.desktop`

<pre>
[Desktop Entry]
Name=Sublime Text 2
Comment=Best text editor ;)
Exec=/opt/Sublime\ Text\ 2/sublime_text
Icon=/opt/Sublime\ Text\ 2/Icon/128x128/sublime_text.png
Terminal=false
Type=Application
StartupNotify=true
Version=1.0
</pre>

*Indent on Save*

* Install Package: https://packagecontrol.io/packages/Reindent%20on%20save



Dropbox
-----

<pre>
cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86_64" | tar xzf -
</pre>

Maven
----

<pre>
wget http://apache.rediris.es/maven/maven-3/3.1.1/binaries/apache-maven-3.1.1-bin.tar.gz
tar -zxvf apache-maven-3.1.1-bin.tar.gz
sudo mv apache-maven-3.1.1 /opt/
sudo chown root:root /opt/apache-maven-3.1.1/ -R
echo "PATH=$PATH:/opt/apache-maven-3.1.1/bin/" > /etc/profile.d/mvn.sh
</pre>

[Maven Colorizer](https://github.com/builddoctor/maven-antsy-color)

<pre>
curl https://raw.github.com/builddoctor/maven-antsy-color/master/mvn >> ~/.bash_aliases
</pre>

Java JDK
----

<pre>
sudo apt-get install openjdk-6-jdk
</pre>

Remote Desktop Sharing (for HTPC)
----

Reference: http://askubuntu.com/questions/25189/remote-login-with-graphical-display-manager-gdm-lightdm

This provides a way to share desktop remotely (not the same as remote login). Useful for HTPC remote control.

Prepare Server:
<pre>
sudo apt-get install x11vnc
sudo x11vnc -forever -auth /var/lib/lightdm/.Xauthority -display :0
</pre>

Connect Client:
<pre>
vncviewer -via htpc localhost:0
</pre>

(Where htpc is the ssh connection configured at @~/.ssh/config@)

Disable Apport
----

Reference: http://www.techdrivein.com/2012/08/how-to-disable-system-program-problem.html

edit /etc/default/apport:
<pre>
enabled=0
</pre>

Samba Client
---

In order to be able to mount samba on filesystem:

<pre>
sudo apt-get install -y cifs-utils
</pre>

Then to mount do:

<pre>
mount -t cifs //sc/docs /media/sc/docs -o username=dimitris
</pre>

Whiteboard cleaner
---

https://gist.github.com/lelandbatey/8677901

<pre>
#!/bin/bash
convert "$1" -morphology Convolve DoG:15,100,0 -negate -normalize -blur 0x1 -channel RBG -level 60%,91%,0.1 "$2"
</pre>

Ubuntu Eyecandy (Themes, Icons, Wallpapers)
---

See: http://mokaproject.com/

Plank: http://wiki.go-docky.com/index.php?title=Plank:Installing

Wallpapers: http://wallpaperswide.com/

Terminal Recording
---

* https://github.com/icholy/ttygif

Credential Generation
----

To create on terminal a random credential:

```
cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 64 | sed 1q
```

Other Apps
----------

* Skype
* GIMP
* Filezilla
* Emma
* Team Speak 3 Client
* Libre Office
* Eclipse




