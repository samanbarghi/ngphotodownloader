National Geographic Photo of the Day Downloader for Linux. 
=================
  This is a shell script I wrote to automate the process of downloading National Geographic photo of the day, and 
  set it as background in linux. The script downloads the photo of the day in the same directory that it resides. You 
  can use cron to make it automatically running everyday. 


Setup
=================

  All you need to do is to create a directory for your wallpaper and put the script in there, e.g.:
  
    cd ~/Pictures/
    git clone https://github.com/samanbarghi/ngphotodownloader.git NGWallpapers

Cron
=================
  You can setup your cron to run daily to download and set the background. Simply add something like this to your crontab:
  
    0 12 *  * * sh /home/yourusername/Pictures/NGWallpapers/ngwallpaper.sh
  
Enjoy!
=================
  
    
 
