# git-ready

git-ready is a tool for quickly joining an organization on GitHub.

Description
-----------

git-ready does three things.
1. Forks all repositories of the organization to your account.
2. Clones the forked repositories locally.
3. Configures an `upstream` remote for each repository, for convenient fetching.

It can be run again without concern. It will only fork and clone missing repositories.

Why would you want this?
------------------------

For a team that uses a Fork + Pull Request workflow, and has a large number of repositories, `git-ready` is a simple way to onboard new team members.

Example Workflow
----------------

1. Fork repository.
2. Make changes.
3. Test changes.
4. Push changes to `origin`
5. Submit Pull Request to `upstream`
6. Code Review
7. Merge

Installation
------------

`gem install git-ready`

Usage
-----

`git-ready <organization>`

Configuration
-------------
git-ready will search for configuration files in the following places:
* /etc/git-ready.yaml
* /usr/local/etc/git-ready.yaml
* ~/.config/git-ready.yaml
* ./git-ready.yaml

These will be loaded in order, and any conflicting keys will be overwritten.

If no configuration is found, git-ready will enter _Interactive Setup Mode_, and attempt to guide you through setup. It will prompt for your GitHub username and password, so it can issue itself an auth token (with `repo` scope only) for future use. This will be written to the configuration file.

If your GitHub account uses 2-Factor Authentication, git-ready will prompt you for a 2FA token.

If you would prefer to set up an auth token manually, that is supported too.

OSX Installation Issues?
------------------------

One of the gems used by git-ready ([Rugged](https://github.com/libgit2/rugged)), requires `cmake` to build. On OSX, this isn't installed by default, but can easily be resolved with `brew install cmake`.

License
-------
[MIT](https://tldrlegal.com/license/mit-license)

Contributors
------------
* [Chris Olstrom](https://colstrom.github.io/) | [e-mail](mailto:chris@olstrom.com) | [Twitter](https://twitter.com/ChrisOlstrom)
