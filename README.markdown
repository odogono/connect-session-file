# connect-session-file


## Installation

    $ npm install connect-session-file

## Options

    - `path` storage path (optional, default: process.env.TMPDIR) 
    - `prefix` filename prefix (optional, default: `file-store-`)
    - `useAsync` use asynchronous file operations (optional, default: false)
    - `printDebug` prints debug output (optional, default: false)
    - `reapInterval` interval between removing stale sessions (optional, default: 600000 (10 mins), disable: -1 )
    - `maxAge` maximum age of sessions before removal (optional, default: 600000*3 (30 mins) )

## Example

See example/app.js

With express4:

    var session = require('express-session');
    var FileStore = require('connect-session-file')(session);

    app.use(express.session({
        secret: settings.cookie_secret,
        store: new FileSessionStore({
          db: settings.db
        })
      }));

With express<4:

    var express = require('express');
    var FileStore = require('connect-session-file')(express);

    app.use(express.session({
        secret: settings.cookie_secret,
        store: new FileSessionStore({
          db: settings.db
        })
      }));

With connect:

    var connect = require('connect');
    var FileStore = require('connect-session-file')(connect);

## Tests




## See Also

https://github.com/kcbanner/connect-mongo

https://github.com/bartt/connect-session-mongo
