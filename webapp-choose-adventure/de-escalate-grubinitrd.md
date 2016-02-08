# Can't-boot First-Responders: De-escalate - GRUBMAGIC

### De-escalation work-around #1: Try to GRUB your way out of it

1. In GRUB, press `e`

1. Go to initrd line and press `e`

1. Use arrow keys and `Backspace` or `Del` to delete everything except `initrd /`

1. Press the `Tab` key multiple times to look for alternate/backup files with `initrd` (RHEL < 6) or `initramfs` in their name; try booting each one in turn by finishing the name, pressing `Enter` and then `b`

  - [One of the alternate initrd/initramfs files booted!](congrats.html)

  - [None of the alternates booted or there is only 1 initrd/initramfs file!](de-escalate-rescue.html)