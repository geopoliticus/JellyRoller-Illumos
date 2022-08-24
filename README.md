# JellyRoller - The CLI Jellyfin Controller Utility for Linux and Windows

JellyRoller is an open source CLI Jellyfin Controller written in Rust that works on Windows and Linux.  It's primary purpose is to allow administration of a Jellyfin application from the command line.

## How it works
Currently, JellyRoller authenticates as a user (admin rights required) and stores the authentication token within its configuration, similar to how an API key would be stored.  Due to some issues with API keys in Jellyfin this is the only supported method of authentication.  Once authenticated, JellyRoller uses the Jellyfin API to manage the server.

## Usage Information
```
jellyroller 
A CLI controller for managing Jellyfin  

USAGE:
    Windows:    jellyroller.exe <SUBCOMMAND>           
    Linux:      jellyroller <SUBCOMMAND>

OPTIONS:
    -h, --help    Print help information

SUBCOMMANDS:
    add-user                     Creates a new user
    delete-user                  Deletes an existing user
    disable-user                 Disable a user
    enable-user                  Enable a user
    get-devices                  Show all active devices
    get-scheduled-tasks          Show all scheduled tasks and their status
    grant-admin                  Grants the specified user admin rights
    help                         Print this message or the help of the given subcommand(s)
    list-logs                    Displays the available system logs
    list-users                   Lists the current users
    reconfigure                  Reconfigure the connection information
    remove-device-by-username    Removes all devices associated with the specified user
    reset-password               Resets a user's password
    revoke-admin                 Revokes admin rights from the specified user
    scan-library                 Start a library scan
    server-info                  Displays the server information
    show-log                     Displays the requested logfile
```

## Installation
**Note:**  All installation instructions assume the end-user can handle adding the application to their user's PATH.
### Building From Source
Currently built with rustc 1.63.0.  If building on a Linux machine, you may need to install openssl-devel.
```
git clone <git location>
cd jellyroller
cargo build
```
### Downloading Release
See Releases for binaries.  I can currently build for 64-bit Windows, 64-Bit Linux
## Roadmap
Please see below for my current ideas.  I will be organizing these into issues and releases in the coming days.  I am a firm believer in "dogfooding" so the commands I felt were needed (ones I will most often use) for an initial release are in place.  Please feel free to open feature requests via an issue or contacting me in the JellyRoller Matrix room (https://matrix.to/#/#jellyroller:matrix.org).  I am also freely open to coding suggestions.

| Feature/Enhancement | Priority |
| ------------------- | -------- |
| Output beautification | Medium |
| Scheduled Task Execution Support | High |
| Code stucture cleanup | Low/Medium |
| Documentation of test process | Medium |
| Implementation of automatic testing | High | 