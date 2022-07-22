### Setting up 

## Setting up MDP proof of concept

1. Unzip file and rename 'current-MM-project'
2. Open a new terminal 
3. Navigate to 'current-MM-project' in the terminal
4. Run `git init`
5. Create a remote git repository called 'current-MM-project' 
6. Use `git remote add origin` to link to the newly created remote repository 
7. Use `git add .`, `git commmit -m "message"` and `git push` to add files to remote repository 

## Test locally 

1. From the directory 'current-MM-project' change into the 'docs' folder
2. Run `bundle install`
3. Run `bundle exec jekyll serve`
4. Open relevant server address in browser

## Check repository is working online 

1. From the remote git repository, click 'Settings'
2. Click 'Pages' on the left hand sidebar 
3. Choose 'master' branch and 'docs' under 'Source' 
4. Visit the published proof of concept at the link provided. 

## Adding a new .md file 

1. Navigate to current-MM-project/docs/_posts/
2. Upload or create a new .md file using 'Add file' button 
3. Name the new post in the format YYYY-MM-DD-NAME-OF-POST.md
4. Add the following YAML frontmatter to the top of the file

`layout: post
title:  "Example Title"
date:   2022-07-14 11:23:21 +0100
categories: [Ideas]
image: post-image.png
description: Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco`

5. Below the frontmatter, add content for your post.
6. At the bottom of the page, type a short, meaningful commit message that describes the change you made to the file.
7. Click Commit New File

## Upload images to reference in a new .md file

1. Navigate to current-MM-project/docs/assets/images/
2. Upload image using 'Add file' button
3. In the new .md post reference the image in the format ![Image Description]({{site.baseurl}}/assets/images/async-py.png "Image Description")

## Activities Backlog 

1. Can we better maintain images and posts?
2. Can we set up mobile compatability if PoC gains momentum
3. Can we tidy up CSS so that it is more robust if PoC gains more momentum 