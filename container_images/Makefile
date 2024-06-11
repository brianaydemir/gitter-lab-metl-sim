.PHONY: all build clean

ROSETTA_INSTALLERS ?= /staging/$(shell whoami)/rosetta
NOW := $(shell date +"%Y%m%d-%H%M")

all: build

build: metl-sim-base-$(NOW).sif

clean:
	rm -rf build.{log,out,err}
	rm -rf metl-sim-base-*.sif

# --------------------------------------------------------------------------

%-$(NOW).sif: %.def
	apptainer build -F -B ${ROSETTA_INSTALLERS}:/rosetta-installers $@ $<
