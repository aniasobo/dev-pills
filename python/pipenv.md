# Troubleshooting `pipenv` and the Pipfile dependencies

### Resolve package dependencies

```
$ pipenv lock --pre --clear
```

Workaround: add problematic packages to `dev-packages`, like so:

```
# Pipfile
...
[packages]
pckg1 = "==3.0.0"

[dev-packages]
pckg2 = "==1.0.2"
```

Then lock & install:

```
$ pipenv lock --dev
$ pipenv install --dev
```