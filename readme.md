
This repo demonstrates an issue in which Jekyll appends the _absolute_
path of `_layout/default.htm` to the absolute path for the `_posts`
directory and then tries to find default.htm at that location.

The issue appears to have started occurring in Jekyll `2.5.0`. 

I do not see the issue in the preceding version, Jekyll `2.4.0`.

If I build with Jekyll `2.4.0`, I get the following output:

    $ ~/.rvm/gems/ruby-2.2.0/gems/jekyll-2.4.0/bin/jekyll build --config _config.yml -s _posts -d ./_site --verbose
    Configuration file: _config.yml
                Source: _posts
           Destination: ./_site
          Generating... 
                        done.
     Auto-regeneration: disabled. Use --watch to enable.

If I build with Jekyll `2.5.0`, I get the following output:

    $ ~/.rvm/gems/ruby-2.2.0/gems/jekyll-2.5.0/bin/jekyll build --config _config.yml -s _posts -d ./_site --verbose
    Configuration file: _config.yml
                Source: _posts
           Destination: ./_site
          Generating... 
    Error reading file /Users/cparker/git/github/carljparker/test-case-jekyll-directory/_layouts/default.html: No such file or directory @ rb_sysopen - /Users/cparker/git/github/carljparker/test-case-jekyll-directory/_posts/Users/cparker/git/github/carljparker/test-case-jekyll-directory/_layouts/default.html

I have posted about this behavior in the following locations on GitHub:

  <https://github.com/jekyll/jekyll/issues/3488#issuecomment-87139175>

  <https://github.com/jekyll/jekyll/pull/2882#issuecomment-87150875>

*** END ***

