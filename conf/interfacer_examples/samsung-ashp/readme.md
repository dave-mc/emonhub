### SAMSUNG ASHP MIB19N Modbus

Read data from a Samsung Heat Pump or HVAC unit using the [MIM-B19N Modbus module](https://www.samsung.com/uk/support/model/MIM-B19N/). Tested on AE050RXYDEG-EU Gen6 ASHP. Should work for all Samsung HVAC units.

**read_interval:** Interval between readings in seconds

```text
[[SAMSUNG-ASHP-MIB19N]]
    Type = EmonHubMinimalModbusInterfacer
    [[[init_settings]]]
        device = /dev/ttyUSB0
        baud = 9600
        parity = even
        datatype = int
    [[[runtimesettings]]]
        pubchannels = ToEmonCMS,
        read_interval = 20
        nodename = samsung-ashp
        # prefix = sdm_
        [[[[meters]]]]
            [[[[[ashp]]]]]
                device_type = samsung
                address = 1
                registers = 75,74,72,65,66,68,52,59,58,2,79,87,5,89
                names = dhw_temp,dhw_target,dhw_status,return_temp,flow_temp,flow_target,heating_status,indoor_temp,indoor_target, defrost_status,away_status,flow_rate,outdoor_temp,3_way_valve
                scales = 0.1,0.1,1,0.1,0.1,0.1,1,0.1,0.1,1,1,0.1,0.1,1
                precision = 2,2,1,2,2,2,1,2,2,1,1,2,2,1
```
