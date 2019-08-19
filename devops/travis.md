# Travis notes

**Fix for Travis failing to execute bundle:**

```
before_install:
- sudo apt-get update -qq
- sudo apt-get install -qq postgresql-server-dev-9.3
- gem update --system  # added this line
- gem install bundler  # added this line
```

**how to get Travis to run the correct version of FF for JS tests:**  

```
addons:
  firefox: "33.0"
before_script:
  - export DISPLAY=:99.0
  - sh -e /etc/init.d/xvfb start
```

* [Setting up Travis for a Rails app](https://medium.com/full-taxx/how-to-setup-travis-ci-for-a-rails-application-78a453963300)