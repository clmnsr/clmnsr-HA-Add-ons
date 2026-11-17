\# Changelog



\## 2.0.0

\- \*\*Major Update:\*\* Generalized the Add-on to support all standard and modded Klipper/Moonraker installations.

\- \*\*New Feature:\*\* Added `printer\_ip` option to the Home Assistant UI. You no longer need to use environment variables; simply type your IP into the configuration tab.

\- \*\*New Feature:\*\* Added `reset\_pairing` toggle. If you need to link your printer to a different OctoEverywhere account, toggle this on and restart the Add-on to generate a fresh QR code.

\- \*\*Under the hood:\*\* Implemented a smart Python wrapper during the build process to automatically track IP changes and securely clear old pairing tokens without breaking native container paths.

