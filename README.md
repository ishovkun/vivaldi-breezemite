# Breezemite for Vivaldi
This is a custom .css script that adds Breezemite window decorations into
the Vivaldi's tab bar on Linux. This script is usable if Vivaldi is told not to use
the system window decorations.
The stylesheet is meant for KDE Plasma users who want to save their vertical
screen real estate and are looking forward to DWDs.

Since sometimes a screenshot is better than a wordy description, just look
at this:
![Screenshot](./Screenshot.png)

Furthermore, for the active-window-control users, this stylesheet hides
the window decoration in Vivaldi! So when Vivaldi is maximized, the result
will look like this:
![Screenshot](./Screenshot_maximized.png)

## Installation
Detailed instructions on how to enable custom stylesheets in Vivaldi can
be found elsewhere
https://forum.vivaldi.net/topic/14333/how-to-add-custom-css-code-on-linux

For the lazy people though, it goes like this:
1. Find the browser.html file
(on my Arch linux machiene the path is /opt/vivaldi/resources/vivaldi/browser.html)
2. Add the following line into the `<head>` tag:
~~~~
<link rel="stylesheet" href="style/custom.css" />
~~~~
After doing this your `browser.html` should look something like this:
~~~~
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Vivaldi</title>
    <link rel="stylesheet" href="style/common.css" />
    <link rel="stylesheet" href="style/custom.css" />
  </head>
  <body style="
    background-color: #d4d4d4;
    background-image: url('resources/vivaldi-splash-icon.svg');
    background-size: 16%;
    background-position: center;
    background-repeat: no-repeat;">
    <div id="app" />
    <script src="localeSettings-bundle.js"></script>
    <script src="background-common-bundle.js"></script>
    <script src="vendor-bundle.js"></script>
    <script src="settings-bundle.js"></script>
    <script src="urlbar-bundle.js"></script>
    <script src="components-bundle.js"></script>
    <script src="bundle.js"></script>
  </body>
</html>
~~~~

3. Copy the `custom.css` file into the `style` folder.
(Again, on my machience it is located at /opt/vivaldi/resources/vivaldi/style)

4. Run Vivaldi and enjoy your vertical-space-saving setup!

## Disable hiding decorations for maximized windows
If you don't use active-window-control Plasma applet or simply want the
window decorations shown for maximized windows as well,
Comment out or simply remove the following tags:
~~~~
.maximized #tabs-container.top  {
    padding-top:0px !important;
    padding-left: 0px !important;

}
~~~~
and
~~~~
.maximized .window-buttongroup {
    margin-left: 5px;
    opacity: 0.0;
    width: 0px !important;
}
~~~~
