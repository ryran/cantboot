# Can't-boot First-Responders: Booting to kernel panic

### System boots to kernel panic
1. Have customer start downloading the latest DVD iso (but the same major version) from https://access.redhat.com/downloads in case rescue mode ends up being required
1. Take screenshot of console or if that's not possible, take photo with a camera & force system reset
1. In bootloader:
  1. As soon as bootloader appears, press space bar to stop countdown timer (to prevent auto-booting)
  1. Take note of how many menu entries are present
  1. Remove `rhgb` and `quiet` args from kernel cmdline and boot
1. Take screenshot of console or if that's not possible, take photo with a camera & force system reset again
1. In bootloader:
  1. Remove `rhgb` and `quiet` args from kernel cmdline again
  1. Add `debug` to kernel cmdline and boot
1. Take screenshot of console or if that's not possible, take photo with a camera
1. Ask if they have console logging configured (serial, iDRAC, iLO, etc)
  - If so, get logs from most recent attempt with `debug`
1. [De-escalate + capture more data](de-escalate.html)