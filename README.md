Useful links

- https://learn.microsoft.com/en-us/community/content/wsl-user-msft-kernel-v6
- https://github.com/microsoft/WSL2-Linux-Kernel?tab=readme-ov-file#build-instructions
- https://github.com/microsoft/WSL/issues/8709#issuecomment-1212912844
- https://askubuntu.com/questions/1379425/system-has-not-been-booted-with-systemd-as-init-system-pid-1-cant-operate#:~:text=Option%201%3A%20%22The%20old%20way%22
- https://github.com/microsoft/WSL/issues/11771#issuecomment-2272556114


1. Checkout https://github.com/microsoft/WSL2-Linux-Kernel/tree/linux-msft-wsl-5.15.y
2. Replace contents of `Microsoft/config-wsl` with `config-wsl`
3. Run `make -j$(nproc) KCONFIG_CONFIG=Microsoft/config-wsl`
4. Run `sudo make modules_install headers_install`
5. Move `arch/x86/boot/bzImage` to Windows
6. Update `%USERPROFILE%/.wslconfig` with kernel path
7. Restart WSL
8. Run `sudo service apparmor start`
