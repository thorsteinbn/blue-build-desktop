# Setup Vscode with terminal and podman from host

## VScode settings


Add the following to enable bash terminal from the host system

```json
    "terminal.integrated.profiles.linux": {

        "bash": {
        "path": "host-spawn",
        "args": ["bash"]
        }
    },
```

Create the following script, place it for instance in ~/.local/podman-host

```bash
#!/bin/sh
exec flatpak-spawn --host podman "${@}"
```

Set this script as the dockerPath

```json
    "dev.containers.dockerPath": "/var/home/[username]/.local/podman-host",
```
