macOS - macOS Bootstrap Playbook
================================

On a new machine, run:

```bash
xcode-select --install
softwareupdate --install-rosetta

curl "https://bootstrap.pypa.io/get-pip.py" -o /tmp/get-pip.py
sudo python3 /tmp/get-pip.py
sudo pip install ansible
export PYTHONUNBUFFERED=1
export PYTHONIOENCODING='utf-8'
ansible-pull -K -d /tmp/bootstrap -i localhost, -e 'ansible_python_interpreter=/usr/bin/python3' -U https://github.com/bts-bastion/macos.git
# or to work from a branch
# ansible-pull -K -d /tmp/bootstrap -i localhost, -e 'ansible_python_interpreter=/usr/bin/python3' -U https://github.com/bts-bastion/macos.git -C "bts/bastion"
```

## TODO
* mise install languages (rust, golang, poetry, python)
* configure git (Done)
* configure git GPG signing
* install GPG suite
* capslock-esc swap https://stackoverflow.com/questions/127591/using-caps-lock-as-esc-in-mac-os-x/40254864#40254864 https://apple.stackexchange.com/questions/283252/how-do-i-remap-a-key-in-macos-sierra-e-g-right-alt-to-right-control