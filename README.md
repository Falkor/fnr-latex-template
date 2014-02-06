`README.md`

Copyright (c) 2014 [Sebastien Varrette](mailto:<Sebastien.Varrette@uni.lu>) [www](http://varrette.gforge.uni.lu)

        Time-stamp: <Jeu 2014-02-06 11:32 svarrette>

-------------------
# AFR Project Proposals -- LaTeX Template

## Synopsis

LaTeX-based templates for submission of project/AFR proposal to the [FNR](http://www.fnr.lu/) (Fond
National de Recherche Luxembourg). 

I made them because I think it's more convenient for collaborating work and
permits a better rendering  / management of the bibliography. Eventually, the
final version can be exported to the Word template using teh RTF version of the
proposal generated by `make rtf` 

Up to now, you'll find here LaTeX templates for the following calls: 

* [AFR PhD](http://www.fnr.lu/en/AFR-PhD-Postdoc-Grants/PhD-Grants) -- see `AFR/PhD/`
* [AFR PostDoc](http://www.fnr.lu/en/AFR-PhD-Postdoc-Grants/Postdoc-Grants) -- see `AFR/Postdoc/`
* [FNR Inter](http://www.fnr.lu/en/Research-Programmes/Research-Programmes/INTER-Programme),
  Promotion of International Collaboration, in particular for the [CHIST-ERA](http://www.fnr.lu/en/Research-Programmes/Research-Programmes/Calls/CHIST-ERA-Call-2013) European call -- see `INTER/CRIST-ERA`

## Local repository setup

This repository is hosted on out [GitHub](https://github.com/Falkor/fnr-latex-template).
Once cloned, initiate the potential git submodules etc. by running:

    $> cd fnr-latex-template
    $> make setup

## Pre-requisites

### Git

You should become familiar (if not yet) with [Git](http://git-scm.com/).
Consider these resources:

* [Git book](http://book.git-scm.com/index.html)
* [Github:help](http://help.github.com/mac-set-up-git/)
* [Git reference](http://gitref.org/)

At least, you shall configure the following exported variables within your
favorite shell (adapt accordingly): 

    # Bash configuration
    # Set your git user info
    export GIT_AUTHOR_NAME='<firstname> <name>'
    export GIT_AUTHOR_EMAIL='<email>'
    export GIT_COMMITTER_NAME="${GIT_AUTHOR_NAME}"
    export GIT_COMMITTER_EMAIL="${GIT_AUTHOR_EMAIL}"

You can also use the following commands:

    $> git config --global user.name "Your Name Comes Here"
    $> git config --global user.email you@yourdomain.example.com
    # configure colors
    $> git config --global color.diff auto
    $> git config --global color.status auto
    $> git config --global color.branch auto

### git-flow

The Git branching model for this repository follows the guidelines of
[gitflow](http://nvie.com/posts/a-successful-git-branching-model/).
In particular, the central repository holds two main branches with an infinite lifetime:

* `production`: the *production-ready* branch
* `master`: the main branch where the latest developments interviene. This is
  the *default* branch you get when you clone the repo

# Advanced information

## Releasing mechanism

The operation consisting of releasing a new version of this repository is automated by a set of tasks within the `Makefile`.

In this context, a version number have the following format:

      <major>.<minor>.<patch>-b<build>

where:

* `< major >` corresponds to the major version number
* `< minor >` corresponds to the minor version number
* `< patch >` corresponds to the patching version number
* `< build >` states the build number _i.e._ the total number of commits within the `master` branch.

Example: `1.0.0-b28`

The current version number is stored in the file `VERSION`. __/!\ NEVER MAKE ANY MANUAL CHANGES TO THIS FILE__

For more information on the version, run:

     $> make versioninfo

If a new  version number such be bumped, you simply have to run:

      $> make start_bump_{major,minor,patch}

This will start the release process for you using `git-flow`.
Probably after that, the first things to do is to change within the main LaTeX document the version number and commit this change.
Then, to make the release effective, just run:

      $> make release

it will finish the release using `git-flow`, create the appropriate tag in the `  production` branch and merge all things the way they should be.

# Contributing

This project is released under the terms of the
[GNU GPLv3](https://www.gnu.org/licenses/gpl.html) licence -- see the
[LICENCE](https://github.com/Falkor/fnr-latex-template/blob/master/LICENSE)
file.


Help me to complete the (missing) LaTeX templates by Forking this repository,
complete it (if possible under the same model) and pulling requests. 

