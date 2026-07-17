# prime-connect
An unofficial safe method to use BLE in SPIKE Prime Robot without the need to switch to Pybricks or tamper with the firmware!

I've came across this while USB sniffing the SPIKE Prime App via USBPcap. Hope it helps! 

The SPIKE Prime USB communication interface exposes the hub's MicroPython REPL. Through this REPL, it is possible to modify internal hub configuration values:

```py
hub.config["hub_os_handle_bluetooth"] = False
hub.config["hub_os_enable"] = False
```

When these settings are disabled, control of Bluetooth operations is transferred from the SPIKE Prime hub operating system to the MicroPython runtime.

This allows MicroPython code running on the hub to directly manage BLE communication, enabling custom Bluetooth functionality while keeping the preserving firmware.
