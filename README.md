2 layer pcb version of Shilga's RP2040 Gameboy flash cartridge. Also replaced some components with 

Changes:
-Removed inner layers, instead routed buses and tracks in place of the power planes at the back layer. Also one single signal track is moved to the back layer.
-Replaced 1005 caps with 1608's. JLCPCB doesn't do 1005 package in ecomomic PCBA service.
-Added an optional location for AMS1117-3.3 regulator, in case the MCP1825T isn't available. If AMS1117-3.3 is used, JP2 middle pad solder mask should be removed and soldered to supply a constant POWERGOOD signal that enables the level shifters. 

With these three changes, the PCB could be manufactured at 2$ for 5pcs at JLCPCB. Also if PCBA service is needed, it reduces the number of the extended components that add 3$ of setup fee each. 

The RP2040, TXB0108, TXB0102 and the WS2812b are inevitably extended parts at JLCPCB.

Not tested:
-The whole PCB
-JP2 POWERGOOD bypass functionality(keeping IC's enabled at all times may be a problem)
-Replacement of power planes with tracks
-AMS1117-3.3 compatibility

Goals:
-Replacement of TXB level shifters with discrete circuits made of jellybean transistors. This might be difficult because there are 26 data lines that needs to be level shifted and there is little space, too much moving around might be needed. Heck, might even need to use the back layer.
-Replacement of CJ2302 mosfet with a cheaper one. AO3400A might be a candidate.
-Replacement of the diodes with jellybean ones
-Making the whole pcb made of jellybean parts except RP2040
