# Fedora GNOME Ansible Playbook

Petit playbook pour configurer un poste Fedora GNOME (extensions, paquets, Flatpak, dconf).

Prérequis
- Ansible installé
- Flatpak installé sur la machine cible

Installer les collections requises:

```bash
ansible-galaxy collection install -r requirements.yml
```

Vérifications et exécution

- Vérifier la syntaxe:

```bash
ansible-playbook --syntax-check playbook.yml
```

- Exécution en dry-run:

```bash
ansible-playbook -C -v playbook.yml
```

- Lancer le playbook (peut nécessiter sudo):

```bash
ansible-playbook -K playbook.yml
```

Notes
- `tasks/dnf.yml` installe des paquets système.
- `tasks/flatpak.yml` ajoute le remote Flathub et installe les applications Flatpak en utilisant `community.general`.
- Si vous voulez installer Flatpaks par utilisateur, ajustez `become` à `false` dans `tasks/flatpak.yml`.
