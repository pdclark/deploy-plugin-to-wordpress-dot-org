# Configuration

Edit these lines:

    # User config
    PLUGINSLUG="example-plugin"   # Slug on wordpress.org (from the plugin URL)
    MAINFILE="example-plugin.php" # Name of main php file in the WordPress plugin
    SVNUSER="username"            # SVN username on wordpress.org

# Usage

* Place deploy.sh at the top of your plugin's Git directory.
* Make it executable with `chmod 755 deploy.sh`.
* Run `./deploy.sh` to deploy master to wordpress.org.

## Readme Markdown

If you choose to use a readme.md file for Github, instead of having two files just use the readme.md with the proper heading usage, the script will automatically convert:

* "# Plugin title" becomes "=== Plugin title ==="
* "## Section title" becomes "== Section title =="
* "### Sub heading" becomes "= Sub heading ="

Outside of the different headings, everything else in the file must match the syntax that WordPress expects. The single readme file can work for both places.

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