IPMItool Commands Cheat Sheet

General IPMItool Commands

ipmitool ---> help	Shows help info for IPMItool
ipmitool mc info---> Checks firmware version
ipmitool mc reset [warm/cold]	---> Resets the management controller
ipmitool fru print---> Displays field-replaceable-unit details

Sensor Output IPMItool Commands

ipmitool sdr list ---> 	List all sensor names on the system. Each sensor will be mapped to its corresponding sensor number
ipmitool sdr type list ---> List all sensor types on the system.
ipmitool sdr type Fan	 ---> List all fan type sensors on the system.
ipmitool sdr type "Power Supply"	---> List all power supply type sensors on the system.
ipmitool sdr type Temperature  ---> List all temperature type sensors on the system.

Chassis Commands

ipmitool chassis status ipmitool chassis identify []	---> Turns on front panel identify light
ipmitool [chassis] power soft	---> A soft-shutdown via acpi
ipmitool [chassis] power cycle --->	A combination of a hard power off, 1-second wait, then power on
ipmitool [chassis] power off	---> A hard power off
ipmitool [chassis] power on ---> A hard power on
ipmitool [chassis] power reset	---> A hard reset

Modify Boot Device Commands

ipmitool chassis bootdev pxe	---> Modify the boot order to boot pxe first
ipmitool chassis bootdev cdrom	---> Modify the boot order to boot cdrom first
ipmitool chassis bootdev bios 	---> Modify the boot order to boot bios first

Logging IPMItool Commands

ipmitool sel info	---> Returns general information on system event logs
ipmitool sel list	----> Returns a list of system event logs
ipmitool sel elist	---> Returns a list of system event logs cross-referenced with sensor data logs
ipmitool sel get ID	---> Returns detailed information on a particular event log (use event ID to specify which log)
ipmitool sel clear	---> Clear event logs
