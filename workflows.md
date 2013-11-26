### Set up ST3 backup from existing installation
```bash

# Make your backup Folder.
mkdir ~/Dropbox/ST3/
cd ~/Library/Application\ Support/Sublime\ Text\ 3/
# Move the files.
mv Packages/ ~/Dropbox/ST3/
mv Installed\ Packages/ ~/Dropbox/ST3/
# Make symlinks
ln -s ~/Dropbox/ST3/Packages/ Packages
ln -s ~/Dropbox/ST3/Installed\ Packages Installed\ Packages

```

### Setting up new system
```bash

cd ~/Library/Application\ Support/Sublime\ Text\ 3/

# Remove packages and settings
rm -rf Packages/ ~/Dropbox/ST3/
rm -rf Installed\ Packages/ ~/Dropbox/ST3/

# Make symlinks
ln -s ~/Dropbox/ST3/Installed\ Packages Installed\ Packages
ln -s ~/Dropbox/ST3/Packages/ Packages

```

### creating laravel project
```
composer create-project laravel/laravel your-project-name --prefer-dist
```