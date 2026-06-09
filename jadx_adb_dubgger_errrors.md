
see example error https://github.com/skylot/jadx/issues/2808


> i got this error because i was new to debugging.
> what i wanted was i want to debug android app using jadx.  
> so i can debug it without source code,  
> but i faced errors mentioned above ,the root cause was bad configuration  
> i am explaining details so later even if we forget solution then this will help us.  
> my setup was
> * windows 11
> * jadx 1.5.5


### how to configure jadx and adb to debug android app 

in jadx gui if we clicked adb option then a pop up will show   
> adb path must be provided in the  first input box otherwise contents in the device list start blinking .
> it will also blinks if there is no devcies connected to system by adb devices.
> if you dont know adb path then  just download adb from any source  then put its full file path in this input box,

<img width="640" height="410" alt="adb_jadx_blinking_emulator 2026-06-09 185403-video-to-gif" src="https://github.com/user-attachments/assets/d930e293-9a1d-460b-ab19-7913eed9f51a" />.  
my path was

```C:\Users\system\Documents\platform-tools\adb.exe```

next we need to enter following in next row first input box (ADB addr )
``` 
localhost
```  

next we need port to enter in second inputbox ( ADB port)

to get it open cmd terminal and execute these instruction ,
``` 
adb kill-server
```

now start adb

```
adb start-server
```
now you will get a port as output like this .
```
* daemon not running; starting now at tcp:5037
* daemon started successfully
```
enter this port 5037 in jadx popup input box named port , it now looks like this.  

<img width="1443" height="748" alt="Image" src="https://github.com/user-attachments/assets/9a15c6dd-edd6-4abd-aab9-d79c9980fb6a" />

then click on refresh. your device will appear in this list.  


<img width="1013" height="643" alt="image" src="https://github.com/user-attachments/assets/2901471a-5ec0-4833-9921-7c2f1e3c2047" />


