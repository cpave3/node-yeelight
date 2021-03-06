# node-yeelight
[![Build Status](https://travis-ci.org/cpave3/node-yeelight.svg?branch=master)](https://travis-ci.org/cpave3/node-yeelight)

node-yeelight is a 0 dependency solution for controlling Xiaomi Yeelights. There are already a number of other solutions 
available, but they were not exactly what I wanted, so I made another one to be better than all the others.

<p align="center">
  <!-- Why isn't there Markdown for centered images? -->
  <img src="https://imgs.xkcd.com/comics/standards.png" alt="Competing standards">
</p>


## How is this any different?

Well it has less functionality for a start. All of the other ones I saw came bundled with an SSDP solution. 
I already have my own SSDP solution [over here](https://github.com/cpave3/node-ssdp) so I didn't want to pull in another one. 
I just wanted something to interface with the lights. This solution offers a 1:1 implementation 
of the [official docs from Xiaomi](http://www.yeelight.com/download/Yeelight_Inter-Operation_Spec.pdf) without 
any 3rd party dependencies.

To actually find the lights you will need an SSDP implementation of you don't know the IP of your light. 
As mentioned above,[I have taken care of that too](https://github.com/cpave3/node-ssdp) but because I'm 
not building it into this package, you can use whichever one you like. Or write your own.

## How do I use this?

Simply require and instantiate the package as a class, passing in the ip address and port of the light as an object.

```
const Yeelight = require('node-yeelight');
const yee1 = new Yeelight({ ip: 0.0.0.0, port: 55443 });
```

You can now call any of the operations from the official docs on this instance.

