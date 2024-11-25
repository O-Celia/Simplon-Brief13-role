# ANSSI-RECOM

## Description

Ce rôle Ansible applique des configurations de sécurité basées sur des recommandations ANSSI, NIST, et DISA-STIG. Il automatise des tâches pour renforcer la sécurité des systèmes cibles.

## Prérequis

- Ansible 2.9+ installé.
- Accès root ou sudo sur les machines cibles.
- Dépendances Python éventuelles (ex : boto pour AWS, si applicable).

## Variables

Les principales variables configurables sont définies dans :
- defaults/main.yml : Variables par défaut.
- vars/main.yml : Variables spécifiques.

Exemple de variables utilisées dans ce rôle :
```code
DISA_STIG_RHEL_08_010381: true
low_complexity: true
restrict_strategy: true
```

## Dépendances

Aucune dépendance externe n'est nécessaire pour ce rôle.
Exemple de Playbook
```code
- hosts: servers
  roles:
    - { role: ANSSI-RECOM }
```

## Tests

Pour tester le rôle sur une machine locale, utilisez le fichier test.yml :
```code
ansible-playbook -i inventory test.yml
```

## Tags

Les tâches sont étiquetées avec des standards de sécurité pour une exécution ciblée :

- CCE-82202-3
- DISA-STIG-RHEL-08-010381
- NIST-800-53-CM-6(a)
