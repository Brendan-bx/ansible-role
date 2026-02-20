# k3d-lab

Role Ansible pour installer et configurer un laboratoire k3d (Kubernetes en Docker).

## Description

Ce rôle installe et configure un cluster Kubernetes local en utilisant k3d. Il installe Docker, k3d, kubectl et crée un cluster k3d avec les paramètres spécifiés.

## Prérequis

- Système d'exploitation : Linux (Debian/Ubuntu, Red Hat, SUSE)
- Accès root ou sudo

## Variables

Les variables par défaut sont définies dans `defaults/main.yaml`. Les principales variables sont :

- `k3d_cluster_name` : Nom du cluster (défaut: `my-cluster`)
- `k3d_agents` : Nombre d'agents dans le cluster (défaut: `2`)
- `k3d_port_mapping` : Mapping des ports (défaut: `30080:30080@loadbalancer`)
- `k3d_docker_user` : Utilisateur à ajouter au groupe docker (défaut: `{{ ansible_user_id }}`)
- `k3d_manifest_file` : Nom du manifest Kubernetes à déployer (défaut: `nginx.yaml`)

## Exemple d'utilisation

```yaml
- hosts: localhost
  roles:
    - k3d-lab
  vars:
    k3d_cluster_name: my-k3d-cluster
    k3d_agents: 3
```

## Auteur

Brendan

## Licence

MIT
