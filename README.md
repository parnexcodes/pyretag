# pyretag

A python script to retag mkv files.

# Setting Up

- `pip install pyfiglet`
- `pip install rich`

Move the mkv files to **input** folder.

Edit **config.json** (for uploading through rclone) [Optional]

Default **config.json**
```
{
    "rclone_upload": "False",
    "rclone_remote": "drive",
    "delete_files": "False"
}
```

# Usage

```
py retag.py -h

usage: retag.py [-h] -i INPUT -o OUTPUT

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Original Group/Release Tag.
  -o OUTPUT, --output OUTPUT
                        Your Group/Release Tag.
```

**Example Command** : `py retag.py -i CBFM -o LOLi`

## Note

Input and Output Value are **case-sensitive**.

![](https://i.imgur.com/ZW5wbaK.png)

#### Final Output is saved in **output** Folder

# What does it do

- Changes the **Title** of the **mkvfile** to `Bla.bla.2012.1080p.AMZN.WEB-DL.DDP.5.1 - Your Name / Group Name`
- Changes the **Title** of first 3 tracks to blank (incase the original release has anything in title.)
- **Remuxes** the **mkvfile** with new name and changes done above.
- Uploads to any **rclone remote** set in **config.json** and return the link (saved as **links.txt** in same directory).
- If files > 1 : Makes a folder , moves the files to this folder and uploads it otherwise uploads single file.
