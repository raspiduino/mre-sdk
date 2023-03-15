# Development Resources
This document may contain tools/references to resources that might be useful to you for developing MRE apps.

## RGB565 Color Picker
Colors in MRE apps are generally stored in an RGB565 format. To generate colors in this format, use this tool: https://chrishewett.com/blog/true-rgb565-colour-picker/
### Usage:
Assume you have a line of code which assigns a color to a color struct like this:
```c
color.vm_color_565 = VM_COLOR_RED;
```
Instead of `VM_COLOR_RED`, you can generate a color using the tool above, and paste it in place of the color constant (for example, `0x3186` is a dark shade of gray).
Now the code should look like this:
```c
color.vm_color_565 = 0x3186;
```
