# power_monitor
Power monitor for a repeater. Developed specifically for the [SR5MS M17 repeater](https://przemienniki.net/przemienniki/70cm/SR5MS?setlang=en) in Poland. The device hasn't been tested yet.<br>
<img src="https://user-images.githubusercontent.com/44336093/184401034-85ec8cce-7844-4971-b8fa-7ef0ffc827f1.png" alt="drawing" width="500"/>

# Sensor
The sensor recommended to be used with this board is [Bird 4D100](https://www.steampoweredradio.com/pdf/bird/catalogs/Bird%20Thruline%20Power%20Sensors%20Catalog%201978.pdf) (for the 70cm band). Other sensors with 30μA range can be used, others may require R3/R5 value change. NOTE: the sensor is not a directional coupler - there's an RF detection circuitry inside the can which outputs current as a function of power (two outputs: incident and reflected power).<br>

# Operation
This device is well suited for constant envelope modulations like the n-FSK or analog FM. The bigger the PAPR, the bigger the measurement error. SWR value is calculated based on instantanous power measurement.<br>
0..30μA current from the sensor generates a voltage drop at R3 (and R5) giving 0..42mV voltage range. This voltage is amplified by U1 with a gain of 78. This produces up to 3.28V at the output of the amp. It is then measured by the ADC in U4 and the power and SWR values are calculated. The result is displayed on an LCD.

# Software
In development. The file with the pinout for CubeMX (>=6.6.1) is in the main directory: `SWR_monitor.ioc`.
