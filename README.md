_View this file in DevOps._


# .gitignore
This file lists all unversioned files and folders. If you make any changes to these files or folders, these will not be detected by Git and you will not be able to commit and push them. You should have no need to do so, anyway.


# Folder DevOps

## YAML Files
The .yaml files are referenced in the Pipelines section of DevOps. Pipelines read files stored in the dev branch, so if you want to make any change, make sure it is updated in the dev branch.

You only need to update name of the deployment folder in the target UiPath tenant. You should have no need to modify any other part of the scripts. The deployment folder must exist in the target tenant before the scripts run, otherwise the deployment will fail.

## Update Assets
It is possible to add, edit and delete assets as part of the deployment process. For other automation components such as queues, storage buckets, triggers, etc., you will have to raise a ServiceNow request so that the support team can take care of that.

### Assets_to_delete.csv
The first line is the header, then place each asset's name on a new line.

```
name
AssetToDelete1
AssetToDelete2
etc.
```

### Assets_to_add_or_update.csv
The first line is the header, then place each asset's definition on a new line. If a given assets exists, it will be updated. If it does not exist, it will be
Rules:

 - No space before or after comma
 - Valid types are: text, boolean, integer
 - Description is optional, however, you must still use the last comma
```
name,type,value,description
AssetToAdd1,text,Asset1 value,optional description
AssetToUpdate,boolean,true,
AssetToAdd2,integer,3,another description
```

    
