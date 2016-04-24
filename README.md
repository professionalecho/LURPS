# LURPS
The website for the Lancaster University Roleplaying Society. This website uses [Jekyll](http://jekyllrb.com/) and [Bootstrap](http://www.getbootstrap.com) to make cool stuff happen, and make it super easy for Webmasters future to change stuff.

## Getting Up & Running

To start up you'll need to install a few things. The first is Ruby, and its associated DevKit. You can find both of those [here](http://rubyinstaller.org/downloads/). I used version 2.2.4. When installing the DevKit, put it somewhere like `C:\RubyDevKit`. Then, once you've installed both of those, open a command terminal and navigate to the DevKit folder by typing `cd C:\RubyDevKit`. Then, type `ruby dk.rb init` to configure Ruby, and finally `ruby dk.rb install` to install it!

Once Ruby is installed, it's a piece of cake to install Jekyll. Literally all you need to type is `gem install jekyll`, and it'll start! You'll need access to the files in this repository by requesting a pull, and then using a program like [GitHub Desktop](https://desktop.github.com/) (not the popular choice, but the easiest and friendliest by far) to be able to use the repository.

Using the command terminal, navigate to the repository (`cd C:\Users\[username]\Documents\GitHub\LURPS` by default), and run Jekyll by typing `jekyll serve`. You'll then be able to point your browser at `http://localhost:4000/` to see changes as you make them!

## Making Changes

In the root of the LURPS folder are the pages you'll mostly be using. The front page is `index.html`, everything else is as named in the live site. Some are Markdown, some are HTML, but it all works under Jekyll. What's happening here is that the "background" information that lays out the site (structuring, styles, meta-information etc.) has been put into the `_layouts` folder so you can focus on the content. The information at the top of each page (the stuff between three dashes) is key information that the service uses to build up the site. Here's what each of them mean, using the 'Find Us' page as an example:

* **title: Find Us**: This is the title of the page. It's displayed in the browser (before the society name) and is used to name the banner image for that page. For that reason never include special characters in the title field.
* **layout: default**: The default layout is the only layout, so this should never change.
* **slogan: LURPS is based...**: This appears in the white box over the banner (or as the first line on mobiles).
* **credit: Christian Cable**: The name of the person who provided the banner image. Always make sure you credit the person!
* **flickr: 5JViQt** The Flickr ID of the banner image. Find this by clicking "Share" on the Flickr image page and taking the six-character code. You then need to save the image to the `css/banners/` folder, naming it after your title with hyphens replacing spaces (so this one is called `find-us.jpg`).
* **group: navigation**: If you want the page to appear at the top navigation bar, include this. Otherwise, take it out.

In addition, the `index.html` page and the `exec.html` page have more arguments in this section. The `exec.html` ones are just the names of the exec, and providing that information will automatically fill in the rest of the page. In the `css/exec-photos/` folder, put pictures of each member following the same naming conventions as the banners (so Patrick Lickman becomes `patrick-lickman.jpeg`) and it should be good to go. The `index.html` ones all refer to key information displayed on the front page, with descriptive tags explaining what they should say. This provides a fast way to update often-changing information such as the next social.

## Committing Changes, and Really Committing Them

Once you're happy with the site, use GitHub to commit the changes to here. Then, with your Webmaster Powers, connect to the LURPS webspace (via the [university's VPN](http://lancasteranswers.lancs.ac.uk/portal/app/portlets/results/viewsolution.jsp?solutionid=111025142706591&isguest=true)), take the entire contents of the (hopefully hitherto untouched) `_site` folder and put them in there. You may get a lot of notifications about replacing files, because you're updating every single one of them. It should be fine.

If it isn't fine, you can always download an older version of the site from here to try again. And if it is extremely un-fine, let me know, and I'll see what I can do.

## Tips

If you link to anywhere on the site, use the code `{{ site.baseurl }}`. This means www.lurps.co.uk, so for example if you're trying to access the stylesheet type `"{{ site.baseurl }}/css/style.css"`. This will then correctly render both on the local host and on the live site, without you having to change it between.

Try not to change much in `_layouts/default.html`, as that's where much of the secret code hides.
