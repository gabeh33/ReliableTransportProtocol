# Reliable Transport Protocol

This project builds a transport protocol that will deliver packets in order and reliably, regardless of if packets are sent out of order, delayed, duplicated, or dropped. 

## Description 

This project was designed to gain an understanding of how TCP or TCP like protocols work when they are built on top of UDP. Packets can be duplicated, reordered, dropped, delayed, all on top of a network with low bandwidth and/or high latency. I wrote the code in both 3700send and 3700recv. 3700recv is ran first, and and then 3700send is ran and reads input from STDIN. The data must be sent from 3700send to 3700recv and arrive exactly how it was sent. Information about how to test it is given below. The goal of this project is not to implement all of TCP, however many ideas from TCP helped me in this project such as slow start, ACKs, cwnd, etc. 

## Getting Started


### Installing

* Included with the source code is a Vagrant file, which can be used to access different ways to run the program. 

### Executing program

* Run the Vagrant file using any of multiple methods. 
* To configure the unreliable network inside the VM created by the Vagrant file, use 
```
$ netsim [--bandwidth <bw-in-mbps>] [--latency <latency-in-ms>] [--delay <percent>] [--drop <percent>] [--reorder <percent>] [--duplicate <percent>]
```
* In order to reset the settings, use 
```
$ netsim
```
* Then to test the program, use the command 
```
$ nettest [--live] [--size {small,medium,large,huge}] [--timeout TIMEOUT]
```
* Where --live instructs the script to echo STDERR to the console, --size denotes the amount of data to send, and --timeout is the max number 
of seconds to run the program.
* Alternatively to run a whole suite of tests, use the command
```
testall
```

## Authors

Gabe Holmes
* https://www.linkedin.com/in/gabe-holmes/
* holmes.ga@northeastern.edu 

## Version History

* 0.1
    * Initial Release
