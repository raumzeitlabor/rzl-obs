# RZL Vortrags-Equipment Doku



## Marshall CV630-IP PTZ Cam
https://wiki.raumzeitlabor.de/wiki/Kamera

Hersteller Seite:
https://marshall-usa.com/cameras/CV630-IP/
IP: 172.22.36.137
Webinterface: http://172.22.36.137/en/login.html (user "admin", pass "9999", bitte so lassen…)


## HDMI grabber/Encoder HEV-10
https://wiki.raumzeitlabor.de/wiki/HEV10

Hersteller Seite:
https://www.ddmalltech.com/collections/hdmi-extenders/products/h-265-h-264-hdmi-video-encoder-supports-4k-60hz-hdmi-input-and-real-time-local-loop-output-compact-size-rtmp-rtmps-rtsp-ts-udp-rtp-multicast-unicast-youtube-live-facebook-and-more
IP: 172.22.36.138
Webinterface: http://172.22.36.138/ (user "admin", pass "admin", bitte so lassen…)


## Rode Wireless GO II

Drei Geräte. Ein Empfänger mit 3,5mm Klinken-Ausgang zur Kamera. Zwei Drahtlose Sender zum Anklipsen an den Kragen.

* Beide Sender zeichnen einen >7 Stunden Loop auf als Backup
* Zum Zugreifen auf die Backups wird "RodeCentral" benötigt

###### ! ACHTUNG !
- Wenn RodeCentral ein Firmwareupdate durchführt, werden die Einstellungen und alle Aufzeichnungen auf den Sendern gelöscht!
- Bitte danach wieder auf _beiden_ Sendern folgende Einstellungen vornehmen:
* Record "Always"     -- Backup-Aufnahme auf dem Sender, falls was in OBS schiefgeht
* Pad "Off"           -- das wäre eine dB-Absenkung. Brauchen wir nicht
* LEDs "Dim"          -- Macht die blauen LEDs ein bisschen weniger penetrant
* O-Button "Nothing"  -- Da es an den Sendern keine optische Rückmeldung gibt, dass man grade muted ist, schalten wir das feature lieber ganz ab

###### Lagerort
* Bitte dafür sorgen, dass alle drei _immer_ in der Ladeschale liegen.




## OBS - Open Broadcaster Software ##

###### Plugins
https://obsproject.com/forum/resources/transition-table.1174/
https://obsproject.com/forum/resources/advanced-scene-switcher.395/
(Plugin für Kamera-Steuerung, leider nur macos und windows)
https://marshall-usa.com/cameras/CV630-IP/


###### Installation

* OBS installieren (getestet mit 27.1.3)
* beide plugins installieren (siehe oben)
* Dateien anpassen je nach OS (siehe unten)
* Profil importieren über OBS Menu
* Szenen importieren über OBS Menu

###### Unterschiede MacOS, Linux, Windows

* Audio capture
** Linux:   pulse_input_capture  (evtl. auch alsa?)
** Windows: wasapi_input_capture
** macOS:   coreaudio_input_capture

* Video encoding
** macOS:   RecEncoder=com.apple.videotoolbox.videoencoder.h264.gva
            Encoder=com.apple.videotoolbox.videoencoder.h264.gva
** Linux:   RecEncoder=obs_x264
            Encoder=obs_x264
** Windows: Encoder=obs_x264
            RecEncoder=obs_x264
