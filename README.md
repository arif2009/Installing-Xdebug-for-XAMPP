# Installing Xdebug for XAMPP with PHP

## Requirements

* XAMPP for Windows: https://www.apachefriends.org/download.html
* You need to install Microsoft Visual C++ . Check your **Control Panel > Programs and Features**, if you don't have it then install from the below link. 
* Visual C++ Redistributable for Visual Studio 2015 [x86 or x64](http://www.microsoft.com/en-us/download/details.aspx?id=48145).
* Visual C++ Redistributable for Visual Studio 2017 x64 or [x86](https://go.microsoft.com/fwlink/?LinkId=746571).

## Setup

* Download Xdebug from [here](https://xdebug.org/download.php). If you can't detect your appropiate Xdebug then, open [Xdebug wizard](https://xdebug.org/wizard.php) and copy your phpinfo (generally you will get it from http://localhost/dashboard/phpinfo.php) section into thi wizard text box.
* Copy the file `php_xdebug-YourDownloaded.dll` to: `C:\xampp\php\ext`
* Open the file `C:\xampp\php\php.ini` with Notepad++
* Disable output buffering: `output_buffering = Off`
* Scroll down to the bottom and pest this `[XDebug]` section :

```ini
[XDebug]
zend_extension = "c:\xampp\php\ext\php_xdebug-YourDownloaded.dll"
xdebug.remote_autostart = 1
xdebug.profiler_append = 0
xdebug.profiler_enable = 0
xdebug.profiler_enable_trigger = 0
xdebug.profiler_output_dir = "c:\xampp\tmp"
;xdebug.profiler_output_name = "cachegrind.out.%t-%s"
xdebug.remote_enable = 1
xdebug.remote_handler = "dbgp"
xdebug.remote_host = "127.0.0.1"
xdebug.remote_log = "c:\xampp\tmp\xdebug.txt"
xdebug.remote_port = 9000
xdebug.trace_output_dir = "c:\xampp\tmp"
;36000 = 10h
xdebug.remote_cookie_expire_time = 36000
```
* Stop/Start Apache
