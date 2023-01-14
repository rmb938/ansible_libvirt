# ansible_libvirt
Ansible for LibVirt KVM Hosts

## Requirements

* Network bridge `br0` with static IP and default gateway setup
* Tailscale
  * `dnf config-manager --add-repo https://pkgs.tailscale.com/stable/fedora/tailscale.repo`
  * `dnf install tailscale`
  * `tailscale up --ssh`
* SELinux Disabled due to https://github.com/tailscale/tailscale/issues/4908
  * `sed -i 's/SELINUX=enforcing.*/SELINUX=permissive/' /etc/selinux/config`
* Ansible User created and setup with sudo
  * `useradd ansible`
  * `echo "ansible ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/ansible`
