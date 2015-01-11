`soltool` is a CLI for interacting with Flash ".sol" (Local Shared Object) files.

soltool provides the following commands:

view
----

Usage:
```
soltool [--level LEVEL] [--debug] view [FILE] [--raw] [--sdat]
```
Emits the contents of the FILE as a json dictionary.  If --raw is passed,
pprint/repr instead.  If --sdat is passed, decode the SDAT encoded amf payload.

get-encoding
------------

Usage:
```
soltool [--level LEVEL] [--debug] get-encoding [FILE]
```
Emits the AMF encoding version for FILE to stdout (e.g., "0" or "3")

check
-----

Usage:
```
soltool [--level LEVEL] [--debug] check [FILE] [--out OUTFILE]
```
Sanity checks whether FILE can be reserialized without errors.
Optional OUTFILE specifies a filename to write the reserialized sol contents.

find-recent
-----------

Usage:
```
soltool [--level LEVEL] [--debug] find-recent [--maxage SECONDS]
```

Searches known flash cookie storage object locations, and emits any that have been
modified in the last `--maxage` seconds (default: 2h)

Example:
```
$ soltool find-recent

/home/pete/.macromedia/Flash_Player/#SharedObjects/Y2NDTGYB/thelastdoor.com/swf/extra1/dnff843ax81.swf/log.txt.sol
/home/pete/.macromedia/Flash_Player/#SharedObjects/Y2NDTGYB/thelastdoor.com/swf/extra1/dnff843ax81.swf/Flox.ON2BkMxSaXggeLzP.sol
/home/pete/.macromedia/Flash_Player/#SharedObjects/Y2NDTGYB/thelastdoor.com/swf/extra1/dnff843ax81.swf/savegame.sol
/home/pete/.macromedia/Flash_Player/#SharedObjects/Y2NDTGYB/thelastdoor.com/swf/extra1/dnff843ax81.swf/Flox.RestSer#/vice.queue.ON2BkMxSaXggeLzP.sol
```

edit
----

Usage:
```
soltool [--level LEVEL] [--debug] edit [FILE]
```

Opens FILE in your preferred $EDITOR, saving changes back to FILE

Note this feature is highly experimental and many complex types
(byte arrays, vectors, etc) may fail to deserialize or reserialize properly.
