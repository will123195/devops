# devops service and utility

### Service:
- listen for githooks
- daily/hourly backups
- monitor instances/services
- mirror commits to github/bitbucket

### Utiltity:
- deploy code 
    - liveswap
    - check travis build
- create ami's


```
Usage: ops <command> [<args>]

Commands:
  ami <instanceTag>
  config  
  deploy <service> [<gitTag>] to <env>
  instances
  lb <instanceTag>
  register <service>
  rotate <service> on <env>
  ship <service> <gitTag> to <env>
  version <service>
```


Config
```js
{  
  services: [
    {
      name: "db",
      git: ["ssh+git://git@github.com/will123195/db.git"],
      baseAmi: "ubuntu-nodejs", // or packerTemplate
      production: {
        start: "npm run production",
        awsInstanceTag: "leveldb",
        awsInstanceQty: 3,
        openPorts: [1777]
      },
      staging: {
        start: "npm run staging",
        awsInstanceTag: "leveldb-staging",
        openPorts: [1777]
      }
    }
  ],
  alerts: {

  }
}

}
```
