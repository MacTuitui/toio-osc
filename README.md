# toio-osc
Tools to connect to toio cubes and control them over OSC

## Why?
The idea is that managing Bluetooth Low Energy connections is hard and painful, 
but very important to play with toio cubes. What if there were a way to abstract
everything and use a common OSC API to communicate with the cubes? That's what this
project is trying to do.

## How?

* Install rust
* run `cargo run --release` to compile and run the application

## What is happening?
The application with listen to BTLE events and connects to any toio cube it sees.
Right now it also subscribes to the position ID characteristic and button characteristic.
It will then forward all notifications as OSC packet to the server specified in the code
(right now, `localhost:3333`).
The application will also open a server on port `3334` to listen to OSC messages to then
forward to the cubes. Right now only the `motor` message is implemented and allows you 
to control the cubes around.

## Related projects
See the nannou example [here](https://github.com/MacTuitui/toio-nannou) or 
the processing example [here](https://github.com/MacTuitui/toio_processing) 
for examples on how to use this application.

## Caveats
If you are running Big Sur, you must authorize the terminal application to use 
Bluetooth. 
This has been tested on Mac OS Catalina and Windows 10. More to come soon!
