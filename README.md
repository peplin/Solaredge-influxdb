SolarEdge InfluxDB monitor
==========================

this is a simple python tool to export SolarEdge inverter data to
an InfluxDb <https://www.influxdata.com/time-series-platform/influxdb/> for monitoring purposes. It works by reading the inverter
data from a SolarEdge inverter that has its ModBusTCP interface activated.
It then connects via TCP and reads the SunSpec modbus registers via ModBusTCP.
It requires Python 3.6+ to run.
Development was done against an SolarEdge SE7K inverter, let me know if it works with other types!

Usage:
------
`./solaredge.py [inverter IP]`

In addition, you can specify additional flags to customize the tool:
* `--influxdb <host or ip>` specifies the IP or hostname of the InfluxDb (default localhost)
* `--influxport <port>` specifies the port InfluxDb is running on (default 8086)
* `--unitid <id>` specifies the ModBus ID used by the inverter (default 1)
* `--port <port>` specifies the ModBus TCP port to connect to (default 502)
* `-d` or `--debug` activates debug logging, adding an additional -d includes aioinflux logging
* `-p <x>` or `--period <x>` record data every <x> seconds (default 5)