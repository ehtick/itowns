![iTowns](https://raw.githubusercontent.com/iTowns/itowns.github.io/master/images/itowns_logo_300x134.png)
# iTowns

[![Coverage Status](https://coveralls.io/repos/github/iTowns/itowns/badge.svg?branch=master)](https://coveralls.io/github/iTowns/itowns?branch=master)
[![example branch parameter](https://github.com/iTowns/itowns/actions/workflows/integration.yml/badge.svg?query=branch%3Amaster)](https://github.com/iTowns/itowns/actions/workflows/integration.yml?query=branch%3Amaster)
[![DeepScan grade](https://deepscan.io/api/teams/2856/projects/10991/branches/159107/badge/grade.svg)](https://deepscan.io/dashboard#view=project&tid=2856&pid=10991&bid=159107)
[![Discord](https://img.shields.io/discord/1024249405634781244)](https://discord.gg/YueemZcEvw)

## What is it?

iTowns is a [Three.js](https://threejs.org/)-based framework written in
Javascript/WebGL for visualizing 3D geospatial data.

It can connect to WMS/WMTS/TMS servers including elevation data and load many
different data formats (3dTiles, GeoJSON, Vector Tiles, GPX and much more). A
complete list of features and supported data formats is [available on the
wiki](https://github.com/iTowns/itowns/wiki/Supported-Features).

It officially targets the last two major versions of both Firefox, Safari and
Chromium-based browsers (Chrome, Edge, ...) at the date of each release. Older
browsers supporting WebGL 2.0 may work but we do not offer support.

![iTowns screenshot](https://raw.githubusercontent.com/iTowns/itowns.github.io/master/images/itownsReleaseXS.jpg)

## Documentation and examples

The official documentation is [available
here](http://www.itowns-project.org/itowns/docs/). It contains tutorials to help
you start using iTowns, and an API reference. You can find more informations on
its contribution [here](docs/README.md).

Official examples can be [viewed
here](http://www.itowns-project.org/itowns/examples/). Some examples available:

* [Globe with WFS data](http://www.itowns-project.org/itowns/examples/#source_stream_wfs_3d)
* [Plane mode with Vector Tiles](http://www.itowns-project.org/itowns/examples/#vector_tile_raster_2d)
* [3D effect using scene postprocessing](http://www.itowns-project.org/itowns/examples/#effects_stereo)
* [Globe with split rendering](http://www.itowns-project.org/itowns/examples/#effects_split)

[![iTowns examples](http://www.itowns-project.org/images/montage.jpg)](http://www.itowns-project.org/itowns/examples/)

## How to run it locally?

Clone the repo and then run:

```
npm install
npm start
```

Try out the examples at http://localhost:8080/examples

## How to use it in your project?

You can use it through npm (the preferred way) or download a bundle from our
github release page.

### With npm

In your project:

To use all iTowns features, install `itowns` package :

```bash
npm install --save itowns
```

```js
import { Coordinates } from 'itowns';

const coordinates = new Coordinates('EPSG:4326', 88., 50.3, 120.3);

// change projection system to pseudo mercator
coordinates.as('EPSG:3857');
```

To import Widget features

```js
import { Navigation } from 'itowns/widgets';

const viewerDiv = document.getElementById('viewerDiv');

// Create a GlobeView
const view = new itowns.GlobeView(viewerDiv);

// Add navigation widget
const navigation = new Navigation(view, {
    position: 'bottom-right',
    translate: { y: -40 },
});
```

iTowns is currently moving to a monorepo organization and to a segmentation in sub-modules, allowing to import only some of itowns functionalities. Current itowns sub-modules are:
- [@itowns/geographic](packages/Geographic/README.md): `npm install --save @itowns/geographic`

This package contains the ES5-compatible sources of iTowns, up to date with the latest release.

If you're using a module bundler (like wepback), you can directly write
`require('itowns')` in your code.

Alternatively, we provide a bundle you can directly include in your html files
that exposes `itowns` in `window`:

```html
<script src="node_modules/itowns/dist/itowns.js"></script>
```

**/!\ Please note that this bundle also contains the dependencies**.

### From a release bundle

See our [release page](https://github.com/iTowns/itowns/releases). Note that
there isn't a lot of support for older version of iTowns, we highly recommend to
use the last release everytime.

### Try modifications before they are released

If you want to try some features or bug fixes that are planned for the next release, we provide
a @next version of itowns. You can install it as such :

```bash
npm install --save itowns@next
```

To switch back to the version to date with the latest release, you need to run :

```bash
npm install --save itowns@latest
```

## Contributing

If you are interested in contributing to iTowns, please read the [CONTRIBUTING
guide](CONTRIBUTING.md) and the [CODING guide](CODING.md).

iTowns has been redesigned from this [early version](https://github.com/iTowns/itowns-legacy).

## Licence

iTowns is dual-licenced under Cecill-B V1.0 and MIT.
Incorporated libraries are published under their original licences.

See [LICENSE.md](LICENSE.md) for more information.

## Maintainers

iTowns is an original work from French IGN, [MATIS research
laboratory](http://recherche.ign.fr/labos/matis/). It has been funded through
various research programs involving the French National Research Agency, Cap
Digital, UPMC, Mines ParisTec, CNRS, LCPC and maintained by several organizations
along the years (IGN, Oslandia, AtolCD, CIRIL Group). It has also received contributions from people [listed
here](CONTRIBUTORS.md).

iTowns is currently maintained by [IGN](http://www.ign.fr) and
[CIRIL Group](https://www.cirilgroup.com/en/). 

Contributions in any forms and new contributors and maintainers are welcome. Get in touch with us if you are interested :)

The governance of the project is open and explicited [here](https://github.com/iTowns/itowns-governance).

[![IGN](./img/logo_ign.png)](https://www.ign.fr)
[![CIRIL Group](./img/CIRIL_Group_logo.png)](https://www.cirilgroup.com/en/)
