<p align="center">
  <img src="Logo/LogoLogniscient.png" alt="Logniscient 🔎" width="400">
</p>

# Logniscient 🔎

**Logniscient** est une intelligence artificielle développée par [Groulor](https://github.com/Groulor), [LeNonante](https://github.com/LeNonante) et [Orty](https://github.com/orty-orty) pour assister l'équipe de l'association **Hack'UTT** dans l'analyse de fichiers de logs pour la [European Cyber Cup](https://european-cybercup.com/).

**Sa mission :** transformer l'analyse manuelle des logs réseau (Zeek) en un processus automatisé de détection de cyber-fraude et d'activités malveillantes.

---

## 🚀 Fonctionnalités
- Détection des comportements malveillants à partir de logs.
- Automatisation de l'analyse et classification des connexions suspectes.
- Interface intuitive pour associer les colonnes des logs au modèle d'analyse.

---

## 🛠️ Technologies utilisées
- **Langage** : Python
- **Machine Learning** : LightGBM
- **Traitement des logs** : Pandas
- **Visualisation** : Matplotlib / Seaborn

---

## 📂 Installation

### 📌 Prérequis
Assurez-vous d'avoir **Python installé (>= 3.8)**. Vous pouvez vérifier votre version avec :
```sh
python --version
```

### 📥 Installation des dépendances
Clonez le projet et installez les dépendances nécessaires :
```sh
git clone https://github.com/LeNonante/Logniscient.git
cd Logniscient
pip install -r Distribution/requirements.txt
```

---

## 📖 Utilisation

#### 1️⃣ Lancer le script
Exécutez le script principal :
```sh
python Distribution/main.py
```

#### 2️⃣ Charger un fichier de logs
- Sélectionnez un fichier **CSV** contenant les logs à analyser.
- Les colonnes ayant le même nom que celles attendues seront **automatiquement détectées**.
- Pour les autres, associez-les manuellement via la **liste déroulante** correspondant.
- Résultat renvoyé :
    - Le CSV renvoyé est similaire à celui d'entrée. Voici la description des colonnes rajoutées à la fin de celui-ci :
        - **Prediction** : Peut valoir **malveillant** si cette ligne est identifiée comme malveillante, ou **none** si elle semble sûre.
        - **Probabilité de malveillance** : Indique la probabilité à laquelle la ligne semble malveillante
   
#### Champs attendus
| Champ | Description |
|-------|------------|
| **conn_state** | État final de la connexion (ex. S0, S1, REJ…). |
| **duration** | Durée de la connexion. |
| **ts** | Timestamp du début de la connexion (en Unix timestamp). |
| **local_orig** | Indique si l'origine de la connexion est locale. |
| **local_resp** | Indique si la réponse est locale. |
| **protocol** | Protocole utilisé (ex. TCP, UDP, ICMP). |
| **service** | Service détecté (ex. HTTP, DNS, SSL). |
| **history** | Séquence des événements du handshake réseau. |
| **src_port** | Port source de la connexion. |
| **orig_bytes** | Nombre d’octets envoyés par l’initiateur. |
| **orig_pkts** | Nombre de paquets envoyés par l’initiateur. |
| **orig_ip_bytes** | Nombre total d’octets IP envoyés par l’initiateur. |
| **dest_port** | Port de destination de la connexion. |
| **resp_bytes** | Nombre d’octets envoyés par le répondeur. |
| **resp_pks** | Nombre de paquets envoyés par le répondeur. |
| **resp_ip_bytes** | Nombre total d’octets IP envoyés par le répondeur. |
| **missed_bytes** | Nombre d’octets manqués pendant la capture. |
| **ID** | Identifiant unique de la connexion. |

### 4️⃣ Sauvegarder les résultats
- Validez l’analyse.
- Choisissez un fichier de sortie pour enregistrer les résultats.

---

## 📜 Licence
Ce projet est sous licence **MIT**

---

## 🖋️ Auteurs
- [Groulor](https://github.com/Groulor)
- [LeNonante](https://github.com/LeNonante)
- [Orty](https://github.com/orty-orty)

