# pgreze.com

[![Netlify Status](https://api.netlify.com/api/v1/badges/b849cb37-f780-42ba-9405-d069771080a2/deploy-status)](https://app.netlify.com/sites/pgreze/deploys)

My [hugo](https://gohugo.io/) powered and [netlify](https://netlify.com) hosted blog.

## Usage

To use always the same version with docker (-extras is adding py-pygments):

```
# Version
docker run --rm -it jguyomard/hugo-builder:0.55-extras hugo version

# Create a new post
docker run --rm -it -v $PWD:/src -u hugo jguyomard/hugo-builder:0.55-extras hugo new post/2019-10-02-universal-apk-commands.md

# Serve
docker run --rm -it -v $PWD:/src -p 1313:1313 -u hugo jguyomard/hugo-builder:0.55-extras hugo server -w --bind=0.0.0.0
# With drafts
docker run --rm -it -v $PWD:/src -p 1313:1313 -u hugo jguyomard/hugo-builder:0.55-extras hugo server -D -w --bind=0.0.0.0

# Build and see results
docker run --rm -it -v $PWD:/src -u hugo jguyomard/hugo-builder:0.55-extras hugo
cd public/ && python3 -m http.server
```

Sadly brew is not usable because current hugo version (0.64.1) is not rendering images:

```
# Install
brew install hugo

# Create a new post
hugo new post/2019-10-02-universal-apk-commands.md

# Start server
hugo server
# With drafts
hogu server -D

# Create release in public/
hugo
```

