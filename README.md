# Folder archive
> Daily Folder Backup and Rotation for Linux

## Key Features:
- Daily automated backups of a specified folder using the zip utility.
- Date-appended archive file names for easy identification.
- Automatic removal of backups older than 14 days.
- Scheduled execution using cron for a hands-off approach.

## Explanation:
- The script sets the source directory (SOURCE_DIR) that will be zipped and the archive directory (ARCHIVE_DIR) where the zipped files will be stored.
- It creates a timestamp in the format YYYY-MM-DD and stores it in the DATE variable.
- The zip command is used to create the zipped archive and append the date to the file name.
- The find command is used to delete files older than 14 days in the archive directory. (edit in the script as needed)
- The cron entry schedules the script to run daily at 13:00 (1 PM).

Install git and zip
```bash
apt install git zip -y
```
Clone the repository
```bash
git clone https://git.moelle.space/ymoelle/folderarchive.git
```
Add the following to cron:
```bash
0 13 * * * sh /path/to/script/zip_folder_daily.sh
```