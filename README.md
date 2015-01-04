`soltool` is a CLI for interacting with Flash ".sol" (Local Shared Object) files.

soltool provides the following commands:

view
====

Usage:

  soltool [--level LEVEL] [--debug] view [FILE] [--raw]

Emits the contents of the FILE as a json dictionary.  If --raw is passed,
pprint/repr instead.

get-encoding
============

Usage:

  soltool [--level LEVEL] [--debug] get-encoding [FILE]

Emits the AMF encoding version for FILE to stdout (e.g., "0" or "3")

check
=====

Usage:

  soltool [--level LEVEL] [--debug] check [FILE] [--out OUTFILE]

Sanity checks whether FILE can be reserialized without errors.
Optionally, OUTFILE specifies a filename to reserialize to.
