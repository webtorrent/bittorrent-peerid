# bittorrent-peerid [![travis](https://img.shields.io/travis/fisch0920/bittorrent-peerid.svg)](https://travis-ci.org/fisch0920/bittorrent-peerid) [![npm](https://img.shields.io/npm/v/bittorrent-peerid.svg)](https://npmjs.org/package/bittorrent-peerid) [![downloads](https://img.shields.io/npm/dm/bittorrent-peerid.svg)](https://npmjs.org/package/bittorrent-peerid)

#### Maps a Bittorrent Peer ID to its corresponding client type and version.

[![browser support](https://ci.testling.com/fisch0920/bittorrent-peerid.png)](https://ci.testling.com/fisch0920/bittorrent-peerid)

Also works in the browser with [browserify](http://browserify.org/)!

This module is used by [WebTorrent](http://webtorrent.io).

## install

```
npm install bittorrent-peerid
```

## usage

```js
var peerid = require('bittorrent-peerid')
var parsed = peerid('-AZ2200-6wfG2wk6wWLc')

console.log(parsed.client, parsed.version)
```

The `parsed` peerid object looks like this:

```js
{
  client: 'Vuze',
  version: '2.2.0.0'
}
```

bittorrent-peerid can parse peer ids encoded in the following formats:
* a 20-byte Buffer
* a 40-character hex string
* an arbitrarily-sized human-readable utf8 string (must decode to a 20-byte Buffer)

If an unknown peer id is passed in, the returned client will be `unknown`.

## todo

* ~~Support known Azureus-style clients.~~
* ~~Support known Shadow-style clients.~~
* ~~Support known Mainline-style clients.~~
* ~~Support known Custom-style clients.~~
* ~~Recognize BitComet/Lord/Spirit spoofing.~~
* Full support for client version parsing.
* Full support for customized client version schemes.
* Support unknown clients that conform to either the Azureus or Shadow-style conventions.

## credit

This module is based heavily on the BTPeerIDByteDecoderDefinitions class from [Azureus](http://sourceforge.net/projects/azureus/) (Vuze). Related resources include:
* [BitTorrent Specification](http://wiki.theory.org/BitTorrentSpecification)
* [Transmission](http://transmission.m0k.org/trac/browser/trunk/libtransmission/clients.c)
* [g3peerid](http://rufus.cvs.sourceforge.net/rufus/Rufus/g3peerid.py?view=log)
* [Shareaza](http://shareaza.svn.sourceforge.net/viewvc/shareaza/trunk/shareaza/BTClient.cpp?view=markup)
* [libtorrent](http://libtorrent.rakshasa.no/browser/trunk/libtorrent/src/torrent/peer/client_list.cc)

## license

MIT. Copyright (c) Travis Fischer.
