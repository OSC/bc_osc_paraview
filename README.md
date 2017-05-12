# Batch Connect - OSC Paraview

![GitHub Release](https://img.shields.io/github/release/osc/bc_osc_paraview.svg)
![GitHub License](https://img.shields.io/github/license/osc/bc_osc_paraview.svg)

A VNCSim app designed for OSC OnDemand that launches Paraview within an Oakley
shared node through Quick batch.

## Prerequisites

This app requires the following software be installed on the nodes that the
batch job is intended to run on:

- [Paraview](http://www.paraview.org/) 4.4.0+
- [Lmod](https://www.tacc.utexas.edu/research-development/tacc-projects/lmod) 6.0.1+
- [Fluxbox](http://fluxbox.org/) 1.1.1+

For hardware rendering support:

- [X server](https://www.x.org/)
- [VirtualGL](http://www.virtualgl.org/) 2.3+

For VNC server support:

- [TurboVNC](http://www.turbovnc.org/) 2.1+
- [noVNC](https://github.com/novnc/noVNC) 0.6.2+

## Install

Use git to clone this app and checkout the desired branch/version you want to
use:

```sh
git clone <repo>
cd <dir>
git checkout <tag/branch>
```

You will not need to do anything beyond this as all necessary assets are
installed. You will also not need to restart this app as it isn't a Passenger
app.

To update the app you would:

```sh
cd <dir>
git fetch
git checkout <tag/branch>
```

Again, you do not need to restart the app as it isn't a Passenger app.

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

### INPUT_FILE

*Optional*

If this environment variable is set, then Paraview will attempt to load the
file path specified in this variable. This can be an absolute path or relative
to the user's home directory.

## Contributing

1. Fork it ( https://github.com/OSC/bc_osc_paraview/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
