# AWX K8s Ansible

Warning: This playbook is alpha quality and should only be used by the brave!

This playbook spawns a ready-to-use AWX system and Rancher on a highly available RKE2 K8s cluster. It is an experimental fork of my [https://github.com/PC-Admin/awx-ansible](awx-ansible) repository.

AWX is a tool that can be used to manage multiple servers with Ansible.
Ideally this system can manage the updates, configuration, backups and monitoring of many servers/services on its own. 


## Previews

![awx-backup](https://user-images.githubusercontent.com/29645145/213112337-e79c990a-909a-454d-91ae-ee23353478c8.jpg)

![rancher](https://user-images.githubusercontent.com/29645145/213112353-7ab20285-2ca1-44ed-8da4-ea044b8fa5a4.jpg)


## Installation

To configure and install this AWX setup on either DigitalOcean or your own servers, follow the [Install_AWX.md in the docs/ directory](docs/Install_AWX.md).


## License

This playbook is copyrighted by Michael Collins under the [MIT License](licenses/MIT_License_Michael_Collins.txt).


## Other Licenses

"AWX" is a registered trademark of Red Hat, Inc. Please consult their [AWX Trademark Guidelines](https://github.com/ansible/awx-logos/blob/master/TRADEMARKS.md) for more information.

The AWX source code is copyrighted to Red Hat Inc, and is made available under the [Apache License 2.0](https://github.com/ansible/awx/blob/devel/LICENSE.md).

Rancher is Kubernetes management tool, it is copyrighted to Rancher Labs and is made available under the [Apache License 2.0](https://github.com/rancher/rancher/blob/release/v2.7/LICENSE).
