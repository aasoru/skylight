# [Skylight Films Website](www.skylightfilms.es)

![screenshot](https://aasoru.github.io/images/projects/skylightfilms_screencapture.jpg)

Based on [Grav CMS](https://getgrav.org/), a **Fast**, **Simple**, and **Flexible**, file-based Web-platform.

# Requirements

- PHP 7.3.6 or higher.

### Start Project

All you need is this command:

```
$ /bin/grav server
```

# Running Tests

First install the dev dependencies by running `composer install` from the Grav root.

Then `composer test` will run the Unit Tests, which should be always executed successfully on any site.
Windows users should use the `composer test-windows` command.
You can also run a single unit test file, e.g. `composer test tests/unit/Grav/Common/AssetsTest.php`

To run phpstan tests, you should run:

- `composer phpstan` for global tests
- `composer phpstan-framework` for more strict tests
- `composer phpstan-plugins` to test all installed plugins
