National Geographic Photo of the Day Downloader for Linux. 
=================
  This is a shell script I wrote to automate the process of downloading National Geographic photo of the day, and 
  set it as background in linux. The script downloads the photo of the day in the same directory that it resides. You 
  can use cron to make it automatically running everyday. 

  Although National Geographic posts a photo everyday, not all the photos come with a high quality format. So the script       checks whether a wallpaper format exists or not. If so, it downloads the photo into the same directory the script resides.

Setup
=================

  All you need to do is to create a directory for your wallpapers and put the script in there, e.g.:
  
    cd ~/Pictures/
    git clone https://github.com/samanbarghi/ngphotodownloader.git NGWallpapers
    


Cron
=================
  You can setup your cron to run daily to download and set the background. Add the following to current user's crontab by issueing:
  
     crontab -u username -e
     
  Replace  `username` with your username. Make sure to export `PATH` in your crontab
  
    PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin  
    0 12 *  * * sh /home/yourusername/Pictures/NGWallpapers/ngwallpaper.sh
    
  In my case since I am running the script on my laptop, and my laptop is not always on; I call the script every 3 hours to make sure it runs at least once each day. Don't worry about duplicates, the script will not download the image if it already exists in the directory. The overhead of the script on cpu/memory/network is negligible, so don't worry about calling the script 8 times a day:

    00 */3 * * * sh /home/yourusername/Pictures/NGWallpapers/ngwallpaper.sh
    
 Keep in mind that   `DBUS_SESSION_BUS_ADDRESS` is only detected for `cinnamon`, `gnome`, and `mate`. If other managers are runnign  you need to modify the following lines in the script so `pgrep` catch the right `pid`: 
 
  PID=$(pgrep -o "cinnamon-sess|gnome-sess|mate-sess")
  export DBUS_SESSION_BUS_ADDRESS=$(grep -z DBUS_SESSION_BUS_ADDRESS /proc/$PID/environ|cut -d= -f2-)

Refer to http://stackoverflow.com/questions/10374520/gsettings-with-cron for more information. 
    
Enjoy!
=================
  
    
 
