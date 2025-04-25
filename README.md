# Snort-IPTables-Project

## Description
Ce projet a été réalisé dans le cadre de mes études pour mettre en place un système de détection d'intrusion (IDS) et de blocage des attaques réseau. J'ai utilisé **Snort** pour détecter les scans et les attaques, et **IPTables** pour journaliser et bloquer le trafic malveillant.

### Objectifs
- Installer et configurer Snort sur une VM Ubuntu (IP : 192.168.1.92).
- Détecter les scans SYN et les tentatives d'injection SQL.
- Configurer IPTables pour bloquer le trafic malveillant provenant d'une VM Kali (IP : 192.168.1.90).
- Tester le système avec des attaques simulées.

## Contenu du dépôt
- **[resume_complet.pdf](resume_complet.pdf)** : Rapport détaillé de toutes les étapes du projet (installation, configuration, tests).
- **[presentation.pdf](presentation.pdf)** : Présentation sous forme de diapositives pour une soutenance.
- **[resume_complet.tex](resume_complet.tex)** : Code LaTeX du rapport.
- **[presentation.tex](presentation.tex)** : Code LaTeX de la présentation.

## Étapes du projet
1. **Installation de Snort et DAQ** :
   - Mise à jour du système et installation des dépendances.
   - Compilation et installation de DAQ et Snort à partir des sources.
2. **Configuration de Snort** :
   - Création des répertoires et configuration de `snort.conf`.
   - Ajout de règles communautaires et personnalisées.
3. **Tests de détection** :
   - Lancement de scans SYN et d'injections SQL depuis Kali.
   - Vérification des alertes dans la console.
4. **Configuration d'IPTables** :
   - Création d'une chaîne personnalisée pour journaliser et bloquer le trafic.
   - Blocage des scans et des injections SQL.
5. **Résultats** :
   - Les scans et attaques sont détectés et bloqués avec succès.

## Prérequis
Pour reproduire ce projet, vous aurez besoin des éléments suivants :

### Environnement
- Une machine virtuelle Ubuntu (IP : 192.168.1.92 dans mon cas).
- Une machine virtuelle Kali Linux (IP : 192.168.1.90 dans mon cas) pour simuler des attaques.
- Mettre les 2 VMs sous le réseaux bridged pour permettre la communication entre les 2 VMs
- Connexion Internet pour télécharger les fichiers (Snort, DAQ, règles communautaires).

### Logiciels et dépendances
- Privilèges root ou `sudo` sur la VM Ubuntu pour installer les dépendances et configurer IPTables.
- Paquets nécessaires pour Snort et DAQ :
  ```bash
  sudo apt install -y build-essential libpcre3-dev libdumbnet-dev bison flex zlib1g-dev liblzma-dev openssl libssl-dev pkg-config libhwloc-dev cmake
