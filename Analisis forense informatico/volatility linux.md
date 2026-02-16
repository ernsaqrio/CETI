export VOLATILITY_PLUGINS=.

export VOLATILITY_PROFILE=LinuxCentOSx64

export VOLATILITY_LOCATION=file://memoria.lime

  

[vol.py](http://vol.py) linux_banner

  

unset VOLATILITY_PLUGINS

[vol.py](http://vo.py) --plugins=. linux_banner

  

linux_cpuinfo

linux_mount exec ro/rw

linux_enumerates_file

linux_find_file

linux_recover_file_system

gdb
