# ansible-macos-finder
Ansible role to manage finder settings in macOS.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-finder.svg)](https://travis-ci.org/feffi/ansible-macos-finder) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-finder/total.svg)](https://github.com/feffi/ansible-macos-finder) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-finder.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-finder) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-finder.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-finder) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-finder.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-finder) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-finder/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-finder.git
  name: feffi.macos-finder
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
macos_finder:
  # Show folders before files
  sort_folder_first: true

  # Show Hidden Files
  all_files: true

  # Show Full Path in Finder Title
  show_path: true

  # Set window animations and Get Info animations
  animated: false

  # Empty Trash securely by default
  secure_trash: true

  # When performing a search, search the current folder by default
  search_current_default: "SCcf"

  # Set warning when changing a file extension
  warning_change_ext: false

  # Set Finder view mode, Icon View = `icnv`, List View = `Nlsv`, Column View = `clmv`, Cover Flow = `Flwv`
  view_mode: "clmv"

  # Set Default Finder Location
  default_location: "PfLo"

  # Set Default Finder Location path
  default_location_path: "file://${HOME}"

  # Allow text selection in Quick Look
  select_quicklook: true

  # Show 'Quit Finder' Menu Item
  allow_quit_finder: true

  # Show icons for external drives on the desktop
  show_external_drives: true

  # Show icons for hard drives on the desktop
  show_harddrives: true

  # Show icons for servers on the desktop
  show_servers: true

  # Show icons for removable media on the desktop
  show_removables: true

  # Show path in path bar
  show_pathbar: true

  # Show status bar in Finder
  show_statusbar: true

  # Warning before emptying the Trash
  warn_trash_empty: false

  # Set creation of .DS_Store files on network volumes
  ds_files: false

  # Enable AirDrop over Ethernet and on unsupported Macs running Lion
  airdrop: true

  # Show all filename extensions
  extensions: true

  # Enable spring loading for directories
  springload: true

  # Set the spring loading delay for directories
  springload_delay: 0

  # Set Sidebar Icon Size
  sidebar_size: 1

  # Remove duplicates in the “Open With” menu
  remove_duplicates: true

  # Show the ~/Library folder
  hide_library_folder: false

  # Sets default save target to be a local disk, not iCloud
  default_target_icloud: false

  # Enable snap-to-grid for icons on the desktop
  icon_snap_mode: "grid"

  # Size of icons in pixel
  icon_size: 80

  # Grid spacing for icons in pixel
  grid_spacing: 100

  # Show item info near icons
  icon_show_info: true

  # Icon label position: true = bottom, false = right
  icon_label_bottom: true

  # Show sidebar in Finder
  sidebar_show: true

  # Set Finder sidebar width in pixel
  sidebar_width: 134

  # Group files by Kind, Name, Application, Date Last Opened, Date Added, Date Modified, Date Created, Size, Tags, None
  group_by: "Kind"
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_finder:
          sort_folder_first: true
          all_files: true
          show_path: true
          animated: false
          secure_trash: true
          search_current_default: "SCcf"
          warning_change_ext: false
          view_mode: "clmv"
          default_location: "PfLo"
          default_location_path: "file://${HOME}"
          select_quicklook: true
          allow_quit_finder: true
          show_external_drives: true
          show_harddrives: true
          show_servers: true
          show_removables: true
          show_pathbar: true
          show_statusbar: true
          warn_trash_empty: false
          ds_files: false
          airdrop: true
          extensions: true
          springload: true
          springload_delay: 0
          sidebar_size: 1
          remove_duplicates: true
          hide_library_folder: false
          default_target_icloud: false
          icon_snap_mode: "grid"
          icon_size: 80
          grid_spacing: 100
          icon_show_info: true
          icon_label_bottom: true
          sidebar_show: true
          sidebar_width: 134
          group_by: "Kind"
      roles:
        - { role: feffi.macos-finder }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-finder,
            macos_finder: {
              sort_folder_first: true,
              all_files: true,
              show_path: true,
              animated: false,
              secure_trash: true,
              search_current_default: "SCcf",
              warning_change_ext: false,
              view_mode: "clmv",
              default_location: "PfLo",
              default_location_path: "file://${HOME}",
              select_quicklook: true,
              allow_quit_finder: true,
              show_external_drives: true,
              show_harddrives: true,
              show_servers: true,
              show_removables: true,
              show_pathbar: true,
              show_statusbar: true,
              warn_trash_empty: false,
              ds_files: false,
              airdrop: true,
              extensions: true,
              springload: true,
              springload_delay: 0,
              sidebar_size: 1,
              remove_duplicates: true,
              hide_library_folder: false,
              default_target_icloud: false,
              icon_snap_mode: "grid",
              icon_size: 80,
              grid_spacing: 100,
              icon_show_info: true,
              icon_label_bottom: true,
              sidebar_show: true,
              sidebar_width: 134,
              group_by: "Kind"
            }
          }
```
