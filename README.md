# TP 10 : Client REST Android Retrofit

> **Cours** : Architecture Microservices : Conception, Déploiement et Orchestration

Application Android permettant de consommer un service REST pour gérer des comptes bancaires avec des fonctionnalités CRUD (Create, Read, Update, Delete).

## 🎬 Démo

[![Demo Video](https://img.shields.io/badge/▶️-Voir_la_démo-red?style=for-the-badge)](https://www.youtube.com/watch?v=VOTRE_VIDEO_ID)

## 📋 Fonctionnalités

- **Affichage des comptes** (JSON et XML)
- **Ajout de compte**
- **Modification de compte**
- **Suppression de compte**
- **Switch JSON ↔ XML** en temps réel

## 🛠️ Technologies

| Composant | Version |
|-----------|---------|
| Android SDK | 34 |
| MinSDK | 24 (Android 7.0) |
| Retrofit | 2.9.0 |
| Gson | JSON parsing |
| SimpleXML | XML parsing |
| Material Design | 1.11.0 |

## 📁 Structure

```
app/src/main/java/ma/projet/restclient/
├── MainActivity.java          # Activité principale
├── model/
│   └── Compte.java           # Entité compte bancaire
├── service/
│   └── CompteService.java    # Interface Retrofit
├── config/
│   └── RetrofitClient.java   # Configuration Retrofit
├── repository/
│   └── CompteRepository.java # Couche d'accès données
└── adapter/
    └── CompteAdapter.java    # Adapter RecyclerView
```

## 📦 Build

```bash
# Compiler l'APK debug
./gradlew assembleDebug

# L'APK est généré dans:
# app/build/outputs/apk/debug/app-debug.apk
```

## 🚀 Installation

1. **Prérequis** : JDK 17 configuré dans `gradle.properties`
2. Ouvrir le projet dans Android Studio
3. Synchroniser Gradle
4. Lancer sur émulateur ou appareil physique

## ⚙️ Configuration

Le backend doit être accessible sur `http://10.0.2.2:8082/` depuis l'émulateur Android.

Modifier l'URL dans `RetrofitClient.java` si nécessaire.

### Configuration Retrofit JSON
```java
Retrofit retrofit = new Retrofit.Builder()
    .baseUrl(BASE_URL)
    .addConverterFactory(GsonConverterFactory.create())
    .build();
```

### Configuration Retrofit XML
```java
Retrofit retrofit = new Retrofit.Builder()
    .baseUrl(BASE_URL)
    .addConverterFactory(SimpleXmlConverterFactory.create())
    .build();
```

## 📡 API Endpoints

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| GET | `/api/comptes` | Liste tous les comptes |
| GET | `/api/comptes/{id}` | Obtenir un compte |
| POST | `/api/comptes` | Créer un compte |
| PUT | `/api/comptes/{id}` | Modifier un compte |
| DELETE | `/api/comptes/{id}` | Supprimer un compte |

## ✅ Build Status

- ✔️ APK Debug compilé avec succès
- ✔️ Compatible Android 7.0+ (API 24)
- ✔️ Taille APK: ~6 MB

## 👤 Auteur

**CHAKRAhossam**
