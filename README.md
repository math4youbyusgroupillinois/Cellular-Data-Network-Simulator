# Cellular Data Network Simulator

Cellular Data Network Simulator is dedicated WiFi network to monitor network usage and simulate network link conditions for mobile applications. It uses well established technologies: OpenWrt, tc, iptables and CloudShark.

## Features

* Easy to use web and mobile interface
* Simulate: bandwidth, delay, loss, corruption, occasional loss of signal
* Can capture the traffic and send it to CloudShark
* Apply limits per-device
* Works well in environment with multiple devices and multiple testers
* Works well as virtual machine bridged with separate wireless network

## Requirements

* OpenWrt device running on latest trunk release - can be router or virtual machine
* Two network interfaces - one for WAN and one for WIFI/LAN

## Installation

The are a few simple steps to install Cellular Data Network Simulator:

1. Install cdns:

        opkg update
        opkg install https://github.com/Polidea/Cellular-Data-Network-Simulator/releases/download/0.5/cdns_0.5-0_all.ipk
        
    Installation of Cellular Data Network Simulator replaces default Luci webpage. The Luci can be accessed using: http://ip-address/index-old.html

2. Configure:

        vim /etc/config/cdns

    By default there are 5 profiles: Full, HSDPA, Edge, GPRS and Disabled.

3. Start the service:

        /etc/init.d/cdns enable
        /etc/init.d/cdns start
        
    That simply enables and starts the service,
        
4. Start the uhttpd daemon:

        /etc/init.d/uhttpd enable
        /etc/init.d/uhttpd start

    If you didn’t do it before you have to enable and start the uhttpd daemon.
    
5. Start using:

    Simply open: http://ip-address/.

## Uninstallation

        /etc/init.d/cdns stop
        opkg uninstall cdns

## Compile yourself

1. Download sources:

        git clone <repo-path>
        
2. Build the package yourself:

        make
        
3. For more options view help:

        make help


## License

       BSD 2-Clause License    

## Changelog

* First public release (25.11.2013)
