NOTE
====

Jekyll build-on-Heroku-deploy can leverage on Rails asset pipeline `rake assets:precompile` hook to avoid relying on a custom buildpack, please check Jesse B. Hannah method here: https://github.com/jbhannah/jbhannah.net/commit/c7a22cfa62b1274342e4e162125b3ae171c3b125

Heroku Ruby Jekyll Buildpack
============================

Heroku Ruby Jekyll Buildpack is an up-to-date fork of Heroku's [official Ruby buildpack](https://github.com/heroku/heroku-buildpack-ruby) (v85) with added support for generating static [Jekyll](https://github.com/mojombo/jekyll) sites during the build/deployment stage.

With this [buildpack](http://devcenter.heroku.com/articles/buildpacks) you no longer need pre-build the site or commit the _site build directory to your repo. This simplifies the deployment process and keeps the repo clean. All of the standard Ruby tools are maintained in this buildpack, so you can take full advantage of Rack middleware and other useful tools from the Ruby ecosystem.

Usage
-----

    heroku create --buildpack http://github.com/jeremyvdw/heroku-buildpack-ruby-jekyll.git

or add this buildpack to your current app

    heroku config:add BUILDPACK_URL=http://github.com/jeremyvdw/heroku-buildpack-ruby-jekyll.git

Create a Ruby web app with dependencies managed by [Bundler](http://gembundler.com/) and a Jekyll site. [Heroku-Jekyll-Hello-World](https://github.com/burkemw3/Heroku-Jekyll-Hello-World) can be used as a sample starter.

Push to heroku

    git push heroku master

Watch it "Building jekyll site"
```
    -----> Fetching custom git buildpack... done
    -----> Ruby app detected
    -----> Compiling Ruby/Rack
    -----> Using Ruby version: ruby-2.1.0-rbx-2.2.1
    -----> Installing dependencies using Bundler version 1.3.2
          Running: bundle install --without development:test --path vendor/bundle --binstubs vendor/bundle/bin --deployment
          Using RedCloth (4.2.9)
          Using blankslate (2.1.2.4)
          Using fast-stemmer (1.0.2)
          Using classifier (1.3.3)
          Using colorator (0.1)
          Using highline (1.6.20)
          Using commander (4.1.5)
          Using ffi (1.9.3)
          Using ffi2-generators (0.1.1)
          Using liquid (2.5.4)
          Using rb-fsevent (0.9.3)
          Using rb-inotify (0.9.2)
          Using rb-kqueue (0.2.0)
          Using listen (1.3.1)
          Using maruku (0.7.0)
          Using posix-spawn (0.3.8)
          Using yajl-ruby (1.1.0)
          Using pygments.rb (0.5.4)
          Using redcarpet (2.3.0)
          Using safe_yaml (0.9.7)
          Using parslet (1.5.0)
          Using toml (0.1.0)
          Using jekyll (1.4.0)
          Using psych (2.0.2)
          Using rack (1.5.2)
          Using puma (2.7.1)
          Using rack-jekyll (0.4.1)
          Using rubysl-abbrev (2.0.4)
          Using rubysl-base64 (2.0.0)
          Using rubysl-benchmark (2.0.1)
          Using rubysl-bigdecimal (2.0.2)
          Using rubysl-cgi (2.0.1)
          Using rubysl-cgi-session (2.0.1)
          Using rubysl-cmath (2.0.0)
          Using rubysl-complex (2.0.0)
          Using rubysl-continuation (2.0.0)
          Using rubysl-coverage (2.0.3)
          Using rubysl-english (2.0.0)
          Using rubysl-csv (2.0.2)
          Using rubysl-curses (2.0.0)
          Using rubysl-date (2.0.6)
          Using rubysl-delegate (2.0.1)
          Using rubysl-digest (2.0.3)
          Using rubysl-drb (2.0.1)
          Using rubysl-e2mmap (2.0.0)
          Using rubysl-enumerator (2.0.0)
          Using rubysl-erb (2.0.1)
          Using rubysl-etc (2.0.3)
          Using rubysl-expect (2.0.0)
          Using rubysl-fcntl (2.0.4)
          Using rubysl-fiber (2.0.0)
          Using rubysl-fileutils (2.0.3)
          Using rubysl-find (2.0.1)
          Using rubysl-forwardable (2.0.1)
          Using rubysl-getoptlong (2.0.0)
          Using rubysl-socket (2.0.1)
          Using rubysl-thread (2.0.2)
          Using rubysl-gserver (2.0.0)
          Using rubysl-io-console (2.0.0)
          Using rubysl-io-nonblock (2.0.0)
          Using rubysl-io-wait (2.0.0)
          Using rubysl-ipaddr (2.0.0)
          Using rubysl-mathn (2.0.0)
          Using rubysl-readline (2.0.2)
          Using rubysl-irb (2.0.4)
          Using rubysl-logger (2.0.0)
          Using rubysl-matrix (2.1.0)
          Using rubysl-shellwords (2.0.0)
          Using rubysl-mkmf (2.0.1)
          Using rubysl-monitor (2.0.0)
          Using rubysl-mutex_m (2.0.0)
          Using rubysl-net-ftp (2.0.1)
          Using rubysl-singleton (2.0.0)
          Using rubysl-net-http (2.0.4)
          Using rubysl-net-imap (2.0.1)
          Using rubysl-net-pop (2.0.1)
          Using rubysl-net-protocol (2.0.1)
          Using rubysl-net-smtp (2.0.1)
          Using rubysl-net-telnet (2.0.0)
          Using rubysl-nkf (2.0.1)
          Using rubysl-observer (2.0.0)
          Using rubysl-open-uri (2.0.0)
          Using rubysl-open3 (2.0.0)
          Using rubysl-openssl (2.0.5)
          Using rubysl-optparse (2.0.1)
          Using rubysl-ostruct (2.0.4)
          Using rubysl-pathname (2.0.0)
          Using rubysl-prettyprint (2.0.2)
          Using rubysl-prime (2.0.0)
          Using rubysl-profile (2.0.0)
          Using rubysl-profiler (2.0.1)
          Using rubysl-pstore (2.0.0)
          Using rubysl-pty (2.0.2)
          Using rubysl-rational (2.0.1)
          Using rubysl-resolv (2.0.0)
          Using rubysl-rexml (2.0.2)
          Using rubysl-rinda (2.0.0)
          Using rubysl-rss (2.0.0)
          Using rubysl-scanf (2.0.0)
          Using rubysl-securerandom (2.0.0)
          Using rubysl-set (2.0.1)
          Using rubysl-stringio (2.0.0)
          Using rubysl-strscan (2.0.0)
          Using rubysl-sync (2.0.0)
          Using rubysl-syslog (2.0.1)
          Using rubysl-tempfile (2.0.1)
          Using rubysl-thwait (2.0.0)
          Using rubysl-time (2.0.3)
          Using rubysl-timeout (2.0.0)
          Using rubysl-tmpdir (2.0.0)
          Using rubysl-tsort (2.0.1)
          Using rubysl-un (2.0.0)
          Using rubysl-uri (2.0.0)
          Using rubysl-weakref (2.0.0)
          Using rubysl-webrick (2.0.0)
          Using rubysl-xmlrpc (2.0.0)
          Using rubysl-yaml (2.0.4)
          Using rubysl-zlib (2.0.1)
          Using rubysl (2.0.15)
          Using rubysl-json (2.0.2)
          Using bundler (1.3.2)
          Your bundle is complete! It was installed into ./vendor/bundle
          Bundle completed (5.85s)
          Cleaning up the bundler cache.
   -----> Writing config/database.yml to read from DATABASE_URL
          Building jekyll site
          Configuration file: /tmp/build_47908e9f-b52c-44f9-8397-d9e6beae90ee/_config.yml
          Source: /tmp/build_47908e9f-b52c-44f9-8397-d9e6beae90ee
          Destination: /tmp/build_47908e9f-b52c-44f9-8397-d9e6beae90ee/_site
          Generating... done.
   -----> Discovering process types
          Procfile declares types -> web
          Default types for Ruby  -> console, rake

   -----> Compiled slug size: 107.0MB
   -----> Launching... done, v7
          http://XXXXXX.herokuapp.com deployed to Heroku
```

See Also
--------

The blog post introducing this buildpack: [http://mwmanning.com/2011/11/29/Run-Your-Jekyll-Site-On-Heroku.html](http://mwmanning.com/2011/11/29/Run-Your-Jekyll-Site-On-Heroku.html).

