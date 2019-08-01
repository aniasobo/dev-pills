# Development environment fixes

## `npm` permission errors 

`sudo chown -R $(whoami) ~/.npm` gives you permission to edit .npm locally

## Killing port processes

`brew services stop <process name>`

real-life example: `brew services stop postgresql`

## To find out which version runs

`which npm`, `which ruby` etc

## To edit PATH

`code ~/.zshrc` or `code ~/.bash_profile` depending on your setup

(this is also where aliases and environment vars are added)