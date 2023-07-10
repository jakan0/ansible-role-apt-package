# ansible-role-apt-package

This Ansible role handles apt cache updates, package installs, upgrades, and
removals.

## Variables

The following table lists the available variables and their default values:

| Variable                       | Default                    | Description                           |
| ------------------------------ | -------------------------- | ------------------------------------- |
| `apt_package_cache_valid_time` | `86400`                    | Cache validity duration in seconds.   |
| `apt_package_install`          | `[]`                       | List of package names to install.     |
| `apt_package_remove`           | `[]`                       | List of package names to remove.      |
| `reboot_required_file`         | `/var/run/reboot-required` | Path to a reboot required flag file.  |
| `reboot_system_throttle`       | `1`                        | How many hosts to reboot in parallel. |

## Usage

Please note that, at least for now, the role is not available from Ansible
Galaxy. To retrieve the role, run the following command in your `roles`
directory:

```shell
git clone https://github.com/jakan0/ansible-role-apt-package.git jakan0.apt_package
```

Once the role has been retrieved, a simple playbook that utilizes this role
would look something like this:

```yaml
- hosts: debian
  roles:
    - role: jakan0.apt_package
      vars:
        apt_package_install:
          - apt-transport-https
          - ca-certificates
```

## License

MIT
