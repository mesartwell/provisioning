# Linux setup ansible playbooks

This Ansible playbook installs/configures most of the software that I use on
linux machines.

## Usage

You'll need to bootstrap this whole process by first installing
ansible:

```sudo apt-get install ansible -y```

Pull the required roles from ansible-galaxy:

```sudo ansible-galaxy install -r requirements.yml```

Then simply execute the desired playbook:

```ansible-playbook htpc.yml```

## Playbooks

* `base-linux.yml`: The bare essentials for all linux systems. Installs needed
                    tools and sets timezone.
* `server-linux.yml`: Solid server foundation. Installs packages like docker,
                      fail2ban, openssh, grafana, prometheus.


