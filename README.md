Installation
------------

1. To install the project, simply use bundle install 

bundle install

2. If using the new MacOS (Monterey (macOS 12), ensure that Ruby 3.1.1 is installed. It's recommended that you do not update the Ruby that comes by default with the Mac but rather use rbenv to install a local copy of the same using the following commands ...

rbenv install 3.1.1
rbenv local 3.1.1
rbenv init


Testing Locally
---------------

bundle exec jekyll serve --incremental

Building the project
--------------------

bundle exec jekyll build
