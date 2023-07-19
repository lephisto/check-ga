# check-ga

Having a running guest-agent is important in Virtualisation Environments. It brings some convenience features like showing you the Network Configuration in the Proxmox VE Management Console. A lot more important is that it takes care of providing your with consistent snapshots of your Filesystems when doing Snapshot Backups.

From time to time it happens that qemu-guest-agent instances die, there are several reasons for this: OOM Killer, unattended-upgrades that failed to do a proper restart, you name it.

This little script helps you to keep track if all your VMs have a proper qemu-guest-agent running by issueing a qm-ping to the guest VM. The results are written into an InfluxDB, and you can easily visualize it in your Dashboards. An example Dashboard for Grafana is provided as well.

## Installation:

- Clone the Git repo: 
`git clone https://github.com/lephisto/check-ga /opt/check-ga`

- Provide credentials to your InfluxDB instance, edit:
`https://github.com/lephisto/check-ga`

- Test if everything is working with 
`/opt/check-ga/check-ga check`
