.DEFAULT_GOAL := build
SHELL:=/bin/bash

clean:
	rm -rf ./dist/*

build:
	mkdir -p dist
	env
	echo BUILDING verifier for ${GOOS}/${GOARCH}
	go build -buildmode=c-shared -o $$OUTFILE verifier.go || exit 1 
	@[ "${CHOWNPERMS}" ] && chown $$CHOWNPERMS dist
	@[ "${CHOWNPERMS}" ] && chown $$CHOWNPERMS dist/*
