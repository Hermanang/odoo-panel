# Role wkhtmltopdf

Role Ansible pour installer wkhtmltopdf selon la distribution, version et architecture.

## Fonctionnalités

- Installation automatique basée sur la distribution, version et architecture
- Support complet pour Debian 9/10/11 et Ubuntu 16.04/18.04/20.04/22.04
- Support des architectures : amd64, i386, arm64, ppc64el, raspberrypi
- Vérification de l'installation existante (idempotent)
- Désinstallation complète avec purge
- Nettoyage automatique des fichiers temporaires
- Validation post-installation

## Distributions supportées

### Debian
- 9 (stretch) : amd64, i386, arm64, raspberrypi
- 10 (buster) : amd64, i386, arm64, ppc64el, raspberrypi  
- 11 (bullseye) : amd64, i386, arm64, ppc64el, raspberrypi

### Ubuntu
- 16.04 (xenial) : amd64, i386, arm64
- 18.04 (bionic) : amd64, i386, arm64, ppc64el
- 20.04 (focal) : amd64, arm64, ppc64el
- 22.04 (jammy) : amd64, arm64, ppc64el

## Utilisation

### Installation standard
```yaml
- hosts: all
  roles:
    - role: wkhtmltopdf
```

### Désinstallation
```yaml
- hosts: all
  roles:
    - role: wkhtmltopdf
      tags: uninstall
```

### Avec tags spécifiques
```bash
# Installation seulement
ansible-playbook playbook.yml --tags wkhtmltopdf

# Désinstallation seulement  
ansible-playbook playbook.yml --tags uninstall

# Validation seulement
ansible-playbook playbook.yml --tags verify
```

## Variables

Les URLs de téléchargement sont définies dans `defaults/main.yml` avec une structure hiérarchique :
- Distribution (debian, ubuntu)
- Version (9, 10, 11, 16.04, 18.04, 20.04, 22.04)
- Architecture (amd64, i386, arm64, ppc64el, raspberrypi)

## Best practices implémentées

1. **Idempotence** : Vérification avant installation
2. **Gestion des erreurs** : Message d'erreur clair pour les combinaisons non supportées
3. **Nettoyage** : Suppression automatique des fichiers .deb temporaires
4. **Validation** : Handler pour vérifier l'installation réussie
5. **Désinstallation complète** : Purge et autoremove

## Tests

Un playbook de test est disponible : `test_wkhtmltopdf.yml`

```bash
# Tester l'installation
ansible-playbook test_wkhtmltopdf.yml --tags wkhtmltopdf

# Tester la désinstallation
ansible-playbook test_wkhtmltopdf.yml --tags uninstall

# Tester l'idempotence
ansible-playbook test_wkhtmltopdf.yml --tags idempotence
