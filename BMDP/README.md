Command | Function
--- | ---
`gdb` | start gdb  
`target extended-remote \\.\COM15` | connect to debug interface using second COM port (LED brightens)  
`monitor version` | show interace version  
`monitor swdp_scan` | detach connected targets and show available targets using the SWD interface  
`attach <n>` | attach to target and pause ecexution  
`load <filename>` | upload file  
`continue` | continue execution until CTRL + C interrupt  
`detach` | detach from target  
`kill` | detach from target and reset  
`quit` | exit gdb  

Commands can be shortened to as few letters as are unambiguous.
