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
  You can setup your cron to run daily to download and set the background. Simply add something like this to your crontab:
  
    0 12 *  * * sh /home/yourusername/Pictures/NGWallpapers/ngwallpaper.sh
    
  In my case since I am running the script on my laptop, and my laptop is not always on; I call the script every 3 hours to make sure it runs at least once each day. Don't worry about duplicates, the script will not download the image if it already exists in the directory. The overhead of the script on cpu/memory/network is negligible, so don't worry about calling the script 8 times a day:

    00 */3 * * * sh /home/yourusername/Pictures/NGWallpapers/ngwallpaper.sh
    
Enjoy!
=================
  
    
 
