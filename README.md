# asp.net-framework-webapp-yaml
Deploying a .NET Framework web app with a yaml pipeline. These two pipelines are too be ran as templates by another projects `azure-pipelines.yml` file. 


``` 
C:.
└───asp.net-framework-webapp-yaml
        build_aspNetFramework_WebApp.yml
        deploy_aspNetFramework.webApp.yml
``` 

## Use:

```
resources:
  repositories:
    - repository: BuildTemplates
      type: git
      name: 'DevOps/BuildTemplates'

jobs:
- job: build
  Steps:
  - template: build_aspNetFramework_webApp.yml@BuildTemplates
- job: deploy
  - template: deploy_aspNetFramework_webApp.yml@BuildTemplates
```
****
