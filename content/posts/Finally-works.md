+++
title = "Finally Works"
date = 2018-03-16T23:48:28-05:00
tags = [
    "hugo",
    "netlify",
]
categories = [""]
draft = false
+++

This is the first time I try to set up a blog.
I have to say it is so hard.

The framework I choosed Hugo, it is good, at least for now.
The real problem is about hosting. Though Hugo gives several ways to host the blog, it turns out to be very difficult.

For hosting server I first used VM from Google cloud platform, but I met some really confusing issues about deploying the blog. Hugo uses Rsync to deploy the website, but the server from google keeps refusing by saying that there was a "permission denied (public key)" error. Though I did some research on SSH, private and public keys, at last nothing works so I have to abandon that.

Then I transfer to Netlify. At first there is a tons of buiding errors poping up, so I have to go through everything I have done to debug.

The first error is about the theme issue. Netlify reads from Github repos, try to clone the repo and bulid it. At first the blog works locally but it cannot find theme documents. I skim through everything and I find out that Git does not trace documents inside the "theme" directory.

The reason is that Hugo download theme by cloning repos from Github, and for that reason, the theme itself is already a repo, it could not be included in our repo!

OK, that's why the offical Hugo document suggest us to use "git submodule" on themes for Netlify. I tried several time, but nope, "git submodule" does not work at all. So I have to delete the ".git" file inside the theme directory, thus combine two repo into one, and it works!

But new problem arises, I get a new error code 255. According to the debuging page, it is a known bug when Nelify have different Hugo version than you. You need to add a configuration called "HUGO_VERSION" and set it to the version of your Hugo.

Then the most magical thing happens, I check the version number of Hugo on my Windows 10 machine, it says 0.37, I enter that information, and I still get the 255 error.

Well, interesting.

I think about a lot of posibilities and at last I choose to upgrade my Hugo version. I have work with Hugo on Linux before and I knew the lastest version is "0.37.1". I go to the release page of Hugo on Github, and find the download for Hugo 0.37.1 there. I figure out how to "install" that, it is only replacing the hugo.exe file under something like "programData/choco/bin" directory.

And Bang! Finally it works!

Later about customizing domain does not take much time, theres no bugs appearing, everything just work as expected as I changed the DNS server for my domain. The only thing is that it really takes a while to refect the changes in DNS.

Anyway, cheers for finishing this goal! The next thing I may need to configure this blog and try to learn some Markdown.