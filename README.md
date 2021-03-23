# haveged

[![Build Status](https://drone.osshelp.ru/api/badges/ansible/haveged/status.svg)](https://drone.osshelp.ru/ansible/haveged)

Role for haveged installation and configuration.

## Usage (example)

```yaml
    - role: haveged
      haveged_custom_params:
        - { key: "test", value: "test" }
```

## Available parameters

### Main

| Param | Default | Description |
| -------- | -------- | -------- |
| `haveged_setup` | `full` | Setup mode. See [OSSHelp KB article](https://oss.help/kb4895) |
| `haveged_default_params` | `[{key: "w", value: "1024"}, {key: "p", value: "/var/run/haveged.pid"}]` | default params for haveged config |
| `haveged_custom_params` | `[]` | custom params for haveged config |

## Known issues

### -w option in containers

In non-privileged containers, we cannot set the option `-w` for haveged, because it requires changes to /proc/sys/kernel/random/write_wakeup_threshold, which is prohibited.

## FAQ

None, so far.

## Useful links

- [Official documentation](https://github.com/jirka-h/haveged)
- [DigitalOcean tutorial](https://www.digitalocean.com/community/tutorials/how-to-setup-additional-entropy-for-cloud-servers-using-haveged)

## TODO

None, so far.

## License

GPL3

## Author

OSSHelp Team, see <https://oss.help>
