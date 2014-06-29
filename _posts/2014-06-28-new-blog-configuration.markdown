---
layout: post
title:  "New Blog Configuration"
date:   2014-06-28 23:57:17
categories: jekyll github
---

**Goal:** Setup second blog using Github Pages, Jekyll and a custom domain.

**Progress:** Completed, one day

I've set up a number of personal websites and blogs over the years, but it seems that each time I do things a little bit differently. I moved on from wordpress at the beginning of the year for the simpler pastures of [Github Pages](https://pages.github.com/) and [Jekyll](http://jekyllrb.com/). Using my text editor to write my posts allows me to focus more on writing and less on all the other "stuff" that comes along with platforms like Wordpress. Pushing to Github is quick and easy, and also means everything you write is automatically backed up. And best of all, if you're using a public repo it's free. I'm slowly weaning myself off of paid hosting and finding it to be a much smoother experience.

**GitHub Project Pages**

Migrating my first [blog](http://www.onebrokeb.com) was fairly straightforward since Github allows one User Pages site per account. I felt like it was possible to setup more than one blog, but wasn't sure of the process. So today I spent a bit of time researching the blog setup and also if there would be any domain issues before I went out and purchased my new domain. From the GitHub documentation I determined that I needed to create my second blog as a Project Pages site. After one false start with setting up the repo properly I found and followed the initial steps outlined by [Anna Debenham](http://24ways.org/2013/get-started-with-github-pages/). The unique thing about Project Page sites is that they are intended to contain project files and site files in the same repo, but in separate branches. Since I'm just plannig a standalone site I only needed the gh-pages branch in the repo. So when I got to the "Make gh-pages your default branch" part of Anna's post I used a command line prompt provided by [François Marier](http://feeding.cloud.geek.nz/posts/setting-default-git-branch-in-bare/). Then I continued through Anna's post until just after the "jekyll new" part. She continues to go over creating individual files, but once Jekyll is installed it already includes the necessary files to get started and I wanted to finish my initial setup before customizing anything. 

**Custom domain**

The last part of my initial setup was the domain. I use a different domain registrar each time, with mixed results. Today I chose to go with [Namecheap](http://www.namecheap.com) and I was pleasantly surprised by the simple process and clean interface. They didn't have ads all over the place, or try to upsell me on a million things. It was straightforward and a good price of only about $15 for the domain and they include Whois privacy at no extra cost. The final step was creating the CNAME file in my repo and changing the A records in Namecheap to point my new domain, alwaysbelearning.co to the blog. After everything was deployed and configured it seemed to only take a few minutes for the site to load on the domain. Victory!

**Next steps**

Since then I've updated the __config.yml file with my basic site info. I also wrote an about page and created my first inspirational graphic for the site using the nifty tool [Canva](http://www.canva.com), and wrote my first posts. Hopefully over the next week I'll find time to work on the site aesthics, but I really plan on doing on going experiments with the look of the site as I experiment with different front-end tools and techniques. But all in all, not bad for a day's work.

\- B