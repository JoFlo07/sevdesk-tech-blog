# What is this?

This is the sevDesk Techblog - hosted at https://tech.sevdesk.com.

Tobin and Raphael are currently responsible. But everyone is encouraged to join the team.
Feel free to reach out. We are superhappy about feedback!

More:

 * Our tech chapter (internal): https://sevdesk.atlassian.net/wiki/spaces/CCC/pages/3634495493/Tech+Blog+Initiative
 * Join our internal slack channel at https://sevdesk.slack.com/archives/C02QK1ZSY5T

# What's the tech behind the blog?

The blog uses hugo and is based on the ananke theme.
More here: https://gohugo.io/getting-started/quick-start/

It uses some tiny customizations in layout/partials.

Hosting and deployment is done via GitHub Actions.
More here: https://gohugo.io/hosting-and-deployment/hosting-on-github/

# How to create a new post?

Make sure you got hugo installed. You can do so easily via 

    brew install hugo

Also see https://gohugo.io/getting-started/quick-start/

You can then start hugo via

    hugo sever -D

To create a new post either use

    hugo new posts/my-post.md

or simply copy an existing post into that directory.

Once you are happy with your post simply push the post to master and it will be deployed by GitHub Actions.






