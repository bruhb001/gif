# Slovakia Changes

This document details the changes made in Slovakia. Note alot of history will
be left out of this document due to it only being started in late March 2021.

# v1.97.3

- Bug fixes
  - attack command now shows method enhanced max time rather than user max time

# v1.95.5

- Bug fixes
  - Power saving freeze bug

# v1.95.4

- Bug fixes

# v1.95.2

- TermFX stability improvements

# v1.95.1

- Duck command
  - Search quick answers with Duckduckgo

# v1.93.2

- ADD: General background improvements

# v1.93.1

- ADD: General stability improvements

# v1.93.0

- Update: Rust iplookup replaces old deprecated bin command
  - Provides IPv4 and IPv6 validation on input
- Remove: geobssid lookup bin command
- Add: Reseller custom command meta data: `reseller=true`
- Add: Reseller termFX: `<<$reseller>>`

# v1.92.0

- Add: Auto convert method names to lowercase (prevents customers doing it wrong)

# v1.91.0

- Add: Log config file being loaded to improve verbosity of error messages
- Removed: Ulimit attempt to increase max open file (was broken)

# v1.90.0

- Add: Max time is no longer 24 hours and can be set in options.ini
- Add: API Edition supports bracket attack syntax (reduces user error)
- Add: Attack user limit override (Moderation & Management DLC only)
- Add: Port 0 resolves to a random port
- Add: better failed attack debug info

### Breaking changes

- Update `options.ini`
- Update `attacks.json`
- Update `api-attacks.json`

# v1.-.-

No version/change logs were maintained for the versions between v1.56.0 and v1.90.0

# v1.56.0

- Command overrides
- Users command user's total attacks
- Users command user's last target
- Inline attack command tab complete based on individual user usage

# v1.55.0

- users command pager
- sessions last active/idle time

# v1.54.2

- Signalling service optimisations
- Users add username must not contain spaces or tabs
- Reload attacks.json via admin command
- PHP bin command support

# v1.54.0

- Users commands omit field to make it all fit on your screen
- Users view see plan expire in days
- Passwd minimum password length (ini configurable)
- KV store auto int conversion method
- Custom themes
- User command highlight key values
- Qbot support

# v1.53.2

- Notification when failed to connect to DB on startup
- Notification if DoxyProxy is enabled

# v1.53.1

- Switched over to syrinsecurity/doxyproxy client lib

# v1.53.1

- Mirai support!
- Slaves command listing the sources name
- Escape escape characters in log command

# v1.52.0

- KV value store for settings in a .ini file
- Time to wait before closing the connection
  - ini configurable

# v1.51.2

- **Bug fixes**
  - Disabled commands showing in the help command
  - Disabled commands still being accessible
- DoxyProxy support added
