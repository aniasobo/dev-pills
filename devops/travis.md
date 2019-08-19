# Travis notes

**Fix for Travis failing to execute bundle:**

```
before_install:
- sudo apt-get update -qq
- sudo apt-get install -qq postgresql-server-dev-9.3
- gem update --system  # added this line
- gem install bundler  # added this line
```