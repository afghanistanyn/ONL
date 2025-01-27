Getting Started
------------------------------------------------
To install and run ONL you need is an ONL Compatible switch (see
http://opennetlinux.org/hcl) and the ONL installer binary.  Every
ONL compatible switch ships with the ONIE installer environment installed
which gives you a multitude of ways of getting ONL installed on your switch.

We document the easiest way here (manual install) but the http://onie.org website
contains a variety of installation methods including via USB, over the network,
and even over NFS.


ONL Manual Install
------------------------------------------------
1) Attach a serial terminal to the switch
2) Boot switch and hit return to go to ONIE''s interactive mode
    2a) You must wait until after uboot has finished loading; if you
        accidentally interupt uboot first, just run `boot` to continue
        booting into ONIE
3) Download the ONL installer from http://opennetlinux.org and run it by hand

Expected Serial Console Output (from an QuantaMesh LB9, other switches ouput will vary):

        U-Boot 2010.12 (Oct 08 2013 - 17:11:37)

        CPU:   8541, Version: 1.1, (0x80720011)
        Core:  Unknown, Version: 2.0, (0x80200020)
        Clock Configuration:
               CPU0:825  MHz, 
               CCB:330  MHz,
               DDR:165  MHz (330 MT/s data rate), LBC:41.250 MHz
        CPM:   330 MHz
        L1:    D-cache 32 kB enabled
               I-cache 32 kB enabled
        I2C:   ready
        DRAM:  Detected UDIMM TS128MSD64V3A
        Detected UDIMM(s)
        DDR: 1 GiB (DDR1, 64-bit, CL=2.5, ECC off)
        FLASH: 64 MiB
        L2:    256 KB enabled

        LB9 U-Boot
          Product Name          : LB9
          Model Name            : QUANTA LB9
          Serial Number         : QTFCA63280001
          Part Number           : 1LB9BZZ0STQ
          Label Revision Number : 1
          Hardware Version      : 1.0
          Platform Version      : 0xb901 
          Release Date          : 2013/7/5
          MAC Address           : 08:9e:01:ce:bd:2d
        Set ethaddr MAC address = 08:9e:01:ce:bd:2d
        In:    serial
        Out:   serial
        Err:   serial
        Net:   TSEC0: PHY is Broadcom BCM5461S (2060c1)
        TSEC0
        IDE:   Bus 0: OK 
          Device 0: Model: 4GB CompactFlash Card Firm: Ver6.04J Ser#: CDE207331D0100001484
                    Type: Hard Disk
                    Capacity: 3811.9 MB = 3.7 GB (7806960 x 512)
        Hit any key to stop autoboot:  0 
        ## Error: "nos_bootcmd" not defined
        Loading Open Network Install Environment ...
        Platform: powerpc-quanta_lb9-r0
        Version : 1.5.2-20131008154633
        WARNING: adjusting available memory to 30000000
        ## Booting kernel from Legacy Image at 04000000 ...
           Image Name:   quanta_lb9-r0
           Image Type:   PowerPC Linux Multi-File Image (gzip compressed)
           Data Size:    3479390 Bytes = 3.3 MiB
           Load Address: 00000000
           Entry Point:  00000000
           Contents:
              Image 0: 2762740 Bytes = 2.6 MiB
              Image 1: 707380 Bytes = 690.8 KiB
              Image 2: 9254 Bytes = 9 KiB
           Verifying Checksum ... OK
        ## Loading init Ramdisk from multi component Legacy Image at 04000000 ...
        ## Flattened Device Tree from multi component Image at 04000000
           Booting using the fdt at 0x434f378
           Uncompressing Multi-File Image ... OK
           Loading Ramdisk to 2ff53000, end 2ffffb34 ... OK
           Loading Device Tree to 03ffa000, end 03fff425 ... OK
        Cannot reserve gpages without hugetlb enabled
        setup_arch: bootmem
        quanta_lb9_setup_arch()
        arch: exit
                     
        ONIE: Using DHCPv4 addr: eth0: 10.7.1.10 / 255.254.0.0
        discover: installer mode detected.  Running installer.

        Please press Enter to activate this console. ONIE: Using DHCPv4 addr: eth0: 10.7.1.10 / 255.254.0.0
        ONIE: Starting ONIE Service Discovery

        To check the install status inspect /var/log/onie.log.
        Try this:  tail -f /var/log/onie.log

Now press RETURN here to jump into ONIE''s manual installer mode.  You should see:

        ** Installer Mode Enabled **

        ONIE:/ # 

Then simply download the latest ONL installer from the website and run it.

        ONIE:/ # wget http://opennetlinux.org/binaries/latest.installer
        Connecting to opennetlinux.org (107.170.237.53:80)
        latest.installer     100% |*******************************|   164M  0:00:00 ETA
        ONIE:/ # sh latest.installer 
        Open Network Installer running under ONIE.
        Installer Version: Open Network Linux e148b7a (powerpc.all,2014.05.21.18.57,e148b7a90131c07eb8d49f74316baf8f2aae92c6)
        Detected platform: powerpc-quanta-lb9-r0
        Installing in standalone mode.
        Unpacking Open Network Linux installer files...
        onl.powerpc-as4600-54t.loader
        onl.powerpc-as5600-52x.loader
        ...

