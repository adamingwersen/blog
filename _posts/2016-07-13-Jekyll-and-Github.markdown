---
layout:     post
title:      "Qucik and Free: Create a blog"
subtitle:   "With Jekyll and Github Pages"
date:       2016-07-12
author:     "Adam"
header-img: "img/post-bg-01.jpg"
---

<center><h3> What are we doing? </h3></center>

This guide covers all the necessary steps for launching a blog within 20 minutes on any UNIX-based system. A prerequisite is, that you're somewhat familiar with git and a terminal. You will also need a [Github](https://github.com) account. 

Having watched a few confusing videos on youtube and reading blogposts that did not solve my particular issues with this setup, i decided to do a compliation of the lessons i learned. 

I'm doing this on a machine running ARCH-linux, where the process for installing ruby relies on the package-manager (pacman) - if you're on Mac/Ubuntu etc. you just have to make sure that you have git and ruby installed with a bundler - and you should not execute this code:

```.sh
sudo pacman -S ruby
sudo pacman -S git
```

Regarding ruby gems. I followed the approach for defining the correct directories as proposed on the [Archlinux Wiki for Ruby](https://wiki.archlinux.org/index.php/ruby). This should not be necessary on most other operating systems, as the defaults are sufficient. 

<center><h3> Deploy the Jekyll </h3></center>

You should install the jekyll gem and go to your desired directory - you should not create a folder for explicitly for this - Jekyll will create a folder named `yourblog`. 

```.sh
gem install
gem install jekyll
cd ~/yourdir
jekyll new yourblog
```

At this point you already have a functioning framework for a blog:

```.sh
jekyll serve
```

Simply go to the Server Adress - and there you go. You can take a look into the folder that was created using any decent [text-editor](https://www.sublimetext.com/3). You should not fiddle with the `_site` folder. You can freely edit the other files to your liking.

This is not public though - that requires just a bit more work. 


<center><h3> Fix your files </h3></center>

If you want to post the site using Github-Pages, you should now do the following:

	1) Log in to Github.com 
	2) Create new repository - with the same name as `yourblog`
	3) Don't create README.md
	4) Save the shown URL for your repository somewhere 

Get back to your terminal:

```.sh
cd ~/yourdir/yourblog
nano _config.yml
```

For simplicity delete description - this seems to cause some problems with Github when posting.

From here change the field after URL: to `http://yourprofile.github.io`
Also, change the field after BaseURL: to `/yourblog`. Your  `_config.yml` should look something like this:

```yaml
title: Doing things to stuff and vice versa

email: yourmail@mail.com

baseurl: "/yourblog" # the subpath of your site, e.g. /blog
url: "http://yourprofile.github.io" # the base hostname & protocol for your site
twitter_username: yourtwitteraccount
github_username:  yourprofile

# Build settings
markdown: kramdown
```


And yes, it's `kramdown`


Let's initialize a git repo :

```.sh
cd ~/yourdir/yourblog
git init
```

Create a `README.md` file, make sure that it's in the right place using ls in your current directory. Also, check that a `.gitignore` file has been created and that it contains: `_site`, `.sass-cache`
and `.jekyll-metadata`.


```.sh
touch README.md
ls
```


<center><h3> Get up and Github </h3></center>

Now we make sure, that we're not on a master-branch, but rather a gh-pages branch. 

```.sh
cd ~/yourdir/yourblog
git checkout -b gh-pages
git status
```


Then we can simply stage, commit and push to our Github Repository.


```.sh
git add .
git commit -m 'yourcomment'
git remote add origin http://github.com/yourprofile/yourblog.git
git push --set-upstream origin gh-pages
```


The last thing to do;

Go to [Github](https://github.com) and find the repo. Check that the files are created. If so, go to `Settings > Branches` and set Default Branch to gh-pages. 

Your site shhould be up and running by now - blogposts can be added by writing a post in Markdown and adding it to the `_posts` folder and of course remember; stage, commit, push. 

<center><h3> Okay, but it looks like shit </h3></center>

From here you can check out a multititude of tutorials on how to customize layouts and css etc. I would reccomend taking a look at the [Jekyll Documentation](https://jekyllrb.com/docs/home/) - or maybe you're lazy; just copy one of the many [Jekyll Themes](http://jekyllthemes.org/) and fit to your liking.

You can clone the repos directly or do a bit of copy/paste into your existing files.


<center><h3> Not satisfied? </h3></center>

Simply type www.google.com in to your web-browser. 