# 🧹 Chrome Cleanup & Flatpak Management Cheat Sheet

A concise set of reliable commands for removing system-installed Chrome/Chromium and maintaining Flatpak applications.

----------

# 🔥 Remove APT-installed Chrome / Chromium

## Check what is installed

```bash
dpkg -l | grep -E "chromium|chrome"

```

## Remove Chromium

```bash
sudo apt remove --purge chromium-browser chromium

```

## Remove Google Chrome (.deb)

```bash
sudo apt remove --purge google-chrome-stable

```

## Clean unused packages

```bash
sudo apt autoremove --purge

```

----------

# 🧼 Optional: Remove old profile data

⚠️ Only do this if you do NOT need old bookmarks or sessions.

```bash
rm -rf ~/.config/chromium
rm -rf ~/.cache/chromium
rm -rf ~/.config/google-chrome

```

----------

# 📦 Flatpak Management

## Update ALL Flatpak apps and runtimes

```bash
flatpak update

```

## Update only Google Chrome

```bash
flatpak update com.google.Chrome

```

## List installed Flatpak apps

```bash
flatpak list

```

## Remove unused runtimes (recommended cleanup)

```bash
flatpak uninstall --unused

```

***

# 🚀 Run Flatpak Chrome explicitly

```bash
flatpak run com.google.Chrome

```

***

# 🧠 Create a deterministic launcher (recommended)

Avoid confusion between multiple Chrome installations.

```bash
mkdir -p ~/bin

cat > ~/bin/chrome-flatpak << 'EOF'
#!/bin/bash
flatpak run com.google.Chrome "$@"
EOF

chmod +x ~/bin/chrome-flatpak

```

Usage:

```bash
chrome-flatpak

```

***

# 🔍 Sanity Checks

## Verify system Chrome is gone

```bash
which google-chrome

```

## Check Flatpak Chrome version

```bash
flatpak run com.google.Chrome --version

```

***

# 🧩 Useful Flatpak Debug / Permissions

## Show permissions

```bash
flatpak info --show-permissions com.google.Chrome

```

## Override permissions (example: full device access)

```bash
flatpak override --user com.google.Chrome --device=all

```

## Allow full filesystem (if needed)

```bash
flatpak override --user com.google.Chrome --filesystem=host

```

***

# 🧼 Flatpak Deep Cleanup (optional)

Remove unused apps (interactive):

```bash
flatpak uninstall

```

Remove everything not required:

```bash
flatpak uninstall --unused

```

***

# 🧾 Notes

-   Flatpak apps are sandboxed by default.
    
-   Profiles and data live in:
    
    ```
    ~/.var/app/com.google.Chrome/
    
    ```
    
-   System Chrome and Flatpak Chrome do NOT share data.
    

***

# ☕ Final Thought

If something behaves oddly, assume Flatpak permissions before assuming madness.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA3MzMyMTg4Ml19
-->