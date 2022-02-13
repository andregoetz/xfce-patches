# Patches for xfce4
A few patches for xfce4.

## xfwm4
All patches are based on xfwm4-4.16.1.

To apply a patch type:
```
git clone https://github.com/xfce-mirror/xfwm4.git
cd xfwm4
git checkout xfwm4-4.16.1
git apply <patch-name>.patch
```
then rebuild xfwm4
### [Keep panel hidden on fullscreen](xfwm/xfwm4-4.16-keep_panel_hidden_on_fullscreen.patch)
This patch was made by Mike Schliep and rebased by David Keogh see this
[gitlab issue](https://gitlab.xfce.org/xfce/xfwm4/-/issues/84) for more details.
### [Don't raise window on scrolling](xfwm/xfwm4-4.16.1-no_raise_on_scroll.patch)
This patch makes it that windows will not be focused/raised when you scroll in them even if you have "Raise windows when
any mouse button is pressed" option checked in the Window Manager Tweaks.\
It is inspired by this [issue](https://gitlab.xfce.org/xfce/xfwm4/-/issues/50) (possible improvement could be to add a
check option in the settings like in the original patch).
### [Keep window cycle dialog open](xfwm/xfwm4-4.16.1-window_cycle_keep_open.patch)
This patch enables it to keep the window cycling dialog open when you press a key combination (Alt+Tab still works
normally). You can then select the window with the mouse or by pressing the "Cancel-key" (default is escape).\
To set a shortcut either execute
```
xfconf-query -c xfce4-keyboard-shortcuts -n -p "/xfwm4/custom/<Shortcut>" -t string -s "cycle_keep_windows_key"
```
Or apply the corresponding patch for [libxfce4ui](libxfce4ui/libxfce4ui-4.16.1-window_cycle_keep_open.patch) to add an
entry in the Window Manager settings.