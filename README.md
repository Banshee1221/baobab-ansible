# BAOBAB-ANSIBLE

> Baobab LIMS is an open-source laboratory information management system (LIMS) software that will ensure that researchers can track the lifecycle of a biospecimen in the laboratory from receipt to storage and reuse. This software ensures that sufficient metadata is captured.

This ansible playbook is used to deploy a production-ready [Baobab LIMS](https://github.com/BaobabLims/baobab.lims) instance onto a server.

**NB: Please note that this will deploy Baobab and Nginx onto each machine listed in your ansible hosts file. This playbook does not currently support additional features other than a blanket deployment onto a single host.**

**It is currently recommended to only use a single server for this playbook.**

## Usage

- Firstly, clone the repo and download the submodules as well:

    ```shell
    git clone https://github.com/Banshee1221/baobab-ansible.git
    cd baobab-ansible
    git submodule update --init --recursive
    ```

- Create a hosts file for ansible, e.g:

    ```ini
    [baobab]
    baobab-test.sanbi.ac.za ansible_user=ubuntu
    ```

- Edit the `group_vars/all.yml` file to reflect the settings you need. You mainly just need to edit the `server_hostname` and `plone_initial_password`.

- Execute the play with: `ansible-playbook -i name_of_hostsfile site.yml`. **_The buildout part of plone will take some time to execute_**.

---

![Baobab Logo](https://baobablims.org/wp-content/uploads/2018/11/cropped-Baobab-LOGO.png)