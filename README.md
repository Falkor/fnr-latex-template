-*- mode: markdown; mode: auto-fill; fill-column: 80 -*-
`README.txt`

Copyright (c) 2013 [Sebastien Varrette](mailto:<Sebastien.Varrette@uni.lu>) [www](http://varrette.gforge.uni.lu)

        Time-stamp: <Mer 2013-08-21 14:32 svarrette>

--------------------
# afr-latex-template

LaTeX-based templates for submission of project/AFR proposal to the [FNR](http://www.fnr.lu/) (Fond
National de Recherche Luxembourg)  

# Pre-requisites

## Git

You should become familiar (if not yet) with Git. Consider these resources:

* [Git book](http://book.git-scm.com/index.html)
* [Github:help](http://help.github.com/mac-set-up-git/)
* [Git reference](http://gitref.org/)

Remember to correctly initialize git with your name and email as follows: 

      $> git config --global user.name "Firstname Name"
      $> git config --global user.email Firstname.Name@uni.lu


### git-flow

The Git branching model for this repository follows the guidelines of [gitflow](http://nvie.com/posts/a-successful-git-branching-model/).
In particular, the central repo (on `gforge.uni.lu`) holds two main branches with an infinite lifetime:

* `production`: the *production-ready* slides, with a tag for each version used
* `master`: the main branch where the slides are in a state with the latest delivered development changes for the next release. This is the *default* branch you get when you clone the repo, and the one on which developments will take places.

You should therefore install [git-flow](https://github.com/nvie/gitflow), and probably also its associated [bash completion](https://github.com/bobthecow/git-flow-completion).

We will see below that we make also use of an interesting wrapper to `git` to
facilitate the tracking of remote branches (namely
[grb](https://github.com/webmat/git_remote_branch)). 

To initialize completely your local copy of this repo (assuming your SSH key is
correctly configured on the Gforge): 

      $> git clone  https://github.com/Falkor/fnr-latex-template.git
      $> cd fnr-latex-template
      $> make setup

# AFR Postdoc proposal

The full AFR Postdoc proposal is available under `AFR/Postdoc/`


# Contributing

Help me to complete the (missing) LaTeX templates by Forking this repository,
complete it (if possible under the same model) and pulling requests. 

