# Netron Export

![alt text](overview.png)

[netron](https://netron.app) is a nice viewer for machine learning models.
It is however written in Javscript and does not expose its export to PNG/SVG functionalities in its Python interface or as a command line.

This script aims at enabling an automated saving of the graph as PNG or SVG file.
In a nutshell, it works by opening a browser and simulating user interactions (opening the menu, clicking on the right link that will download the model) and then moving the downloaded file to the target location.

## Requirements

This script is mostly based on the [netron](https://github.com/lutzroeder/netron) and [playwright](https://github.com/microsoft/playwright-python) packages.
Since it relies on the name of HTML elements that might change in the future, we fix the netron version.

To install the required packages, execute:
```python
git clone https://github.com/raphael-prevost/netron-export.git
pip install ./netron-export
```

Alternatively, you can directly install from GitHub with
```bash
pip install git+https://github.com/raphael-prevost/netron-export
```

Playwright might also need to install dependencies separately, you can do it via:
```
playwright install --with-deps chromium
```

## Usage

To execute the script, simply run
```
netron_export --output ./output.svg ./my_model.onnx
```
More generally, you can run
```
netron_export -h
```
to see help on all available parameters.

## Running Tests

The tests have a couple of extra requirements that need to be installed:
```
pip install -r requirements-test.txt
```
Then you can run
```
pytest tests
```
and make sure all tests pass.

## Contact

This work was supported by ImFusion GmbH (Munich, Germany).

[Website](https://www.imfusion.com/) |  [LinkedIn](https://www.linkedin.com/company/imfusion/) | [X (formerly Twitter)](https://twitter.com/ImFusionGmbH)


