---
layout:     post
title:      "Transfer Ubuntu"
subtitle:   "My installed software - and configurations"
date:       2016-08-20
author:     "Adam"
header-img: "img/Bit_Rain.jpg"
tags:		[Ubuntu | Fedora | Arch/Antergos]
---
This is for my own purposes - my preferred build/setup.

<h1><center> Initial configuration </center></h1>

After a clean install of Ubuntu 16.04 GNOME:

Reboot to ensure proper startup-sequence.

<h3>Install <b>Tilda</b> drop-down terminal:</h3>

```.sh
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install tilda
```
Customize to liking:
Text Color -> #829496
Background Color -> #002B36
Set "open tilda" to 1/2-button. Set <b>Tilda</b> to run on startup in Startup Applications 

<br>

<h3> Configure Gnome extensions: </h3>
<ul style="list-style-type:circle">
 <li><h4> Alt tab lift first window  </h4></li>½
 <li><h4> Applications menu </h4></li>
 <li><h4> Caffeine </h4></li>
 <li><h4> Dash to dock </h4></li>
 <li><h4> Gradient Top Bar </h4></li>
 <li><h4> Freon </h4></li>
 <li><h4> Laine </h4></li>
 <li><h4> Removable Drive Menu</h4></li>
 <li><h4> User themes</h4></li>
 <li><h4> NetSpeed</h4></li>
 <li><h4> Workspace Indicator</h4></li>
</ul>

<h3> Configure settings (gnome-tweak-tool): </h3>
Appearance: Global Dark Theme <ON>
Top bar: Show date
Windows: Minimize <ON>
Workspaces: Static -> 2

<h3> Styling</h3>
<br>
<ul style="list-style-type:circle">
 <li><h4> Paper Theme </h4></li>
</ul>
```.sh
sudo add-apt-repository ppa:snwh/pulp
sudo apt-get update
sudo apt-get install paper-icon-theme && sudo apt-get install paper-gtk-theme && sudo apt-get install paper-cursor-theme
```

<h3><center> Applications</center></h3>

<h4> Text </h4>h4>
```.sh
# Latex
sudo apt-get install texlive-full
sudo apt-get install texmaker
# Sublime 3
sudo apt-add-repository -y ppa:webupd8team/sublime-text-3
sudo apt-get update && sudo apt-get install sublime-text
```
<h4> Version Control </h4>
```.sh
sudo apt-get install git
``` 
Download [Gitkraken](https://www.gitkraken.com/download)

<h4> Browser </h4>
```.sh
sudo apt-get install chromium-browser
```

<h4> R & Rstudio </h4>
```.sh
sudo apt-get install r-base
```
Download and install [Rstudio](https://www.rstudio.com/products/rstudio/download3/)

<h4> Ruby </h4>
```.sh
sudo apt-get update
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
rbenv install 2.3.1
rbenv global 2.3.1
ruby -v
gem install bundler
```
<h4> Emacs setup </h4>
```.sh
sudo apt-get install emacs
```

Open GUI: 
M-x customize-group -> package
--> package archives --> INS --> (Archive Name : melpa, URL : https://melpa.org/packages/) --> Apply and save.
M-x list-packages

I get: fsharpmode + flatland

<h4> F# </h4>
```.sh
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 3FA7E0328081BFF6A14DA29AA6A19B38D3D831EF
echo "deb http://download.mono-project.com/repo/debian wheezy main" | sudo tee /etc/apt/sources.list.d/mono-xamarin.list
sudo apt-get update
 sudo apt-get install mono-complete fsharp
```

<h4> Python </h4>
Make sure, that Python 3.5 is installed:
```
python3 --version
sudo apt install python3-pip
sudo pip3 install --upgrade pip
pip3 install matplotlib pandas scikit-learn folium numpy jupyter seaborn ggplot d3py plotly csvkit sqlite3
``` 

<h4> Spotify </h4>
```.sh
sudo apt-add-repository -y "deb http://repository.spotify.com stable non-free"
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys D2C19886
sudo apt-get update
sudo apt-get install spotify-client
```



















