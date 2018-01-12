#Running Discourse on Platform.sh

Clone this repo and push to platform.sh. Tada.

> NB: the minimal production plan to run Discourse on platform.sh is Medium

Because we are not working on master in order to push this to platform.sh git server you can use:
`git push platform platform_sh:master`

Or merge the changes to your master branch.

To finish off the installation  you should set the hostname and the developer emails
```
platform vset -emaster env:DISCOURSE_HOSTNAME myhostnoame.com
platform vset -emaster env:DISCOURSE_DEVELOPER_EMAILS myemail@example.com
```

## Changes to upstream
Changes we have made to the default upstream repo:

add 
```
gem 'platform_sh_rails'
```

to the Gemfile. I manually edited the `Gemfile.lock` because currently running `bundle update` breaks the installation.

add 
````
require 'platform_sh_rails'
````
to `application.rb`

create `config/discourse.conf` and remove it from `.gitignore`

Add `.platform.app.yaml` and `.platform/routes.yaml` and  `.platform/services.yaml`

