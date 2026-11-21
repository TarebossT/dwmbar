# dwmbar

dwm status written in shell.

Displays memory usage, cpu usage, cpu temperature, battery level, brightness level, volume level, wifi, keyboard layout, date and time.

Can be used with dwm by adding kill -34 $(cat ~/.cache/pidofbar) to volume, brightness and keyboard layout in dwm's config.h file. For example:
	{ 0,                  XF86XK_AudioMute,         spawn,     SHCMD("amixer -D pulse sset Master toggle; kill -34 $(cat ~/.cache/pidofbar)") },
  { 0,                  XF86XK_MonBrightnessUp, spawn, SHCMD("brightnessctl set +5%; kill -35 $(cat ~/.cache/pidofbar)") },
  { MODKEY,             		XK_a,      spawn,          SHCMD("setxkbmap -query | grep -q 'us' && setxkbmap -layout ro -variant std || setxkbmap us; kill -36 $(cat ~/.cache/pidofbar)") },
