# Terraform Beginner Bootcamp 2023

## Setting up Terraform cli

As the existing files provided are having deprecating commands, so googled out "terraform cli install" and created new bash script *install_terraform_cli*
(Terraform CLI Installation Guide)[https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli]

Need to use *#!/usr/bin env bash* for making bang portable.
(Linux portable)[https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli]

To execute the script try **source ./bin/install_terraform_cli**, as ./bin/install_terraform_cli doesn’t have permissions, we need to manually provide permissions by using below script.

shows list with hidden files(a - all, l - list) to check permissions
```
ls -la
```

Changes *bin/install_terraform_cli* to executable mode
```
Chmod u+x bin/install_terraform_cli
```
Changing file/directory permissions [https://www.freecodecamp.org/news/linux-chmod-chown-change-file-permissions/ ]

### Gitpod Lifecycle

Init is run only when you started the workspace for the first time.

So use init only for heavy lifting items like downloading libraries which are initially required to setup workspace.

GitPod Lifecycle: [https://www.gitpod.io/docs/configure/workspaces/tasks]

###Setting Environment variables to set to PROJECT_ROOT to use in bash scripts.

**env** gives all the environment variables set to our environment

```
env | grep HOST
```

To print environment variable
```
Echo $PROJECT_ROOT
```

There are different ways to set Environment variables in bash script:

	1. ```sh
	PROJECT_ROOT="/path/workspace"

	cd PROJECT_ROOT
	```


	2. export PROJECT_ROOT="/path/workspace"

	```sh
	cd PROJECT_ROOT
	```

	3. PROJECT_ROOT="/path/workspace" ./script_to_run

To persist in gitpod you can use the below :
```
gp env PROJECT_ROOT="/path/workspace"
```

We can also set non sensitive env vars in '.gitpod.yml' file