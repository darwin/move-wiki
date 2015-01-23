# GitHub wiki migration or backup

I needed to move all wiki pages between two repos. 

## Tasks

* pull_wiki - download wiki files from selected github repo to disk
* push_wiki - upload wiki files from disk to selected github repo

## Install

    git clone git://github.com/darwin/move-wiki.git
    cd move-wiki
    git submodule init
    git submodule update

## Prerequisities

Tell me who you are. Set your GitHub credentials into global git config (see [account](/account) page):

    git config --global github.user darwin
    git config --global github.token fffffffffffffffffffffffffffc122c
    
## Pull

    rake pull_wiki user=defunkt repo=grit dest=some/dir

## Push

    rake push_wiki user=mojombo repo=grit source=some/dir
    
## Alternate method (does not use move-wiki)

First create a blank wiki in the `mojombo/grit` repo via Github.com, then:

    git clone git@github.com:defunkt/grit.wiki.git
    cd grit
    git remote add new git@github.com:mojombo/grit.wiki.git
    git pull new
    [merge conflicts and commit]
    git push new master
    
