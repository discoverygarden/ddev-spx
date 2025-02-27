[![tests](https://github.com/discoverygarden/ddev-spx/actions/workflows/tests.yml/badge.svg)](https://github.com/discoverygarden/ddev-spx/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2025.svg)

# SPX <!-- omit in toc -->

The [`php-spx`](https://github.com/NoiseByNorthwest/php-spx) profiling extension has been made available; however, it is left disabled by default.

## Enable SPX

```bash
ddev spx-enable
```

## Use SPX

[`php-spx`'s basic usage docs](https://github.com/NoiseByNorthwest/php-spx?tab=readme-ov-file#basic-usage) may help guide its usage, but should essentially be able to:

- ```bash
  ddev spx-launch
  ```

  - Enable profiling (should be a checkbox).

- Browse the pages being profiled.
- Hit/reload the SPX GUI in the browser to access the profiling results.

## Disable SPX

```bash
ddev spx-disable
```
