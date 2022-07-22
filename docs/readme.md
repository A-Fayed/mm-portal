## General Note 

This PoC (Proof of Concept) is intended to test:
1. The viability and appeal of using Jekyll and Github Pages for Moata Developer Portal (MDP)
2. That basic styling and templates can be used to create a more exciting experience for those using MDP
3. Whether there is an apetite for this type of product (so we can put more resource into taking it further)

## Useful Links 

1. [Installing-Jekyll]: https://jekyllrb.com/docs/installation/ //
2. [Jekyll-Git-Documentation]: https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll //
3. [Figma]: https://www.figma.com/file/gMfCqV7jrn49e9aRSOQVdF/Moata-Developer-Portal?node-id=36%3A249 // Designs for this PoC, and ideas for future iterations can be found here 

## Setting up the PoC & testing locally

1. Unzip the file and rename 'current-MM-project'
2. Open a new terminal 
3. Navigate to 'current-MM-project' in the terminal
4. From the directory 'current-MM-project' change into the 'docs' folder
5. Run `bundle install`
6. Run `bundle exec jekyll serve`
7. Open relevant server address in browser

## Check PoC is working online 

1. Run `git init` from 'current-MM-project' repository
2. Create a remote git repository called 'current-MM-project' 
3. Use `git remote add origin` to link to the newly created remote repository 
4. Use `git add .` `git commmit -m "message"` and `git push` to add files to remote repository 
5. From the remote git repository, click 'Settings'
6. Click 'Pages' on the left hand sidebar 
7. Choose 'master' branch and 'docs' under 'Source' 
8. Visit the published link

## Adding a new .md file 

1. Navigate to current-MM-project/docs/_posts/ in Github
2. Upload or create a new .md file using 'Add file' button 
3. Name the new post in the format YYYY-MM-DD-NAME-OF-POST.md
4. Add the following YAML frontmatter to the top of the file (you can choose from the categories 'Ideas' 'Ui-UX' 'Design' 'Example' and 'Case Studies')

```layout: post  
title:  "Example Title"  
date:   2022-07-14 11:23:21 +0100  
categories: [Ideas]  
image: post-image.png  
description: Lorem ipsum dolor sit amet
```

5. Below the frontmatter, add content for your post.
6. At the bottom of the page, type a short, meaningful commit message that describes the change you made to the file.
7. Click Commit New File

## Upload images to reference in a new .md file

1. Navigate to current-MM-project/docs/assets/images/
2. Upload image using 'Add file' button
3. In the new .md post reference the image in the format `![Image Description]({{site.baseurl}}/assets/images/async-py.png "Image Description")`

## Activities Backlog 

Feel free to add to this list of simple backlog of activities 

1. Think through how we are storing new markdown files and images so they are maintainable on Github
2. Make the proof of concept more intuitive by adding smaller details like retain scroll position, media queries
3. Tidy up CSS so that it is more robust if PoC gains more momentum 
4. Code review - ensuring whatever has been developed is using latest standards/methods
5. Proficiency rating and associated linking
6. Pagination
7. Content from right hand side
8. Feedback from early adopters