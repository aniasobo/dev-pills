# Servers

## Run an ad hoc static http server in your current directory, runs on port 8000

### Python 3

`$ python -m http.server 8000`

### Ruby

`$ ruby -rwebrick -e'WEBrick::HTTPServer.new(:Port => 8000, :DocumentRoot => Dir.pwd).start'`

Ruby 1.9.2+ - `$ ruby -run -ehttpd . -p8000`

Ruby - `adsf`:

```
$ gem install adsf   # install dependency
$ adsf -p 8000
```

Ruby - Sinatra:

```
$ gem install sinatra   # install dependency
$ ruby -rsinatra -e'set :public_folder, "."; set :port, 8000'
```

### Node.js

`http-server`:

```
$ npm install -g http-server   # install dependency
$ http-server -p 8000
```

`node-static`:

```
$ npm install -g node-static   # install dependency
$ static -p 8000
```

[SOURCE AND MORE LANGUAGES](https://gist.github.com/willurd/5720255)
