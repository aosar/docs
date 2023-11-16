# Vim: Advice for Beginners
Learning vim is a huge quality of life boost for a developer, even just knowing a small set of commands.

**The key is to start small.**

The commands are not intuitive at first, so adjusting to them incrementally is key. You will be able to build mental maps from there, and any new commands you learn will become strangely intuitive and fascinating.

I only began with roughly 5 commands, minus save/quit macros, which served me well for years. Even if I only had this set of commands, I would gladly accept it with open arms.

## Getting Started
Vim has a "normal mode" and an "insert mode". Normal mode allows you to run commands like the above without actually typing text. I'd suggest starting with the following commands, getting comfortable with them for months before learning more.

From Normal Mode:

- `i` - insert mode
- `o` - create new line below the current and then enter insert mode
- `yy` - copy (yank) the current line
- `p` - paste the copied line below
- `dd` - delete the current line
- `:w` - write the file (if you are using vscode extension this isnt necessary)

From Insert Mode:
- `esc` - go back to normal mode

I usually press 2-3 times just in case I accidentally entered a weird mode like visual mode.
If things go totally crazy for no reason, you probably have your caps lock on.


## VSCode Integration
I use the VSCode extension for vim so I can use it in my normal workspace. I find the experience seamless with the right configuration. These are the settings I prefer:
```
{
    "vim.useCtrlKeys": false,
    "vim.handleKeys": {
      "<C-E>": true,
      "delete": true
    }
}
```
