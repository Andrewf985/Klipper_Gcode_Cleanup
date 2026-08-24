# Klipper_Gcode_Cleanup
Uses a cronjob to cleanup gcode. Not aware of subfolders.

On the klipper host:

1. run crontab

  crontab -e

2. If you haven't ran crontab yet, it'll likely have you pick a text editor.
3. Enter the line below at the bottom of the file. This specific one is set to Sunday at 3 AM and will delete anything over 30 days old.

  0 3 * * 0 find /home/pi/printer_data/gcodes -type f -name "*.gcode" -mtime +30 -delete >/dev/null 2>&1

4. Update the user path.
5. Save and exit.

If you want it to the run it at a different time and do not know cron time: https://crontab.guru
