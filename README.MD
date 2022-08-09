# Voron V0 Display on CANBUS

![Working](/Images/replaceme.jpg)
Wiring and config to run the SKR E3 V2 over CAN

## Setup Steps

### Compile Toolboard Firmware
- ssh to your pi console
- CD to the klipper directory
```
cd klipper
```
- Run MAKE Clean
```
make clean
```
- open menuconfig
```
make menuconfig
```
- Set the following options for CANBUS connection  
    Note: If you already have a CAN implementation set the CANBUS speed to match your existing configuration. Common speeds are 250000 and 500000

![Config](/images/SKRE3V2_menuconfig.jpg)

-Run make
```
make
```
-When the make is complete connect to the klipper host with SFTP 
Navigate to the Klipper out file
```
 /home/pi/klipper/out
```
- Copy the Klipper.bin file to your local machine 
- Rename the file to firmware.bin
- Transfer firmware.bin to your microSD card
- Replace the microSD card into the Mini E3.
- Power on the system. SKR will automatically update with the Klipper firmware.

## Wiring Diagram

    Note: The MCP2551 does not have 120 ohm resistors. If this is the only device on your CANBUS you will need to wire a 120 ohm resistor between CANH and CANL at the MCP2551 connector.  You CANBUS should measure 60 ohms between CAN H and CAN L with all the devices connected. ( measure while powered off) 

![Wiring](Images/V0Display_CAN_Wiring.jpg)      

![V0 Display Com pins](/Images/V0_Display_com_pins.jpg)

![Display Wiring IMage](/Images/V0_Display_Wiring.jpg)

![MPC2551 Wiring](/Images/MCP2551_CAN_Tran_wiring.jpg)


## Links  

  [MCP2551 board](https://www.aliexpress.com/item/2255800362518857.html?spm=a2g0o.order_list.0.0.21ef1802WJAiGd)
  
  [SKR Mini E3 V2](https://github.com/bigtreetech/BIGTREETECH-SKR-mini-E3/tree/master/hardware/BTT%20SKR%20MINI%20E3%20V2.0/Hardware)
  
  [Maz0r CanBus Configuratuion and troubleshooting guides](https://maz0r.github.io/klipper_canbus/)
