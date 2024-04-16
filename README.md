DHT Gin Custom 
===

# Info
- [ d-ht.com ](https://d-ht.com/)

# Install
```
composer require dhtpublic/dht_gin_custom
```

# Development
[ Drupal coding standards ](https://www.drupal.org/docs/develop/standards) have to be maintained
Code, maschine names and comments have to be in english.

## New version
Create a new tag for new release
Follow [ semver.org ](https://semver.org/) standard.

Have a look at the current tags and versions:
```
git tag
```

Create a new version:
```
git tag x.x.x
```

Push the new tag:
```
git push --tags
```

Workaround .git folder in module

```
Regardless of whether composer require or update the module in a project, please head to the contrib/dht_gin_custom folder and delete the .git folder
It could help adding following script to the composer.json if not allready included.

"scripts": {
    "post-install-cmd": [
        "@composer drupal:scaffold",
        "find htdocs/vendor -name '.git' | xargs rm -rf",
        "find htdocs/vendor -name '.git' | xargs rm -rf",
        "find htdocs/modules -name '.git' | xargs rm -rf",
        "find htdocs/modules -name '.github' | xargs rm -rf"
    ],
    "post-update-cmd": [
        "@composer drupal:scaffold",
        "find htdocs/vendor -name '.git' | xargs rm -rf",
        "find htdocs/vendor -name '.git' | xargs rm -rf",
        "find htdocs/modules -name '.git' | xargs rm -rf",
        "find htdocs/modules -name '.github' | xargs rm -rf"
    ]
}