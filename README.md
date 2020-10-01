# runSelectionInColsole


# recomandet: set hotkey super+c for this script.
# https://pads.ccc.de/autokey2konsole
# Displays the information of the next window to be left-clicked
# import time
import time
# mouse.wait_for_click(1)
winTitle = window.get_active_title()
winClass = window.get_active_class()
# toClip = winClass # 'Hello World'
# clipboard.fill_clipboard(toClip) # https://github.com/autokey/autokey/wiki/API-Examples#clipboard
keyboard.send_keys("<ctrl>+c")
# time.sleep(0.2)
# dialog.info_dialog("Window information", "Active window information:\nTitle: '%s'\nClass: '%s'" % (winTitle, winClass))         
# Activate the specified window, giving it input focus. https://autokey.github.io/index.html
# Title = '[GitHub] Please verify your device - sl5softwarelab@gmail.com - Gmail - Mozilla Firefox'
# Class: 'Navigator.Firefox'
Title = '~ : bash — Konsole'
Class = 'konsole.konsole'
window.activate(Title, switchDesktop=False, matchClass=False)
time.sleep(0.2)
fromClip = clipboard.get_clipboard()
# output = fromClip # output = 'hi'
# keyboard.send_keys(output + "<enter>")
# keyboard.press_key("<ctrl>")
time.sleep(0.2)
if True:
    keyboard.send_keys("<ctrl>+<shift>+v") # works :)
else:
    keyboard.press_key("<shift>")
    keyboard.send_keys("v")
    keyboard.release_key("<shift>")
# keyboard.release_key("<ctrl>")
keyboard.send_keys("<enter>")
# keyboard.press_key("<ctrl>")

# window.activate(winTitle, switchDesktop=False, matchClass=False) # activates the window with 'Atom' as part of the window title.
# dont work: window.activate(winClass + "." + winTitle, switchDesktop=False, matchClass=False) # activates the window with 'atom.Atom' as its class name.
time.sleep(0.2)
window.activate(winTitle, switchDesktop=False, matchClass=False) # activates the window with 'atom.Atom' as its class name.
# dont work: window.activate("autokey-gtk.Autokey-gtk.Autokey", switchDesktop=False, matchClass=False) # activates the window with 'atom.Atom' as its class name.
 

