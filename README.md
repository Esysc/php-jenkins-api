Emagister\Jenkins
=================
Emagister\Jenkins is a Jenkins API written in PHP
for PHP 5.3+. It has been born for Dashboard
and extreme feedback purposes.

At this time, it has support for the following:

- Integrating different Jenkins information
- Accessing to:
  - Jobs
  - ChangeSets
  - Changes
  - Authors
  - Properties

Requiring in another project
============================
Using composer:

```
    "require": {
        "emagister/jenkins": "dev-master"
    }
```

```php
<?php
    use Emagister\Jenkins\Dashboard;
    use Emagister\Jenkins\Source;

    $dashboard = new Dashboard();
    $dashboard->addSource(new Source('http://ci.jenkins-ci.org/view/All/api/json/?depth=2'));
    // Add as many sources as you want
    // ...

    print_r($dashboard->getJobs());
```


Usage
=====
Usage is fairly straightforward,

```php
<?php
    use Emagister\Jenkins\Dashboard;
    use Emagister\Jenkins\Source;

    $dashboard = new Dashboard();
    $dashboard->addSource(new Source('http://ci.jenkins-ci.org/view/All/api/json/?depth=2'));
    // Add as many sources as you want
    // ...

    print_r($dashboard->getJobs());
```

Autoloading
===========
Emagister\Jenkins follows the PSR-0 standard for class naming conventions, meaning
any PSR-0-compliant class loader will work. To simplify things out of the box,
the component contains an "\_autoload.php" file which will register an autoloader
for the Emagister\Jenkins component with spl_autoload. You can simply include that
file, and start using Emagister\Jenkins.

Dashboard Example
=================
You can see a beatiful dashboard working with twitter bootstrap. Point your virtual
host to the examples folder and see the magic.

Demo
====
Check it online at <http://engineering.emagister.com/jenkins-dashboard>