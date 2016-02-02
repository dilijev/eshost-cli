## eshost-cli

eshost-cli makes it easy to run and compare ECMAScript code uniformly across a number of runtimes. Support for runtimes is provided by the library [eshost](https://github.com/bterlson/eshost). Every host is initialized with the [eshost runtime API](https://github.com/bterlson/eshost#runtime-library) available which provides a uniform way to print, create realms, and eval code. 

See eshost's [supported hosts](https://github.com/bterlson/eshost#supported-hosts) for a list of hosts, download/build locations, and other information.

### Usage

Manage hosts with `eshost host`. Run files across all hosts using `eshost file.js`. Run a quick script using `eshost -e "script"`.

#### Examples

```
npm install -g eshost-cli
eshost --help
eshost host --help
eshost host --add <name> <type> <path to host executable> --args <optional arguments>
eshost -e "Map.length"

## chakra-es6
0

## d8
0

## chakra
0

## spidermonkey
1

## node
0
```

### Managing Hosts

The command `host` is used for managing hosts (see above for some examples). You can --add, --list, and --delete them. Adding a host requires a name, type, and path to the runtime executable. You can optionally pass arguments using --args. The same host can be added multiple times with different --args which makes it easy to compare the output of runtimes given different options (eg. by turning language features on and off).

Console hosts are either provided by the browser vendors or, more likely, built from source.

Host types are [those provided by es-host-wrapper](https://github.com/bterlson/es-host-wrapper#supported-hosts), namely:

* ch
* jsshell
* d8
* jsc
* nashorn
* node
* browser
