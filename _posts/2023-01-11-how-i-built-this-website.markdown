---
layout: post
title:  "How I built this website"
date:   2023-01-11 20:25:51 +0100
categories: jekyll
---
I built this website using `GitHub Pages` and `Jekyll`. 

# The solution that works

## Step 1: Creating a GitHub repository

The repository name needs to be `<user>.github.io` or `<organization>.github.io`. So I named the new repository `xuechanma.github.io`.

## Step 2: Cloning the repository to a local folder

I used `GitHub Desktop` to clone the above repository to a designated local folder on the laptop. It was very simple. 

## Step 3: Creating a Jekyll site

In `Terminal`, run command line:
{% highlight ruby %}
cd REPOSITORY-NAME  ## Changes the working directory
git checkout --orphan gh-pages  ## Creates a new branch called gh-pages, and switches to the gh-pages branch
jekyll new --skip-bundle .  ## Creates a Jekyll site in the current directory
{% endhighlight %}

From the local folder, open the Gemfile that `Jekyll` created:
- Add "#" to the beginning of the line that starts with gem "jekyll" to comment out this line.
- Add the `github-pages` gem by editing the line starting with `# gem "github-pages"`. Change this line to:
{% highlight ruby %}
gem "github-pages", "~> 227", group: :jekyll_plugins # The number "227" is copied from https://pages.github.com/versions/.
{% endhighlight %}

Save and close the Gemfile.

In `Terminal`, run command line:
{% highlight ruby %}
bundle install
{% endhighlight %}

After that, I used `GitHub Desktop` to stage, commit and push the above changes to GitHub. At this point, I could see that the website is live: https://xuechanma.github.io/.

## Step 4: Editting the `_config.yml` file

From the local folder, open the `_config.yml` file, and make necessary edits, for example, in my case:
{% highlight ruby %}
baseurl: "" ## the subpath of your site, e.g. /blog. I left it empty.
{% endhighlight %}

Then I used `GitHub Desktop` to stage, commit and push the changes to GitHub.

## Step 5: Generating a test site locally with Jekyll

In `Terminal`, run command line:
{% highlight ruby %}
bundle install
bundle exec jekyll serve
{% endhighlight %}

To preview the site, in the web browser, navigate to the `Server address` indicated in the `Terminal`: something like http://LOCALHOST:4000.


# Things that did not work
- I wanted to use the `al-folio` theme but I tried several times, and the pages build and deployment always failed. 
- I had to switch to `Ruby version 3.1.3`. Problem kept occuring when I used `Ruby version 3.2.0`.


# Useful links

[About GitHub Pages and Jekyll]: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll

