---
layout: post
title:  "A Git Primer for Beginners"
date:   2021-07-22 14:22:00 -0500
categories: post
---

If you use a personal access token to authenticate to github, and you should be using one, you may have encountered the below error when trying to push updates to a remote repository.

{%highlight console%}
(refusing to allow a Personal Access Token to create or update workflow `.github/workflows/build_main.yaml` without `workflow` scope)
{%endhighlight%}

Frustrating right! Well, fortunately this is easy to fix by following the steps below.

1. Login to GitHub
2. Go to Settings and choose Developer Settings
3. Choose Personal Access Tokens
4. Click the link on the personal access token used for your project
5. Check the box beside workflow and click Update Token
6. Click Generate new token and create a save the new token
7. Change the token in your project to the new one with the workflow scope

Note that you may not need to do steps 6 and 7, it's best to try your push again after updating to confirm.

After updating or generating a new token the workflow scope will be allowed and you can continue on your way.






