songdl
======

songdl - A song downloader that uses last.fm to search and download songs

Usage
-----

usage: songdl [-h] [-v] [-f] [-q] query

Download a song from lastfm.

positional arguments:
  query          A string to search for, ie. "Michael Jackson - Beat It"

optional arguments:
  -h, --help     show this help message and exit
  -v, --verbose  Prints verbose messages
  -f, --force    Don't ask any questions, just download the first song or
                 nothing
  -q, --quiet    Don't print any messages. Implies -f

History
-------

I found this method in some message board a long time ago.

From wireshark:
http://api.vk.com/api.php?api_id=525159&method=audio.search&format=json&sig=6400d22d19b875a594c60e7e1a1fb916&test_mode=1&count=10&q=the%20knife%20the%20captain%20(live)

Reverse engineering:
 - Download the crx from https://chrome.google.com/extensions/detail/bbncpldmanoknoahidbgmkgobgmhnafh
 - Unzip the crx
 - Open up javascript/vk.js
 - Look for the following:
       md5hash = MD5(api[0]+'api_id='+api[1]+'count=10format=jsonmethod=audio.searchq='+track+'test_mode=1'+api[2])
