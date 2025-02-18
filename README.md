[![tests](https://github.com/discoverygarden/ddev-spx/actions/workflows/tests.yml/badge.svg)](https://github.com/discoverygarden/ddev-spx/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2025.svg)

# SPX <!-- omit in toc -->

The [`php-spx`](https://github.com/NoiseByNorthwest/php-spx) profiling extension has been made available; however, it is left disabled by default. Note that it will need to be enabled for each new container, so whenever the "web" container for the project is (re)started.

## Enable SPX

```bash
# To enable the extension.
ddev exec phpenmod -v \$DDEV_PHP_VERSION spx
# To make php-fpm reinitialize, to pick up the newly enabled extension
ddev exec killall -USR2 php-fpm
```

## Use SPX

[`php-spx`'s basic usage docs](https://github.com/NoiseByNorthwest/php-spx?tab=readme-ov-file#basic-usage) may help guide its usage, but should essentially be able to:

- Hit https://dgi-starter.ddev.site/?SPX_KEY=dev&SPX_UI_URI=/
  - Change up the hostname as necessary to reflect your current site.
  - Can alternatively:

    ```bash
    ddev launch "/?SPX_KEY=dev&SPX_UI_URI=/"
    ```

- Browse the pages being profiled.
- Hit/reload https://dgi-starter.ddev.site/?SPX_UI_URI=/ , and find the relevant requests at the bottom.
  - Again, alternatively, might to something like:

    ```bash
    ddev launch "/?SPX_UI_URI=/"
    ```

    to get back to it.

## Disable SPX

```bash
# To disable the extension.
ddev exec phpdismod -v \$DDEV_PHP_VERSION spx
# To make php-fpm reinitialize, to drop the newly disabled extension
ddev exec killall -USR2 php-fpm
```

Alternatively, a:

```bash
ddev restart
```

should result in the container being recreated without the extension enabled.
