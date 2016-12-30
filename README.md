# bash-completion-imcl
Bash completion for IBM Installation Manager command line tool (imcl)

Tired of memorizing the IBM Installation Manager command line tool commands, and parameters? Well here's a bash completion script that will help you to use imcl more effectively!

## Installation
First add imcl to PATH
```
cat > /etc/profile.d/imcl_path.sh << EOF
#!/bin/sh
test \$UID -lt 100 && PATH=\${PATH}:/opt/IBM/InstallationManager/eclipse/tools
export PATH
EOF
```

Then download, and copy imcl to */etc/bash_completion.d/*

```
wget -O /etc/bash_completion.d/imcl "https://raw.githubusercontent.com/atterdag/bash-completion-imcl/master/imcl"
```

Each time you log in the two files will be sourced in to your bash shell, but for now just source them manually.
```
. /etc/profile.d/imcl_path.sh
. /etc/bash_completion.d/imcl
```

## Usage
The completion supports all imcl commands, and parameters. It allows you to set strings such as for product IDs, preferences, and properties, and knows when you need to navigate to a file, or a directory.

## Non-root IM installations
If your IM is not installed as root, then you need to adjust the path to the applicable IM installation. But the same bash completetion will work with any imcl command in PATH.
