# Batch Connect - OSC Paraview

A VNCSim app designed for OSC OnDemand that launches Paraview within an Oakley
shared node through Quick batch.

## Install

1. Git clone this app in the desired location and go into the directory:

  ```sh
  git clone <repo> bc_osc_paraview

  cd bc_osc_paraview
  ```

2. Checkout the version of the app you want to deploy:

  ```sh
  git checkout <tag>
  ```

2. This app requires the
   [bc_fvwm_assets](https://github.com/OSC/bc_fvwm_assets) Bower asset, so we
   will need a local copy of Bower:

   ```sh
   npm install bower
   ```

3. Install the Bower asset:

  ```sh
  node_modules/.bin/bower install
  ```

## Update

1. Fetch the updated code:

  ```sh
  git fetch
  ```

2. Checkout the desired tag:

  ```sh
  git checkout <tag>
  ```

3. Update the Bower assets:

  ```sh
  node_modules/.bin/bower update --force
  ```

## Specification

### ROOT

All assets in this package look for dependencies in the specified `$ROOT`
directory. This should be set to correspond to the included `template/`
directory.

An example running the `xstartup` script included in this package:

```sh
# Path where you installed this project
BC_OSC_PARAVIEW_DIR="/path/to/bc_osc_paraview/template"

# Run the `xstartup` script with proper `$ROOT` set
ROOT="${BC_OSC_PARAVIEW_DIR}" ${BC_OSC_PARAVIEW_DIR}/xstartup
```

### PARAVIEW_MODULE

This environment variable describes the specific Paraview version to load. This
also assumes module support through the
[Lmod](https://www.tacc.utexas.edu/research-development/tacc-projects/lmod)
package manager is installed on the running compute node as well as the
requested module in `$PARAVIEW_MODULE`.

## Contributing

1. Fork it ( https://github.com/OSC/bc_osc_paraview/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
