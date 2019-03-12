# Mac Ansible Playbook

This playbook installs and configures most of the software I use on my Mac. It's a fork of geerlingguy/mac-dev-playbook.

## Installation

> Note: If ansible is installed, run `brew uninstall ansible; pip uninstall ansible`. If python3 is installed run `pip uninstall pip; brew uninstall python`

xcode-select --install
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py
pip install ansible
git clone https://github.com/JaredBoone/mac-playbook
cd mac-playbook
ansible-galaxy install -r requirements.yml
ansible-playbook main.yml -i inventory -K

## Overriding Defaults

You can override any of the defaults configured in `default.config.yml` by creating a `config.yml` file and setting the overrides in that file. Any variable can be overridden in `config.yml`; see the supporting roles' documentation for a complete list of available variables.

## Configuration

My [dotfiles](https://github.com/jaredboone/dotfiles) are installed into the current user's home directory, including the `.osx` dotfile for configuring many aspects of macOS for better performance and ease of use. You can disable dotfiles management by setting `configure_dotfiles: no` in your configuration.