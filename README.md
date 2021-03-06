# Patches for xfce4
A few patches for xfce4

## xfwm4
All patches are based on xfwm4-4.16.1

To apply a patch type:
```
git clone https://gitlab.xfce.org/xfce/xfwm4.git
cd xfwm4
git checkout xfwm4-4.16.1
git apply <patch-name>.patch
```
then rebuild xfwm4
### [Keep panel hidden on fullscreen](xfwm/xfwm4-4.16-keep_panel_hidden_on_fullscreen.patch)
This patch was made by Mike Schliep and rebased by David Keogh see this
[gitlab issue](https://gitlab.xfce.org/xfce/xfwm4/-/issues/84) for more details.
### [Fix crash when clicking outside window list](xfwm/xfwm4-4.16-fix_crash_when_clicking_outside_window_list.patch)
This patch was made by Jonathan Apostoles see this [gitlab issue](https://gitlab.xfce.org/xfce/xfwm4/-/issues/561) for
more details.
### [Don't raise window on scrolling](xfwm/xfwm4-4.16.1-no_raise_on_scroll.patch)
This patch makes it that windows will not be focused/raised when you scroll in them even if you have "Raise windows when
any mouse button is pressed" option checked in the Window Manager Tweaks.\
It is inspired by this [issue](https://gitlab.xfce.org/xfce/xfwm4/-/issues/50) (possible improvement could be to add a
check option in the settings like in the original patch)
### [Keep window cycle dialog open](xfwm/xfwm4-4.16.1-window_cycle_keep_open.patch)
This patch enables it to keep the window cycling dialog open when you press a key combination (Alt+Tab still works
normally). You can then select the window with the mouse or by pressing the "select_key"

To set a shortcut either execute:
#### window cycling
```
xfconf-query -c xfce4-keyboard-shortcuts -n -p "/xfwm4/custom/<Shortcut>" -t string -s "cycle_keep_windows_key"
```
#### selecting the window
```
xfconf-query -c xfce4-keyboard-shortcuts -n -p "/xfwm4/custom/<Shortcut>" -t string -s "select_key"
```
Or apply the corresponding patch for [libxfce4ui](libxfce4ui/libxfce4ui-4.16.1-window_cycle_keep_open.patch) to add the
entries in the Window Manager settings.
### [Close window from tabwin](xfwm/xfwm4-4.16.1-close_window_from_tabwin.patch)
This patch makes it possible to close a window from tabwin by clicking it with the middle mouse button (Button2)

## libxfce4ui
All patches are based on libxfce4ui-4.16.1

To apply a patch type:
```
git clone https://gitlab.xfce.org/xfce/libxfce4ui.git
cd libxfce4ui
git checkout libxfce4ui-4.16.1
git apply <patch-name>.patch
```
then rebuild libxfce4ui
