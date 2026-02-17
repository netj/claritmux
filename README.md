# claritmux

A TMUX Plugin Manager (TPM) plugin for a much clearer status bar and pane borders.

Based on [@89iuv's config](https://github.com/catppuccin/tmux/discussions/317#discussioncomment-11064512).

## Features

- Clean status bar with session, working directory, date/time, and hostname
- Window status with activity/bell/current indicators
- Pane border labels with pane number, command, title, and zoom status
- Ships standalone default colors (mocha-inspired palette)
- Fully customizable: override colors, styles, or formats before loading

## Install

Add to your `.tmux.conf`:

```tmux
set -g @plugin 'netj/claritmux'
```

Then press `prefix + I` to install via TPM.

## Customization

All `@claritmux_*` variables use `-o` (only-if-not-set), so you can override any of them anywhere before TPM loads (i.e., before the `run '...tpm'` line in your `.tmux.conf`).

### Colors

```tmux
# Set any of these before TPM loads to override defaults
set -g @claritmux_color_bg           '#1e1e2e'
set -g @claritmux_color_fg           '#9399b2'
set -g @claritmux_color_separator    '#6c7086'
set -g @claritmux_color_inactive     '#6c7086'
set -g @claritmux_color_active       '#a6e3a1'
set -g @claritmux_color_bell         '#f38ba8'
set -g @claritmux_color_prefix       '#89dceb'
set -g @claritmux_color_session      '#585b70'
set -g @claritmux_color_path         '#89b4fa'
set -g @claritmux_color_date         '#f9e2af'
set -g @claritmux_color_day          '#fab387'
set -g @claritmux_color_time         '#f38ba8'
set -g @claritmux_color_timezone     '#45475a'
set -g @claritmux_color_host         '#585b70'
```

### With catppuccin/tmux

```tmux
# Override claritmux colors with catppuccin theme variables
set -gF @claritmux_color_bg           '#{@thm_bg}'
set -gF @claritmux_color_fg           '#{@thm_overlay_2}'
set -gF @claritmux_color_separator    '#{@thm_overlay_0}'
set -gF @claritmux_color_inactive     '#{@thm_overlay_0}'
set -gF @claritmux_color_active       '#{@thm_green}'
set -gF @claritmux_color_bell         '#{@thm_red}'
set -gF @claritmux_color_prefix       '#{@thm_sky}'
set -gF @claritmux_color_session      '#{@thm_surface_2}'
set -gF @claritmux_color_path         '#{@thm_blue}'
set -gF @claritmux_color_date         '#{@thm_yellow}'
set -gF @claritmux_color_day          '#{@thm_peach}'
set -gF @claritmux_color_time         '#{@thm_red}'
set -gF @claritmux_color_timezone     '#{@thm_surface_1}'
set -gF @claritmux_color_host         '#{@thm_surface_2}'
set -g @plugin 'netj/claritmux'
```

### Styles and formats

Styles (derived from colors) and window name formats can also be overridden:

```tmux
set -g @claritmux_style_status_session  'bg=default,fg=magenta'
set -g @claritmux_format_window_named   ' #{window_name}'
```

## References

- [tmux Formats](https://github.com/tmux/tmux/wiki/Formats)
- [Nerd Fonts Cheat Sheet](https://www.nerdfonts.com/cheat-sheet)

## License

[MIT](LICENSE)
