# RS485 relays

This repo is dedicated to various RS485 relays available on AliExpress. The below information is based on the Chinese documentation provided by the sellers.

Usually the default baud rate is 9600 baud, 8 bit, no parity, 1 stop bit.

# 8 channel


## Command structure ##
|Byte| Meaning | Example |
|----|---------|--------|
|1   |Device address. The default address is 1. | 01 |
|2   |Command Id | 05 |
|3   |Relay address, high byte, always 0 | 00 |
|4   |Relay address, low byte | 04 |
|5-6  |Command parameter | FF 00 |
|7-8  | CRC |  CD FB |

Sample command, turn on relay 4:
```01 05 00 04 FF 00 CD FB```

## Device Address ##
The default address is 01. You can permanently update the address to an other value. Connect only one module to the RS485 bus.

| Command            |   Command bytes                           | CRC | Result |
|--------------------|-----------------------------|---|---|
|Get address | ```00 03 00 00 00 01``` | ... | 00 03 02 00 __01__ 44 44  where 01 is the address|
|Set address to 5    |```00 10 00 00 00 01 02 00 05```| ... |
|Set address back to 1    |```00 10 00 00 00 01 02 00 01```| ... |

## Sourcing ##
Can be purchased here: https://www.aliexpress.com/item/4000146850177.html?spm=a2g0s.9042311.0.0.27424c4dwFSQOt

![8 channel RTU module](https://ae01.alicdn.com/kf/Hf868c739f9aa40c0a7a8d67457929e3f0/Modbus-Rtu-8-Channel-12V-Relay-Module-Switch-Input-Output-RS485-TTL-Communication-interface-relay-8.jpg_Q90.jpg_.webp)
