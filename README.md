# PyWatch

This repo contains a Python implementation mimicking the classic Unix [watch](https://linux.die.net/man/1/watch) command.
It provides additional functionality to allow for scrolling, paging and cycling between multiple commands.
It should also be able to handle dynamic terminal resizing, including height, width & in/out zooming.

## Requirements
- Python >= 3.x
- Tested on Ubuntu 16.04
- Tested on the default terminal, [Yakuake](https://kde.org/applications/system/org.kde.yakuake) and [Terminator](https://gnometerminator.blogspot.com/p/introduction.html)

Update: Removed all Python >= 3.6 requirements. It should now run with any version of Python 3.

## Usage
- Remember to make the file executable: `chmod +x path/to/scripts/pywatch`
- (Optional) Add to system path, e.g. ~/.bashrc: `export PATH=/path/to/scripts/:$PATH`

#### Commands
Assuming the script has been added to the system path, it can be used as a simple replacement for "watch".
Otherwise, replace `pywatch` with `path/to/stripts/pywatch` in the examples below.

```
# Default 1 sec interval
pywatch echo Hello World

# Set interval to half a second
pywatch -n .5 "cat long_logfile.log"

# Two commands we can switch between (default 5 secs)
pywatch "echo Hello World && echo Foo Bar"

# Set cycle time and begin cycling
pywatch -c 10 "cat long_logfile.log && echo Hello World" --cycle
```

#### Controls
+ **Scrolling**: UP/DOWN keys or mouse wheel
+ **Paging**: LEFT/RIGHT keys or PageUp/PageDown keys
+ **Top/bottom of command**: Home/End keys
+ **Cycle between commands**: Tab/Ctrl+Tab keys
+ **Toggle cycling mode**: C key
+ **Change refresh interval**: I key + enter the new interval time

##### Additional Notes:
+ As an indicator, the header is displayed in CYAN when "Cycling" mode is active.
+ The TextBox used to change interval time uses Emacs bindings (which I don't think can be changed), e.g. to delete use Ctrl+H


### Licence
[MIT Licence](LICENCE)