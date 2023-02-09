---
title: "How to setup your blog free of cost with hugo"
date: 2023-02-02T21:30:07+05:30
draft: false
tags : ["hugo","blog"]
categories : ["tech"]
---
Just want to give a brief gist of how I made the website.I use github pages for hosting and used hugo to generate webpages from mark down file.You can also use other hosting sites like netlify but I just did want to pay for a domain name currently or have netlify in my url. So decided settled with the `github.io` url. To host a site you need to create a repository in github with the name `"username".github.io`. eg. if your github username is `basildoesstuff`you should create a repository named `basildoesstuff.github.io` 

## Setting things up🧑‍💻

You need to install git, go and hugo in your local environment .
To generate a hugo project use
```
hugo new site "SiteProjectName"
```
You need a theme now. we are gonna use PaperMod theme your can just go to the `themes`  directory and clone the theme git repository inside it. So for our case 
```
git clone https://github.com/adityatelange/hugo-PaperMod.git
```

To create a blog page use
```
hugo new posts/firstpost.md
```
This command would create a new directory `posts` and create a markdownfile with name `firstpost`. 

## Editing the markdown📝


You can get a basics of editing markdown from this [link](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax). To set up the menu option go to the `config.yaml` and the following properties.
```
menu:
    main:
        -identifier: Categories
         name: Categories
         url: /Categories/
         weight: 10
        
        -identifier: Tags
         name: Tags
         url: /Tags/
         weight: 10

        -identifier: Archives
         name: Archives
         url: /Archives/
         weight: 10
```
To generate the html once you are done with the markdown changes is to run the following command
```
hugo -t "theme-name"
```
where theme name is the name of the repo that you cloned in the themes directory.
The html and static assets will be generated in the public directory and pushing the public