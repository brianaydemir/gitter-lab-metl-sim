# Apptainer Image for metl-sim

Reference: https://github.com/gitter-lab/metl-sim


## Basic Instructions

- Set `ROSETTA_INSTALLERS` to the directory containing
  `rosetta_bin_linux_3.13_bundle.tgz`. This can be done directly
  in the `Makefile` or via an environment variable.

- Run `make build`.


## Uploading the SIF File to a Harbor Registry

    apptainer registry login --username {username} docker://{registry}

    apptainer push {sif_file} oras://{registry}/{project}/{repo}:{tag}


## CHTC-Specific Notes

Submit `build.sub` as an interactive job to run the build on a dedicated
build node. Do **not** build the image on an access point.

Copy the resulting `.sif` file to your directory in `/staging`.
