# nrd
--------------------------------------------------------------------------------

Script to record deployments in NewRelic's App timeline

## Changelog
--------------------------------------------------------------------------------

* **04/24/2017 - v1** - First Stable Release

## Dependencies
--------------------------------------------------------------------------------

[jq], a command-line JSON processor

## How to Use
--------------------------------------------------------------------------------

**Conf File**:
Store you NewRelic API Key inside _nrd.conf_.

Remember to set the var "SCRIPTCONFFILE" in the script with the absolute path to this file.

| Legend | Description |
|--|--|
| API_KEY | your API Key to access NewRelic API environment |

```sh
$ cat nrd.conf
API_KEY=bm90IG15IHJlYWwga2V5
```

**Command Line**:
```
nrd -a <app> -c <changelog> -d <description> -r <revision> -u <user>
```
```
    app: App Name (duh)
    changelog: file added, file changed, file removed, etc
    description: quick description about some new behavior or so
    revision: Revision Number
    user: User who made the deploy
```
**Notice**: Remember to use quotation marks in changelog and description, you know, for best practices.

**Example**:

```sh
$ nrd -a myapp -c "Added: index.php, Removed: None" -d "Index Added for the new site" -r "001" -u "developer@example.com"
```

[//]: #
   [jq]: <https://stedolan.github.io/jq/>
