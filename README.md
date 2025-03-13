# 🛡️ SAE 61 – Sécurisation d’un service web

## 🎯 Objectif

Mettre en place une infrastructure virtualisée pour héberger un **service web sécurisé**, en appliquant des techniques de **durcissement système** et de **filtrage réseau**.

---

## 📄 Cahier des charges

- Créer deux machines virtuelles :
  - Un **serveur web** sous Nginx
  - Un **client** pour les tests
- Mettre en place un **réseau privé** entre les VMs
- Sécuriser le serveur :
  - Configuration d’un **pare-feu restrictif**
  - Durcissement des services essentiels (SSH, système)
- Réaliser des **tests de pénétration**
- Automatiser le déploiement avec **Vagrant** et des scripts

---

## 🛠️ Mise en place

### Environnement

- Hôte : Debian 12
- Virtualisation : Vagrant + libvirt
- Box : `generic/ubuntu1804`

### Configuration

- Réseau interne entre les deux VMs
- IP statiques définies
- Provision automatique via :
  - `provision-server.sh` : installation + sécurisation du serveur
  - `provision-client.sh` : outils de test réseau

### Sécurisation

- Installation de **Nginx**
- Blocage des ports non utilisés
- Autorisation uniquement des ports 22 (SSH) et 80 (HTTP)
- Configuration `iptables` minimale et efficace
- Durcissement SSH (`sshd_config`) et noyau (`sysctl`)

---

## 🔎 Tests réalisés

- Analyse de ports avec `nmap`
- Requêtes HTTP avec `curl`
- Simulation d’accès non autorisés pour tester le firewall

---

## ✅ Résultats

- Le serveur est accessible uniquement via les ports autorisés
- Le système est allégé et sécurisé
- Le tout est déployé automatiquement via Vagrant

---

## 🗓️ Suivi de projet

- **Séance du 03/03/2025 – 13h00 à 16h00**  
  Première ébauche du sujet. Documentation. Création du répo GitHub.

- **Séances du 05/03/2025 – 08h30 à 11h30 et 14h30 à 17h30**  
  Création d'une VM Debian. Mise en place d'un premier Vagrantfile.

- **Séance du 06/03/2025 – 13h00 à 16h00 et 07/03/2025 – 08h30 à 11h30**  
  Création du README. Continuité du Vagrantfile.

- **Séances du 10/03/2025 et 11/03/2025 – 08h30 à 11h30**  
  Continuité du Vagrantfile.

- **Journée du 12/03/2025 – 08h30 à 16h00**  
  Sécurisation du serveur nginx.

- **Séance du 13/03/2025 – 13h00 à 16h00**  
  Diaporama, schéma.

- **Séance du 14/03/2025 – 08h30 à 11h30**  
  *(À compléter)*

- **Soutenance orale – 14/03/2025 – 13h00 à 16h00** 🎤

---

