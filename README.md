# A product for temperature measument

SN8P2501D

We have realized I2C interface, which can be used for EEPROM communication.

## Address content in EEPROM

| EEPROM Address | content |
| -------------- | -------------------- |
| 0x1FFA | INITIAL_TIME_H |
| 0x1FFB | INITIAL_TIME_L |
| 0x1FF8 | FRONT_DELAY_TIME |
| 0x1FF9 | SAMPLE_TIME_GAP |
| 0x1FFE | CURRENT_TEMPERATURE_ADD_H |
| 0x1FFF | CURRENT_TEMPERATURE_ADD_L |

## Calculate equation

Current time={INITIAL_TIME_H,INITIAL_TIME_L}+{FRONT_DELAY_TIME}+{SAMPLE_TIME_GAP}*({CURRENT_TEMPERATURE_ADD_H,CURRENT_TEMPERATURE_ADD_L}-1) minute

TEMPERATURE={*CURRENT_TEMPERATURE_ADD_H}.{*CURRENT_TEMPERATURE_ADD_L} <sup>o</sup>C

## Special addresse for Bluetooth
from 0x1FE0 to 0x1FF5

## Sample time can be variated with temperature
when the timeperature is > 48<sup>o</sup>C or < 5<sup>o</sup>C
T_sample=1/2*SAMPLE_TIME_GAP
