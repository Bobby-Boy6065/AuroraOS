# Aurora OS — Surface Pro 3 project (V4)

Aurora OS is a Debian live-build project targeting the Microsoft Surface Pro 3. It uses XFCE/GTK3, an Aurora top panel, Plank dock, themed welcome page, Control Center, and GNOME Software for real package installs. V4 adds a searchable full-screen launcher, appearance controls, touch/tablet helper, and LightDM greeter configuration.

## V4 changes
- Full-screen application launcher with searchable touch-friendly tiles (`aurora-launcher`).
- Appearance window for dark/light presets, wallpaper, and tablet-mode adjustments (`aurora-appearance`).
- `aurora-theme-switch dark|light` and `aurora-tablet-mode on|off` user-session tools.
- Top-panel menu links for launcher, theme modes, and tablet/desktop mode.
- LightDM GTK Greeter Aurora wallpaper/theme settings.
- V4 notes and test/build guide under `docs/`.

## Current functionality and limits
V4 components are source files and configuration. Launcher tiles launch local system apps. Theme, wallpaper, and tablet helpers call XFCE tools. LightDM config is a configuration change only. Existing XFCE handles window dragging, resizing, workspaces, and application switching.

Not yet built/verified: custom window manager/compositor, dock magnification, automatic touch gesture service/tablet detection, installer safety workflow end-to-end, recovery image, ISO compilation, and Surface hardware tests. Package availability may require edits depending on Debian mirror state.

## Build
On a Debian/Ubuntu build host, install the tools listed in `docs/v4-build-and-test.md`, then run `sudo ./scripts/build-iso.sh` from this project directory. Use `./scripts/check-v4.sh` for source and shell syntax checks.

## Safety
Test in a UEFI virtual machine before booting physical hardware. Back up the Surface Pro 3 before any disk installation. The project does not automatically erase drives. The V4 ZIP is not a prebuilt ISO and has not been hardware-tested.

## ISO build without a Linux PC (Windows users)
A GitHub Actions cloud build workflow is included at `.github/workflows/build-iso.yml`. See `docs/windows-cloud-iso-build.md` for instructions to upload the project to a GitHub repository, run the build in GitHub's hosted Ubuntu environment, and download the ISO artifact. The workflow must complete successfully; it has not been run from this environment.
