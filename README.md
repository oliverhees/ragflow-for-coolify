# RAGflow for Coolify

**Einfaches One-Click Deployment von RAGflow auf Coolify**

[![English](https://img.shields.io/badge/Language-English-blue)](README_EN.md)
[![Deutsch](https://img.shields.io/badge/Sprache-Deutsch-green)](README.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## Über dieses Projekt

Dieses Repository ermöglicht ein schnelles Deployment von [RAGflow](https://github.com/infiniflow/ragflow) auf [Coolify](https://coolify.io). RAGflow ist eine leistungsstarke Open-Source RAG-Engine (Retrieval-Augmented Generation).

**Erstellt von:** [Oliver Hees](https://ai-automation-engineers.com)
**Zur freien Verwendung für die Community**

---

## Schnellstart

### 1. Neues Projekt in Coolify erstellen

1. Öffne dein Coolify Dashboard
2. Klicke auf **+ Add Resource**
3. Wähle **Docker Compose**
4. Wähle **GitHub** als Quelle
5. Repository URL:
   ```
   https://github.com/oliverhees/ragflow-for-coolify
   ```

### 2. Umgebungsvariablen setzen

Füge in Coolify unter **Environment Variables** folgende Variablen hinzu:

```env
RAGFLOW_VERSION=latest
MYSQL_PASSWORD=dein_sicheres_passwort
REDIS_PASSWORD=dein_sicheres_passwort
MINIO_PASSWORD=dein_sicheres_passwort
```

> **Wichtig:** Verwende sichere Passwörter in Produktionsumgebungen!

### 3. Domain konfigurieren

1. Gehe zu **Settings** des ragflow Service
2. Trage deine Domain ein (z.B. `ragflow.deine-domain.de`)
3. Wähle Port **80**
4. Coolify erstellt automatisch SSL-Zertifikate

### 4. Deployen

Klicke auf **Deploy** - fertig!

---

## Immer die neueste Version

Mit `RAGFLOW_VERSION=latest` wird bei jedem Deployment automatisch die neueste RAGflow-Version verwendet.

Für eine feste Version:
```env
RAGFLOW_VERSION=v0.23.1
```

---

## Enthaltene Services

| Service | Beschreibung |
|---------|--------------|
| **RAGflow** | Haupt-Anwendung (Port 80) |
| **Elasticsearch** | Vektorsuche & Indexierung |
| **MySQL** | Relationale Datenbank |
| **MinIO** | Object Storage für Dokumente |
| **Redis** | Cache & Sessions |

---

## Systemanforderungen

| | Minimum | Empfohlen |
|--|---------|-----------|
| **RAM** | 8 GB | 16 GB |
| **CPU** | 4 Kerne | 8 Kerne |
| **Speicher** | 50 GB | 100 GB |

---

## MinIO Console (Optional)

Um die MinIO Console über eine eigene Domain erreichbar zu machen:

1. Erstelle in Coolify einen zusätzlichen Service-Eintrag für `ragflow-minio`
2. Domain: `minio.deine-domain.de`
3. Port: `9001`

---

## Fehlerbehebung

**Container starten nicht:**
- Prüfe die Logs in Coolify
- Elasticsearch benötigt ca. 2-3 Minuten zum Starten

**Nicht genug Speicher:**
- Erhöhe `ES_HEAP_SIZE` (Standard: 2g)

---

## Links

- [RAGflow Dokumentation](https://ragflow.io/docs/dev/)
- [RAGflow GitHub](https://github.com/infiniflow/ragflow)
- [Coolify Dokumentation](https://coolify.io/docs)

---

## Lizenz

MIT License - Zur freien Verwendung für die Community.

---

**Made with love for the Open Source Community**
*[Oliver Hees](https://ai-automation-engineers.com)*
