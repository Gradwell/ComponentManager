ComponentManager
================

ComponentManager adds commands to phix to help you create and maintain a variety of PHP components.

To learn more about PHP components, Google for 'Beyond Frameworks'.

Installation
------------

You can install ComponentManager using the [PEAR Installer](http://pear.php.net). This installer is the community's de-facto standard for distributing PHP components.

    sudo pear channel-discover pear.gradwell.com
    sudo pear install --alldeps Gradwell/ComponentManager

After installation, you will find the code inside your local PEAR repository, which on Linux systems is normally /usr/share/php.

Documentation
-------------

Once installed, ComponentManager adds a number of commands to phix. You can get the list of available commands from phix:

    # display phix's available commands
    phix

    # display the current version of ComponentManager
    phix component-manager:version

Development Environment
-----------------------

If you want to patch or enhance this component, you will need to create a suitable development environment:

    #phpunit
    sudo pear channel-discover pear.phpunit.de
    sudo pear channel-discover components.ez.no
    sudo pear channel-discover pear.symfony-project.com
    sudo pear install --alldeps phpunit/PHPUnit

    # phing
    sudo pear channel-discover pear.phing.info
    sudo pear install --alldeps phing/phing

    # pdepend
    sudo pear channel-discover pear.pdepend.org
    sudo pear install --alldeps pdepend/PHP_Depend-beta

    # phpdoc
    sudo pear install --alldeps pear/PhpDocumentor

    # phpmd
    sudo apt-get install php5-imagick
    sudo pear channel-discover pear.phpmd.org
    sudo pear install --alldeps phpmd/PHP_PMD-alpha

    # phpcpd
    sudo pear install --alldeps phpunit/phpcpd

    # phpcs
    sudo pear install --alldeps pear/PHP_CodeSniffer-beta

    # phpcb
    sudo pear install --alldeps phpunit/PHP_CodeBrowser

You can then clone the git repository:

    # ComponentManager
    git clone git://github.com/Gradwell/ComponentManager.git

You will then need to populate the vendor folder, to build a local copy of all of the dependencies for 

    # vendor folder
    cd ComponentManager
    phing build-vendor

To test your changes, you would do the following:

    # test changes
    phing test
    
    # install changes into vendor folder, for local use
    phing pear-package
    phing install-local
    vendor/bin/phix <command>
