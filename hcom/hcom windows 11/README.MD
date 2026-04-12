# Windows 11 Husky hcom communications package

hcom adapted for Windows 11 usage

## Description

The existing hcom package (PC<>Husky comms over serial link) was built for Windows 98 era PCs. This update is a quick-and-dirty solution to enable to run natively on Windows 11.

Used Cursor agent to uncompress legacy application and to patch out references to system folder files.  No longer installed via Windows application process - just copy files to hard drive and run.

### Capabilities and Limitations

* Enables upload/download of files to Husky computer from Windows 11.
* Limitation: Application Help will not work as it relies on legacy windows capabilities
* No other functionality has been tested

### Installing and Execution

* Download files onto PC
* Run the HCOM32.EXE

### Configuration and Setup

If the HCOM program is not installed on the Husky, it must be downloaded and installed from the PC running HCOM.

* Connect the Hunter to a serial port on the PC.
* Open a channel using HCOM for Windows using the same serial port.
* Select the Session / Software Download option and choose Hunter from the list of machines.
* On the Hunter ensure that the communications parameters are set as follows (type COMS at the DEMOS prompt to start the serial port configuration program):

```
Transmission Parameters
Rate - 2400     Prtcl - none    Pty - 8bit
CTS - n  DTR - n LF - n  Echo - n       T/O - n  Null - 0

Receiving Parameters
Rate - 2400     Prtcl - none    Pty - 8bit
RTS - off       DSR - n DCD - n  T/O - n Serig - off
```
* On the Hunter, type the command "INP 999 HCOM.COM". The screen should now display "Waiting".
* On the PC select the OK button to start the transfer. The Hunter screen should now display "Loading".
* When the transfer is complete press ESC (Shift-BRK) on the Hunter to save the software to disk. The Hunter screen should now display "Aborted".
* Run HCOM on the Hunter and select the Reconnect option on the PC. The directory of the Hunters disk should now be displayed.

## Authors

Original authors at Husky Computers Ltd

Adapted for Windows 11 using Cursor by Brian Foskett

## Version History

* 0.1
    * Initial Release