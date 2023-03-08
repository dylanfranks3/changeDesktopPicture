## **Description** 

Lightweight desktop wallpaper changer that uses remote text file and a remote image handling to update the image whilst being AFK. 

This is intended for an easy install on Mac OS with no third-party installations necessary. This is untested on Linux but assume it is functional (sed method in runner file may cause issue, if on Linux try removing the '').

This repo can easily be modified to have your own local config setup, main file for images, runner file for cron. 

⚠️ *Please note, if you have methods in your crontab containing the substring 'main' this wallpaper changer will not work and cause issues.* ⚠️ 

*Check by:*
```shell
crontab -l 
   ```


## **Configuration**
For this to work, you'll need an online image host which can be retireived by a Curl request, with the desired format: JPEG, PICT, TIFF, PNG or HEIC.

Finally a text file which can be retireived by a Curl request, with only the cron schedule of how often you'd like the background changed. 


## **Installation**

1. Clone repo

   
2. In main file, edit the curl url to the desired url of the image that you'd like displayed
3. In runner file, edit the curl url to the desired url where the cron schedule is stored
2. ```shell
   cd thisRepo #change directory to location of repo
   chmod u+x runner main #add privlidges to these files
   crontab -e #edit crontab
   ```
5. Add this to your crontab, save and quit:
    ```shell
   * * * * * path/to/repo/runner
   ```
  
