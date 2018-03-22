# My Wholesome Blog
###### by bishwin

## Steps
1. `git clone https://github.com/Bishwin/selftitled.git`
1. `mkvirtualenv wholesome`
1. `pip install -r requirements`
1. run with `make devserver`
1. stop with `make stopserver`


## Making Posts

###### with python 2 or 3

Use handy dandy script `make_entry.py` to create posts

`python make_entry.py "My_Wholesome_Post_Name"`

###### with python 2 (untested with python 3)

This project uses `Fabric` to automate some tedious tasks.
  
To create a new post with `Fabric` do:
  
`fab make_entry:"New Post"`

To add your own custom method to use with Fabric:
1. editing `fabfile.py`
1. add method
1. use method with `fab your_method_name: <your_args>`


## Editing a post  
`Status: draft` moves content to drafts and isn't visible on homepage  
`Status: published` sets a post visible and appears on homepage   

## Hosting with github pages

using `ghp-import` we can push the `Pelican` generated output directory to a github repo.  
change to your repo details and run the following:
```
ghp-import output
git push git@github.com:<username>/<username>.github.io.git gh-pages:master
```

your site should be up on githubpages

### Automating deploying to github

y'all need to edit `fabfile.py` with your github repo details.

1. open `fabfile.py`
1. edit line `143` to the repo you used above
1. `fab github` to push
