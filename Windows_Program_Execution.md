We use different tools for threat hunting to determine what might be hiding within Windows systems.
To see what exe files have been installed (or run) we can use Amcacheparse. 

in CMD > Amcacheparse.exe -f "C:\Windows\AppCompat\Programs\Amcache.hve" --csv C:\temp

