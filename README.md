# Mongoose-Embedded-Networking-Library-on-nRF51-and-nRF52
Running Mongoose, the most popular open source embedded web server and networking library, on nRF51/nRF52 Development Kits.

nRF5 IoT SDK uses LwIP which is TCP/IP stack for embedded systems. LwIP was already supported by Mongoose, so, no real porting was 
required. Only adjust LwIP client code a bit (make it handle IPv6 connections correctly). Then put it all together by providing the right
compiler flags.

We're going to modify a TCP server example shipped with the SDK. It's located in examples/iot/tcp/server .

Mongoose is distributed as a single C source file, plus C header. Adding it to your project is just a matter of adding a single file 
mongoose.c and providing a few compile flags. For nRF51, the bare minimum is: -DCS_PLATFORM=CS_P_NRF51,
And for nRF52, it is, -DCS_PLATFORM=CS_P_NRF52.
