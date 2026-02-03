# RAGflow for Coolify

**Simple One-Click Deployment of RAGflow on Coolify**

[![English](https://img.shields.io/badge/Language-English-blue)](README.md)
[![Deutsch](https://img.shields.io/badge/Sprache-Deutsch-green)](README_DE.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## About this Project

This repository enables quick deployment of [RAGflow](https://github.com/infiniflow/ragflow) on [Coolify](https://coolify.io). RAGflow is a powerful open-source RAG engine (Retrieval-Augmented Generation).

**Created by:** [Oliver Hees](https://ai-automation-engineers.com)
**Free to use for the community**

---

## Quick Start

### 1. Create New Project in Coolify

1. Open your Coolify Dashboard
2. Click **+ Add Resource**
3. Select **Docker Compose**
4. Choose **GitHub** as source
5. Repository URL:
   ```
   https://github.com/oliverhees/ragflow-for-coolify
   ```

### 2. Set Environment Variables

Add the following variables in Coolify under **Environment Variables**:

```env
RAGFLOW_VERSION=latest
MYSQL_PASSWORD=your_secure_password
REDIS_PASSWORD=your_secure_password
MINIO_PASSWORD=your_secure_password
```

> **Important:** Use secure passwords in production environments!

### 3. Configure Domain

1. Go to **Settings** of the ragflow service
2. Enter your domain (e.g., `ragflow.your-domain.com`)
3. Select Port **80**
4. Coolify automatically creates SSL certificates

### 4. Deploy

Click **Deploy** - done!

---

## Always the Latest Version

With `RAGFLOW_VERSION=latest`, the newest RAGflow version is automatically used with each deployment.

For a fixed version:
```env
RAGFLOW_VERSION=v0.23.1
```

---

## Included Services

| Service | Description |
|---------|-------------|
| **RAGflow** | Main application (Port 80) |
| **Elasticsearch** | Vector search & indexing |
| **MySQL** | Relational database |
| **MinIO** | Object storage for documents |
| **Redis** | Cache & sessions |

---

## System Requirements

| | Minimum | Recommended |
|--|---------|-------------|
| **RAM** | 8 GB | 16 GB |
| **CPU** | 4 cores | 8 cores |
| **Storage** | 50 GB | 100 GB |

---

## MinIO Console (Optional)

To access the MinIO Console via its own domain:

1. Create an additional service entry in Coolify for `ragflow-minio`
2. Domain: `minio.your-domain.com`
3. Port: `9001`

---

## Troubleshooting

**Containers won't start:**
- Check the logs in Coolify
- Elasticsearch needs about 2-3 minutes to start

**Not enough memory:**
- Increase `ES_HEAP_SIZE` (default: 2g)

---

## Links

- [RAGflow Documentation](https://ragflow.io/docs/dev/)
- [RAGflow GitHub](https://github.com/infiniflow/ragflow)
- [Coolify Documentation](https://coolify.io/docs)

---

## License

MIT License - Free to use for the community.

---

**Made with love for the Open Source Community**
*[Oliver Hees](https://ai-automation-engineers.com)*
