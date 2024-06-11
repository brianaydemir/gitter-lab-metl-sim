.PHONY: all build clean

ROSETTA_INSTALLERS ?= /staging/$(shell whoami)/rosetta/3.13
NOW := $(shell date +"%Y%m%d-%H%M")

all: build

build: metl-sim-$(NOW).sif

clean:
	rm -rf build.{log,out,err}
	rm -rf metl-sim-*.sif

# --------------------------------------------------------------------------

%-$(NOW).sif: %.def
	apptainer build -F -B ${ROSETTA_INSTALLERS}:/rosetta-installers $@ $<
