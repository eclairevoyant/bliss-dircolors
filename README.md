<p align="center">
  <br>
  <img src="https://raw.githubusercontent.com/joshjon/bliss-docs/master/bliss-icon.svg?sanitize=true" alt="icon" height="145">
  <h3 align="center">Bliss dircolors</h3>
  <p align="center">
    A delicate theme that injects color without overwhelming your workspace.<br>
  </p>
  <br>
</p>

![session](https://raw.githubusercontent.com/joshjon/bliss-docs/master/bliss-dircolors/images/bliss-dircolors.png)

## Table of Contents
* [About](#about)
* [Installation](#installation)
* [Troubleshooting](#troubleshooting)
* [Author](#author)
* [References](#references)

## About

Bliss dircolors is a theme for the `ls` command in macOS and Linux, and is made for use with dark theme terminals supporting 256 colors e.g. iTerm2.

Bliss inspires calmness and tranquil, whilst maintaining readability and visual distinction between elements. It is specifically designed with colors of high value (lightness) and low to intermediate saturation. As a result, the palette's tonal properties invoke a softer look that is easier on your eyes.

### Setting the Mood
Bliss looks even better with the following terminal setup:
* [iTerm2](https://www.iterm2.com/)
* [Bliss iTerm Theme](https://github.com/joshjon/bliss-iterm)
* [Oh My Zsh](https://github.com/robbyrussell/oh-my-zsh)
* [Bliss Oh My Zsh Theme](https://github.com/joshjon/bliss-zsh)

### Palette

![session](https://raw.githubusercontent.com/joshjon/bliss-docs/master/bliss-dircolors/images/bliss-dircolors-palette.svg?sanitize=true)

### Color Properties

Bliss has similarities to most [default `ls` colors](https://askubuntu.com/questions/17299/what-do-the-different-colors-mean-in-ls) where possible; however, some colors differ from the default scheme in order to increase readability.

* Regular file: white
* Directory: pink, bold
* Symbolic link: green
* Symbolic link to nonexistent file: red background, white
* File that has setuid (u+s): red, underscore
* File that has setgid (g+s): bronze, underscore
* Pipe, socket, door:	bronze background, white
* Block and character device:	bronze, underscore
* Executable:	white, bold
* Other writable (o+w) directory:	blue, bold
* Sticky bit (+t) directory: blue background, white
* Sticky other writable (+t,o+w) directory: teal background, white
* Archive or compressed: lavender, bold
* Image file:	yellow
* Audio file:	lime-green
* Video file:	orange
* Logs and backups: grey

## Installation

### Installing Bliss dircolors

Add the following to your `~/.bash_profile` or `~/.zshrc` to use Bliss dircolors for all future shell sessions.

        eval $(dircolors /<path-to-cloned-repo>/bliss.dircolors)

### Zsh Additional Install Information

If you are using Z shell (Zsh), you may also find that tab completion does not use dircolors when displaying directories. This can make some directories with permissions very difficult to read e.g. other-writable (o+w) directories as seen in the screenshot below.
![session](https://raw.githubusercontent.com/joshjon/bliss-docs/master/bliss-dircolors/images/zsh-issue.png)
To enable Bliss dircolors for Zsh tab completion simply put the following line in your .zshrc file:

```
zstyle ':completion:*:default' list-colors ${(s.:.)LS_COLORS}
```

Tab completion will now use the color properties in `bliss.dircolors`
![session](https://raw.githubusercontent.com/joshjon/bliss-docs/master/bliss-dircolors/images/zsh-fix.png)

## Testing

`bliss-test.zip` contains the sample files shown in the screenshot at the beginning of this document. Once Bliss is installed, this can be used to test the color output from ls.

Note: some files will lose their properties after being cloned to your machine. These properties will need to be re-applied accordingly for dircolors to take effect.

## Troubleshooting

### Zsh commands are not using Bliss dircolors

Refer to [Zsh Additional Install Information](#zsh-additional-install-information).

---

### Author

Joshua Jon<br>
GitHub: https://github.com/joshjon

### References

* [Linux Man Pages:](https://www.systutorials.com/docs/linux/man/5-dir_colors/) dir_colors: configuration file for dircolors
* [Dennis Conrad's Blog:](http://www.conrad.id.au/2013/07/making-mac-os-x-usable-part-1-terminal.html) Making Mac OS X Usable - Part 1 - The Terminal
* [256 Colors:](https://raw.githubusercontent.com/joshjon/bliss-docs/master/bliss-dircolors/images/256-colors.png) A reference for all 256 colors
