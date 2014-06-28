# Now publish

Now let's share our fantastic module `colorify` to the world.

## 1. Register an account

First we need to register an account. There are two approaches:

* Go to http://ctx.io, login with Github, then copy the command and run it.


* Run `cortex adduser`, enter your username, password, and email address in the prompts.




## 2. Publish the package

In project root path, run `cortex publish` to publish the package to the registry. If everythings goes well, you will see:

```
compressing directory "/Users/ltebean/Desktop/colorify" to tarball "/Users/ltebean/.cortex/default/tmp/tmp-1048-mv0p04a6lz4w44o/package.tgz"
   PUT http://r.ctx.io/colorify 201
   GET http://r.ctx.io/colorify 200
   PUT http://r.ctx.io/colorify/-/colorify-0.1.0.tgz/-rev/1-c96b7dc660b01a909dff9aeb60ea698a 201
   PUT http://r.ctx.io/colorify/0.1.0/-tag/latest 201
```

Now other people can use our package by:
```
cortex install colorify
```

