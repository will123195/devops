# devops service and utility

### Service:
- listen for githooks
- daily/hourly backups
- monitor instances/services

### Utiltity:
- deploy code (liveswap)
- create ami's


```
Usage: ops <command> [<args>]

Commands:
  ami <instanceTag>
  config  
  deploy <service> <gitTag> to <env>
  instances
  rotate <service> on <env>
  ship <service> <gitTag> to <env>
  version <service>
```


Config
```js
{  
  services: {
    db: {
      git: "ssh+git://git@github.com/will123195/db.git",
      packerTemplate: "",
      production: {
        branch: "master"
        start: "npm run production",
        awsInstanceTag: "leveldb"
      },
      staging: {
        branch: "develop"
        start: "npm run staging",
        awsInstanceTag: "leveldb-staging"
      }
    }
  },
  alerts: {

  }
}

}
```
