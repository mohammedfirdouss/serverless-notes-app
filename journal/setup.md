### AWS CLI Installation

AWS CLI is installed for the project via the bash script [`./bin/install_aws_cli`](./bin/install_aws_cli)

[Getting Started Install (AWS CLI)](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

[AWS CLI Env Vars](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)

We can check if our AWS credentials is configured correctly by running the following AWS CLI command:
```sh
aws sts get-caller-identity
```

### Refactoring into Bash Scripts
I decided to create a bash script to install the AWS CLI.
This bash script is located here: [./bin/install_aws_cli](./bin/install_aws_cli)
- This will keep the Gitpod Task File ([.gitpod.yml](.gitpod.yml)) tidy.
- This allow us an easier to debug and execute manually AWS CLI install
- This will allow better portablity for other projects that need to install AWS CLI.


### Working Env Vars
#### env command
We can list out all Enviroment Variables (Env Vars) using the `env` command
We can filter specific env vars using grep eg. `env | grep AWS_
#### Setting and Unsetting Env Vars
In the terminal we can set using `export HELLO='world`
In the terrminal we unset using `unset HELLO`
We can set an env var temporarily when just running a command
```sh
HELLO='world' ./bin/print_message
```
Within a bash script we can set env without writing export eg.
```sh
#!/usr/bin/env bash
HELLO='world'
echo $HELLO
```
#### Printing Vars
We can print an env var using echo eg. `echo $HELLO`
#### Persisting Env Vars in Gitpod
We can persist env vars into gitpod by storing them in Gitpod Secrets Storage.
```
gp env HELLO='world'
```
All future workspaces launched will set the env vars for all bash terminals opened in thoes workspaces.
You can also set en vars in the `.gitpod.yml` but this can only contain non-senstive env vars.