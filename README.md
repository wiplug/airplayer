AirPlayer
================================================================================

Command-line AirPlay video client for Apple TV

[![Gem Version](https://badge.fury.io/rb/airplayer.png)](http://badge.fury.io/rb/airplayer)
[![Build Status](https://travis-ci.org/Tomohiro/airplayer.png?branch=master)](https://travis-ci.org/Tomohiro/airplayer)
[![Stillmaintained](http://stillmaintained.com/Tomohiro/airplayer.png)](http://stillmaintained.com/Tomohiro/airplayer)
[![Dependency Status](https://gemnasium.com/Tomohiro/airplayer.png)](https://gemnasium.com/Tomohiro/airplayer)
[![Code Climate](https://codeclimate.com/github/Tomohiro/airplayer.png)](https://codeclimate.com/github/Tomohiro/airplayer)


---


Requirements
-------------------------------------------------------------------------------

- OSX or Ubuntu
- Ruby 1.9.3 or later
- AppleTV 2G or later
- [youtube-dl](http://rg3.github.com/youtube-dl/)


### Ubuntu

```sh
$ sudo apt-get install rdnssd libavahi-compat-libdnssd-dev
```


Installation
--------------------------------------------------------------------------------

### RubyGems

```sh
$ gem install airplayer
```

### Bundler

```sh
$ git clone git://github.com/Tomohiro/airplayer.git
$ cd airplayer
$ bundle install --deployment
```


Usage
--------------------------------------------------------------------------------

### Play online video

```sh
$ airplayer play http://heinlein.local/Movies/AKIRA.m4v

 Source: http://heinlein.local/misc/Movies/AKIRA.m4v
  Title: AKIRA.m4v
 Device: Apple TV (10.0.1.2)
   Time: 00:04:25 |=                                              | 3% Streaming
```

### Play video

```sh
$ airplayer play '~/Movies/Trailers/007 SKYFALL.mp4'

 Source: http://10.0.1.6:7070
  Title: SKYFALL.mp4
 Device: Apple TV (10.0.1.2)
   Time: 00:00:20 |=====                                         | 11% Streaming
```

### Play all video in specific directory

```sh
$ airplayer play ~/Movies/Trailers

 Source: http://10.0.1.6:7070
  Title: 007 Casino Royale.mp4
 Device: Apple TV (10.0.1.2)
   Time: 00:02:33 |==============================================| 100% Complete

 Source: http://10.0.1.6:7070
  Title: 007 Quantum Of Solace.mp4
 Device: Apple TV (10.0.1.2)
   Time: 00:02:01 |==============================================| 100% Complete

 Source: http://10.0.1.6:7070
  Title: 007 SKYFALL.mp4
 Device: Apple TV (10.0.1.2)
   Time: 00:02:36 |==============================================| 100% Complete
```

### Play video podcast XML

Example: CNN video podcast

```sh
$ airplayer play http://rss.cnn.com/services/podcasting/cnnnewsroom/rss.xml

 Source: http://rss.cnn.com/~r/services/podcasting/cnnnewsroom/rss/~5/z7DirHubdP0/exp-travel-insider-hilton-head-island.cnn.m4v
  Title: exp-travel-insider-hilton-head-island.cnn.m4v
 Device: Apple TV (10.0.1.2)
   Time: 00:00:44 |============                                  | 39% Streaming
```


### Repeat play

Repeat one

```sh
$ airplayer play '~/Movies/Trailers/007 SKYFALL.mp4' --repeat
```

Repeat all

```sh
$ airplayer play '~/Movies/Trailers' --repeat
```


### Shuffle play

```sh
$ airplayer play '~/Movies/Trailers' --shuffle
```


Supported MIME types
--------------------------------------------------------------------------------

[AirPlay Overview - Configuring Your Server](http://developer.apple.com/library/ios/#documentation/AudioVideo/Conceptual/AirPlayGuide/PreparingYourMediaforAirPlay/PreparingYourMediaforAirPlay.html)

File extension | MIME type       | Ruby `mime-types`
-------------- | --------------- | -----------------------------
.ts            | video/MP2T      | video/MP2T
.mov           | video/quicktime | video/quicktime
.m4v           | video/mpeg4     | video/vnd.objectvideo
.mp4           | video/mpeg4     | application/mp4, video/mp4


LICENSE
--------------------------------------------------------------------------------

&copy; 2012 - 2013 Tomohiro TAIRA.
This project is licensed under the MIT license.
See LICENSE for details.
