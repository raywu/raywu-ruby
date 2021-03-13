# raywu.github.com (depcrecated)
Octopress

# Blogging
+ http://octopress.org/docs/blogging/

```
rake new_post["title"]

rake new_page[super-awesome]
# creates /source/super-awesome/index.markdown
 
rake new_page[super-awesome/page.html]
# creates /source/super-awesome/page.html

rake generate   # Generates posts and pages into the public directory

rake watch      # Watches source/ and sass/ for changes and regenerates

rake preview    # Watches, and mounts a webserver at http://localhost:4000
```

# Deploy to blog
+ http://octopress.org/docs/deploying/github/

```
rake generate
rake deploy
```

# Remember to commit to Github

```
git add .
git commit -m 'your message'
git push origin source
```
