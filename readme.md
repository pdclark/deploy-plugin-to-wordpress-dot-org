# Configuration

Edit these lines:

    SVNUSER="username"            # SVN username on wordpress.org

# Usage

* Download `deploy.sh` and place it somewhere it wont be deleted.
* Make it executable with `chmod +x deploy.sh`.
* Add an alias in `.profile` for bash or `.zshrc` for zsh `alias wpdeploy='~/deploy-plugin-to-wordpress-dot-org/deploy.sh'
* cd into plugin directory and run `wpdepoly plugin-main-file.php`

# Ignoring Files

If you have files in your Git repository that you would not like to commit to the WordPress repo, find and edit these lines:

    # Add any large source files or other things to ignore here
    echo "Ignoring github specific files and deployment script"
    svn propset svn:ignore "deploy.sh
    README.md
    .git
    .gitignore" "$SVNPATH/trunk/"

# History

Original version: [Dean Clatworthy's deploy script](https://github.com/deanc/wordpress-plugin-git-svn).

[Forked by thenbrent](http://thereforei.am/2011/04/21/git-to-svn-automated-wordpress-plugin-deployment/), which removed the requirement for a local SVN repo.

[Forked by pdclark](https://github.com/pdclark/deploy-plugin-to-wordpress-dot-org) to allow trunk as stable tag, move config to one place, and share with others.