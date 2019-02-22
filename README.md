# Spatial Temporal Asset Catalog (STAC) Validator

[![CircleCI](https://circleci.com/gh/sparkgeo/stac-validator.svg?style=svg)](https://circleci.com/gh/sparkgeo/stac-validator)

This utility allows users to validate STAC json files against the [STAC](https://github.com/radiantearth/stac-spec) spec.

It can be installed as command line utility and passed either a local file path or a url along with the STAC version to validate against. The tool also supports validating against local schemas.

## Requirements

* Python 3.6
    * Requests
    * Docopt

## Example

```bash
pip install .
stac_validator --help

Description: Validate a STAC item or catalog against the STAC specification.

Usage:
    stac_validator <stac_file> [--spec_dir STAC_SPEC_DIR] [--version STAC_VERSION] [--threads NTHREADS] [--verbose] [--timer] [--log_level LOGLEVEL]

Arguments:
    stac_file  Fully qualified path or url to a STAC file.

Options:
    -v, --version STAC_VERSION   Version to validate against. [default: master]
    -h, --help                   Show this screen.
    --spec_dir STAC_SPEC_DIR     Path to local directory containing specification files [default: None]
    --threads NTHREADS           Number of threads to use. [default: 10]
    --verbose                    Verbose output. [default: False]
    --timer                      Reports time to validate the STAC (seconds)
    --log_level LOGLEVEL         Standard level of logging to report. [default: CRITICAL]
    
stac_validator https://cbers-stac.s3.amazonaws.com/CBERS4/MUX/057/122/catalog.json -v v0.5.2
```
