# Web APIs - `window.location` Cheatsheet

|            | protocol |      | hostname             | pathname  | search       | hash |
| ---------- | -------- | ---- | -------------------- | --------- | ------------ | ---- |
| PROPERTIES | `https:` | `//` | `www.somedomain.com` | `/stuff/` | `?filter=JS` | `#2` |

## `https://www.somedomain.com/stuff/?filter=JS#2`

```
window.location.origin    => 'https://www.somedomain.com'
               .protocol  => 'https:'
               .host      => 'www.somedomain.com'
               .hostname  => 'www.somedomain.com'
               .port      => ''
               .pathname  => '/stuff/'
               .search    => '?filter=JS'
               .hash      => '#2'
               .href      => 'https://www.somedomain.com/stuff/?filter=JS#2'
```

## `window.location` properties

| `window.location` | Returns                                           |
| ----------------- | ------------------------------------------------- |
| `.origin`         | Base URL (protocol + hostname + port number)      |
| `.protocol`       | Protocol schema (`http:` or `https:`)             |
| `.host`           | Domain name + port                                |
| `.hostname`       | Domain name                                       |
| `.port`           | Port number                                       |
| `.pathname`       | The initial `/` followed by the path              |
| `.search`         | `?` followed by query string                      |
| `.hash`           | `#` followed by the anchor or fragment identifier |
| `.href`           | full URL                                          |

## Changing the url properties

```
window.location.protocol  = 'https'
               .host      = 'localhost:8000'
               .hostname  = 'localhost'
               .port      = '8080'
               .pathname  = 'path'
               .search    = 'query string'    // no need to pass ?
               .hash      = 'hash'            // no need to pass #
               .href      = 'url'
```

## The `Location` object

```
window.location           => Location   // preferred for clarity
window.document.location  => Location
document.location         => Location
location                  => Location
```

## `window.location` methods

| `window.location` |                                                                          |
| ----------------- | ------------------------------------------------------------------------ |
| `.assign()`       | navigates to the given URL                                               |
| `.replace()`      | navigates to given URL and removes current page from the session history |
| `.reload()`       | reload the current page                                                  |
| `.toString()`     | returns the URL                                                          |

```
window.location.assign('url)
               .replace('url)
               .reload()
               .toString()
```

[Source - @samanthaming](https://dev.to/samanthaming/window-location-cheatsheet-4edl)
