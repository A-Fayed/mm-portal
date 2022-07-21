Development occurs on 'development' branch
- git checkout development

Push to 'master' by rebasing development
- save changes to development branch
- git checkout master
- git rebase development
- git push
- then go back to development `git checkout development`