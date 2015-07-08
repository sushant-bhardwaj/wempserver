**About:**

WempServer is an easy web development platform on Windows helping you to develop dynamic web applications with Nginx+PHP+MySQL. It's green (no installation), safe and fast - just download, extract and start. It's truly portable, you can move it anywhere.

**Operating environment:**

Microsoft Windows NT 5.1-x.x (PE/XP/2003/Vista/2008/7/8/2012/8.1/10...)

**WempServer contains all PHP releases:**

PHP 5.2.17

PHP 5.3.27/28

PHP 5.4.x

PHP 5.5.x (Windows XP and 2003 support dropped.)

...

**Commands:**

Note: Please run as administrator on Vista or later.
```
a    Add vhosts
b    Back
c    Command
cs   Create shortcuts
ct   Create task
ct5  Create task with 5  PHP-FPM
ct10 Create task with 10 PHP-FPM
ct20 Create task with 20 PHP-FPM
d    Delete vhosts
dl   Download latest
ds   Delete shortcuts
dt   Delete task
e    Exit
eh   Edit hosts
em   Edit my.ini
en   Edit nginx.conf
ep   Edit php.ini
fc   FTP client
fs   FTP server interface
g    Google
h    Help
ke   Kill Explorer
l    Localhost
n    Nginx only
np   Notepad
npp  Notepad++
p    PHP-FPM
q    Quit
qf   Quit FTP
r    Reload nginx
re   Restart Explorer
s    Start
s5   Start with 5  PHP-FPM
s10  Start with 10 PHP-FPM
s20  Start with 20 PHP-FPM
sf   Start FTP
top  Taskmgr
w    WWW
```

**Arguments:**
```
-s s   Start all services and then go to menu. (s5, s10, s20)
-s se  Start all services and then exit. (s5e, s10e, s20e)
-s sf  Start FTP services and then go to menu.
-s sfe Start FTP services and then exit.
-s q   Quit all services and then go to menu.
-s qe  Quit all services and then exit.
-s n   Start Nginx only and then go to menu.
-s ne  Start Nginx only and then exit.
Example:
Shortcut target: D:\WempServer\WempServer.exe -s s5
Shortcut working directory: D:\WempServer
```

**Start on Windows startup:**

Method 1: Menu > ct (ct5, ct10, ct20) (RECOMMEND)

Method 2: Create a shortcut to WempServer.exe -s se (s5e, s10e, s20e)

Shortcut properties:

Shortcut target: D:\WempServer\WempServer.exe -s se

Shortcut working directory: D:\WempServer

Copy the shortcut to Start > All Programs > Startup (Win8: C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp)

**Batches:**

**header.bat**

```
@echo off
rem ...
exit
```

**footer.bat**

```
@echo off
rem start /b php\php-fpm -b 9020
rem ping localhost -n 2 1>nul 2>nul
rem start /b php\php-fpm -b 9021
rem ...
exit
```

**start.bat**

```
@echo off
if exist vcredist_x86.exe vcredist_x86.exe & ren vcredist_x86.exe vcredist_x86-installed.exe
if exist vcredist_x64.exe vcredist_x64.exe & ren vcredist_x64.exe vcredist_x64-installed.exe
if exist vcredist_arm.exe vcredist_arm.exe & ren vcredist_arm.exe vcredist_arm-installed.exe
nginx\nginx.exe -s quit 1>nul 2>nul
WempServer.exe -s se
exit
```

**quit.bat**

```
@echo off
WempServer.exe -s qe
exit
```

For more information, please visit http://ysq.me/p/wempserver/