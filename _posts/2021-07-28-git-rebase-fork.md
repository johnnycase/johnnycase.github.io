---
layout: post
title:  "Git - How to Rebase a Fork"
date:   2021-07-28 16:39:00 -0500
categories: post
---

If you have ever forked a repository on github, you have likely encountered the terms **merge** and **rebase** when researching how to interact with the original repository. Merging and rebasing are two different methods to solve the same problem, namely, how to keep your fork in sync with the original repository. This post will cover how and when to use rebase, but keep in mind there are specific scenarios in which to use either method.

So let's say you have forked a github repository so you can contribute some code or documentation. You create a branch of your fork, make your changes, and prepare to make a pull request. But you realize, the original repository has moved on since your fork, meaning, other developers have made commits to it that you don't have on your local copy. You will need to add those changes to your local copy before making a pull request. 

Rebasing will get all the commit to the original repository while saving the changes you made to your local copy. Rebasing will also rewrite the commit history on your forked branch, so it puts your commit at the beginning. This makes for a linear commit history in the original repository.

Keep in mind that rebase should not be done on a public repository where other developers are making commits. Since rebase will rewrite the commit history, it will be confusing other developers working on a project if the entire commit history was rewritten. If, however, you are the only person working on a particular repository, such as a fork, rebase is perfectly applicable and should be used keep a linear commit history.

Once your commits are complete, go to your terminal and change directory to your project. Then follow the list of commands below to rebase from the original repository.

Configure the upstream repository in your project. Change the url to the original repository.
{%highlight console%}
git remote add upstream url
{%endhighlight%}

Check that the upstream repository is configured.
{%highlight console%}
git remote -v
{%endhighlight%}

Get the original repository contents.
{%highlight console%}
git fetch upstream
{%endhighlight%}

Checkout your branch and rebase it with the original repository. Replace `main` in the checkout statement with your branch name.
{%highlight console%}
git checkout main
git rebase upstream/main
{%endhighlight%}

Push the rebased repository to your remote forked branch. The `--force` option may be necessary if there are conflicts between the local and remote repositories. Replace `main` with your branch name.
{%highlight console%}
git push origin main --force
{%endhighlight%}

Now you are ready to make a pull request and merge your changes with the original repository.  






