# Install supertuxkart

## Install the latest Python and setup a new Python virtualenv

```bash
pkcon install -y git
pkcon install -y python3
pkcon install -y python3-pip
pkcon install -y python3-virtualenv
virtualenv-3 ~/python
```

### Load the python virtual environment and activate it for new terminals

```bash
source ~/python/bin/activate
echo "source ~/python/bin/activate" | tee -a ~/.bashrc
```

### Configure the terminal to load the ~/.local libraries

```bash
echo "export LD_LIBRARY_PATH=${HOME}/.local/lib64:${HOME}/.local/lib" | tee -a ~/.bashrc
```

## Install the latest Ansible

```bash
pip install setuptools_rust wheel
pip install --upgrade pip
pip install ansible
```

## Install the supertuxkart ansible role

### Create a directory for the ansible role. 

```bash
install -d ~/.ansible/roles/computate.computate_supertuxkart
```

### Clone the supertuxkart ansible role. 

```bash
git clone git@github.com:computate-org/computate_supertuxkart.git ~/.ansible/roles/computate.computate_supertuxkart
```

## Run the supertuxkart ansible playbook to install the application locally. 

```bash
cd ~/.ansible/roles/computate.computate_supertuxkart
ansible-playbook install.yml
```

