#!/bin/bash

# "system.preferences.startupdisk"
# "system.preferences.appstore"
# "system.preferences.cloudsetup"
# "system.preferences.icloud"
# "system.preferences.family"
# "system.preferences.siri"
# "system.preferences.wallet"
# "system.preferences.sidecar"
# "com.apple.systempreferences"
# "system.preferences.security"

# Set of preferences you want to allow
prefs=(
  "system.preferences"
  "system.settings"
  "system.preferences.datetime"
  "system.settings.datetime"
  "system.preferences.network"
  "system.settings.network"
  "system.preferences.energysaver"
  "system.settings.energysaver"
  "system.preferences.printing"
  "system.settings.printing"
  "system.preferences.accessibility"
  "system.settings.accessibility"
  "system.preferences.accounts"
  "system.settings.accounts"
  "system.preferences.bluetooth"
  "system.settings.bluetooth"
  "system.preferences.desktopscreeneffect"
  "system.settings.desktopscreeneffect"
  "system.preferences.displays"
  "system.settings.displays"
  "system.preferences.dock"
  "system.settings.dock"
  "system.preferences.expose"
  "system.settings.expose"
  "system.preferences.extensions"
  "system.settings.extensions"
  "system.preferences.general"
  "system.settings.general"
  "system.preferences.internetaccounts"
  "system.settings.internetaccounts"
  "system.preferences.keyboard"
  "system.settings.keyboard"
  "system.preferences.mouse"
  "system.settings.mouse"
  "system.preferences.notifications"
  "system.settings.notifications"
  "system.preferences.parental-controls"
  "system.settings.parental-controls"
  "system.preferences.printers"
  "system.settings.printers"
  "system.preferences.sharing"
  "system.settings.sharing"
  "system.preferences.softwareupdate"
  "system.settings.softwareupdate"
  "system.preferences.speech"
  "system.settings.speech"
  "system.preferences.machine"
  "system.settings.machine"
  "system.preferences.timemachine"
  "system.settings.timemachine"
  "system.preferences.trackpad"
  "system.settings.trackpad"
  "system.preferences.sound"
  "system.settings.sound"
  "com.apple.wifi"
  "system.services.systemconfiguration.network"
)

# Grant access to each preference
for pref in "${prefs[@]}"; do
  sudo /usr/bin/security/security authorizationdb write "${pref}" allow
done

sudo /usr/bin/security authorizationdb write system.preferences.datetime authenticate-session-owner-or-admin
sudo /usr/bin/security authorizationdb write system.settings.datetime authenticate-session-owner-or-admin
sudo /usr/libexec/airportd prefs RequireAdminNetworkChange=NO RequireAdminIBSS=NO

# Give Everyone Print Operator Access
sudo dseditgroup -o edit -n /Local/Default -a everyone -t group lpadmin
