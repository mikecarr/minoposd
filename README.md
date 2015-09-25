Retrieved from https://code.google.com/p/minoposd/source/browse/trunk/ on 9/25/15

minOPOSD is an add-on to the ArduCamOSD/MinimOSD-Extra project.

With this add-on you can use the MinimOSD hardware in combination with a flight control from OpenPilot like CC3D and Revo which uses UAVTalk as communication protocol.

It is intended as a temporary solution for the FPV guys till the OpenPilot OSD is available.

This project is GNU GPL v3 and using it is at your own risk.

Everything about OpenPilot: http://www.openpilot.org/

The minOPOSD discussion: http://forums.openpilot.org/topic/15573-openpilot-boards-feeding-minimosd-via-uavtalk/

The original ArduCamOSD code: http://code.google.com/p/arducam-osd/

The original MinimOSD-Extra code: http://code.google.com/p/minimosd-extra/

## Requirements
* Git to clone source
* Download Arduino Software (arduion.cc)

## Get Source
Take the libs from one of the two other original projects http://code.google.com/p/arducam-osd/ and http://code.google.com/p/minimosd-extra/ .

```
git clone https://github.com/mikecarr/minoposd
```

## Configuring

edit OSD_Config.h

```
#define FLIGHT_BATT_ON_MINIMOSD
#define ANALOG_RSSI_ON_MINIMOSD  ( I use RangeLink analog rssi output , 0-3.3v range )
#define AH_BETTER_RESOLUTION
```

FlightBatt.h:
```
#define VOLTAGE_PIN            6
 #define CURRENT_PIN            7
#define REF_VOLTAGE            5            // DEFAULT: a built-in reference, equal to 5 volts on the ATmega328
#define LOW_VOLTAGE            13.2            // filter start value for 4s LiPo
#define VOLT_DIV_RATIO            15.70            // Attopilot 90A/50v sensor Vref 5V based
#define CURR_AMP_PER_VOLT        27.32            // Vref 5V based: This is the start value for calibrating a +-90A       Current Sensor(AC/DC)Attopilot  Sensitivity: 36.6mV/A
#define CURR_AMPS_OFFSET        0.0000
```

FlighBatt.ino:
```
change analogReference from Internal to Default:

    analogReference(DEFAULT);
```
AnalogRSSI.h:
```
#define RSSI_PIN            1           // A1 is pin 24
#define REF_VOLTAGE            5            // DEFAULT: a built-in reference, equal to 5 volts on the ATmega328
```
AnalogRSSI.ino:
```
change analogReference from Internal to Default:
    analogReference(DEFAULT);
```

