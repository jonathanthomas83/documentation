# Deploying HUGO with GitHub Actions

# 1. Create the GitHub Actions code and upload to Github

Deploy to '`main`' branch. (shouldn't need to be changed)

Important: Use the following in the bottom section of the GitHub Action.

```
- name: Deploy
  uses: peaceiris/actions-gh-pages@v3
  with:
    deploy_key: ${{ secrets.ACTIONS_DEPLOY_KEY }}
    publish_dir: ./public
```

https://github.com/marketplace/actions/github-pages-action

# 2. Create SSH Deploy Key and secrets

`ssh-keygen -t rsa -b 4096 -C "$(git config user.email)" -f gh-pages -N ""`

https://github.com/marketplace/actions/github-pages-action#%EF%B8%8F-create-ssh-deploy-key

# 3. Copy the contents of 'gh-pages.pub'

`cat gh-pages.pub`

Copy the contents shown normally and paste into GitHub 'Deploy Keys' under the Repository settings.

Name the Deploy Key: '`Public key of ACTIONS_DEPLOY_KEY`'

# 4. Copy the contents of 'gh-pages'

`cat gh-pages`

Copy the contents shown normally and paste into GitHub 'Secrets' > 'Actions' under the Repository settings.

Name the Secret Action: '`ACTIONS_DEPLOY_KEY`'

# 5. Commit changes in code and push the site to Github

Commit changes in code and push the site to Github. This will automatically kick off an GitHub Action process and will deploy the website/GitHub Pages site.

# 6. More info

- https://github.com/marketplace/actions/github-pages-action#%EF%B8%8F-set-ssh-private-key-deploy_key
- https://discourse.gohugo.io/t/issue-deploying-hugo-site-to-github-pages-using-github-actions/38617/2
