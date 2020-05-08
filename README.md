# xdotool-trigger

A simple wrapper for [xdotool](https://www.semicomplete.com/projects/xdotool/) to easily script some basic input macros

## Arguments

You can pass a single mouse button to trigger or a list of keystrokes

### Mouse buttons

- click
- wheel
- rclick
- wup
- wdown

### Keystrokes

- Characters: a, b, 1, 2, Y, Z
- Keys: Return, space, L_Shift
- Combos: ctrl+a, shift+i

## Options

- -w *window_name*: focus the first window by that name and send the inputs to it
- -r *times*: repeat the inputs this amount of times
- -d *millis*: delay between each click or series of keystrokes
- -p *x,y*: position the mouse in *(x,y)* before triggering the inputs
- -D: Dry-run mode, output the `xdotool` lines that would be executed
- -v: verbose mode, output the lines and also run them

## Examples

### Focus Firefox, select the address bar, type "pizza" and press Enter

```
trigger.sh -v -w Mozilla F6 ctrl+a p i z z a Return
```

### Focus Firefox, refresh the current tab 10 times every 5 seconds

```
trigger.sh -v -w Mozilla ctrl+r -r 10 -d 5000
```

### Trigger 10 clicks at (100,200) every second

```
trigger.sh -v -p 100,200 click -r 10 -d 1000
```

### Simulate wheel down 30 times every 300ms

```
trigger.sh -v wdown -r 30 -d 300
```

## Requirements

`xdotool` must be installed