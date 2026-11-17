\# OctoEverywhere for Klipper - Home Assistant Add-on



This is a custom Home Assistant Add-on to run the \[OctoEverywhere](https://octoeverywhere.com/) Klipper Companion directly inside Home Assistant. 



It is fully compatible with standard Klipper installations as well as modded firmwares like \*\*OpenCreator\*\* or \*\*ZMOD\*\* (often used on Flashforge printers).



\## Features

\* \*\*Seamless UI Configuration:\*\* Set your printer's IP address directly in the Home Assistant Add-on configuration tab.

\* \*\*Smart IP Tracking:\*\* The Add-on automatically detects if you change the printer IP. It will clear the old pairing data and generate a fresh setup QR code in the logs on the next start.

\* \*\*Manual Reset:\*\* A dedicated toggle allows you to force a pairing reset if you ever need to link your printer to a different OctoEverywhere account.



\## Installation



1\. Navigate to your Home Assistant interface.

2\. Go to \*\*Settings\*\* -> \*\*Add-ons\*\* -> \*\*Add-on Store\*\*.

3\. Click the three dots in the top right corner and select \*\*Repositories\*\*.

4\. Add the URL of this GitHub repository and click \*\*Add\*\*.

5\. Close the dialog and search for \*\*OctoEverywhere for Klipper\*\* in the store.

6\. Click \*\*Install\*\*.



\## Configuration



Before starting the Add-on, switch to the \*\*Configuration\*\* tab and configure the following options:



\* \*\*`printer\_ip`\*\* \*(Required)\*: The local IP address of your 3D printer running Klipper/Moonraker (e.g., `192.168.1.254`). 

\* \*\*`reset\_pairing`\*\* \*(Optional)\*: Set this toggle to true if you want to forcefully wipe the current OctoEverywhere pairing data on the next start. \*\*Note:\*\* Turn this back off after a successful reset to prevent the Add-on from wiping your setup on every reboot.



\## Initial Setup (Pairing)



1\. Save your configuration and click \*\*Start\*\* in the Info tab.

2\. Switch to the \*\*Log\*\* tab and wait a few seconds.

3\. You will see a message like `Neue IP (...) oder Reset aktiv! Loesche alte Daten...` followed by an OctoEverywhere setup URL and a QR code.

4\. Scan the QR code or click the link to link this instance to your OctoEverywhere account.



\## Support \& Credits

Powered by the official \[OctoEverywhere Docker Image](https://github.com/QuinnDamerell/OctoPrint-OctoEverywhere). Add-on structure and smart reset logic maintained by Clemens Rosenauer.

