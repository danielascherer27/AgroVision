# 🌱 AgroVision AI

> Sistema de monitoramento inteligente com detecção de objetos em tempo real utilizando **Visão Computacional + IA (YOLO)**.

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Tecnologias](#-tecnologias-utilizadas)
- [Instalação](#️-instalação-completa)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Executando](#️-executando-o-projeto)
- [Como Funciona](#-como-o-sistema-funciona)
- [Banco de Dados](#-banco-de-dados)
- [Configuração da Câmera](#-configuração-da-câmera)
- [Melhorias Futuras](#-melhorias-futuras)
- [Aplicações](#-possíveis-aplicações)
- [Autora](#-autora)
- [Contribuição](#-contribuição)

---

## 🚀 Sobre o Projeto

O **AgroVision AI** é uma aplicação desenvolvida em Python que realiza:

| Recurso | Descrição |
|---|---|
| 📡 Captura de vídeo | Em tempo real via câmera ou arquivo de vídeo |
| 🧠 Detecção com IA | Identificação automática de objetos com YOLO |
| 📸 Evidências | Geração e salvamento automático de imagens |
| 💾 Registro de eventos | Armazenamento em banco de dados SQLite |
| 🌐 Dashboard web | Interface moderna construída com FastAPI |

---

## 🎯 Funcionalidades

- ✅ Monitoramento ao vivo
- ✅ Detecção automática de objetos
- ✅ Salvamento de evidências
- ✅ Registro de eventos
- ✅ Dashboard web moderno
- ✅ Interface responsiva

---

## 🧠 Tecnologias Utilizadas

| Tecnologia | Função |
|---|---|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Linguagem principal |
| ![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white) | Framework web |
| ![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white) | Visão computacional |
| `Ultralytics YOLO` | Detecção de objetos com IA |
| `Uvicorn` | Servidor ASGI |
| `SQLite` | Banco de dados local |
| `Jinja2` | Templates HTML |

---

## ⚙️ Instalação Completa

### 1. Criar pasta do projeto
```bash
mkdir agrovision_ai
cd agrovision_ai
```

### 2. Criar ambiente virtual
```bash
python -m venv .venv
```

### 3. Ativar ambiente virtual

**Windows (PowerShell)**
```powershell
.\.venv\Scripts\Activate.ps1
```

**Linux / macOS**
```bash
source .venv/bin/activate
```

### 4. Atualizar o pip
```bash
python -m pip install --upgrade pip
```

### 5. Instalar dependências
```bash
pip install fastapi uvicorn python-multipart jinja2
pip install opencv-python pillow
pip install ultralytics
```

---

## 📁 Estrutura do Projeto

### 6. Criar pastas
```bash
mkdir app app\templates app\static app\uploads app\models app\static\captures

mkdir dataset_agro dataset_agro\images dataset_agro\images\train dataset_agro\images\val
mkdir dataset_agro\labels dataset_agro\labels\train dataset_agro\labels\val
```

### 📂 Estrutura final esperada
```
agrovision_ai/
│
├── app/
│   ├── main.py
│   ├── detections.db
│   │
│   ├── models/
│   │   └── yolov8n.pt
│   │
│   ├── static/
│   │   ├── style.css
│   │   └── captures/
│   │
│   ├── templates/
│   │   └── index.html
│   │
│   └── uploads/
│
├── dataset_agro/
│   ├── images/
│   │   ├── train/
│   │   └── val/
│   └── labels/
│       ├── train/
│       └── val/
│
├── .venv/
└── README.md
```

---

## 🧠 Modelo de IA

Baixe o modelo YOLOv8 e coloque em `app/models/`:
```
app/models/yolov8n.pt
```

> 💡 O modelo pode ser baixado automaticamente pelo Ultralytics na primeira execução.

---

## ▶️ Executando o Projeto
```bash
python -m uvicorn app.main:app --reload
```

Acesse o dashboard no navegador:
```
http://127.0.0.1:8000
```

---

## 📸 Como o Sistema Funciona
```
[Câmera / Vídeo]
      │
      ▼
[Captura de Frames]
      │
      ▼
[YOLO — Detecção de Objetos]
      │
      ▼
[Bounding Boxes desenhadas]
      │
      ├──→ 💾 Salva imagem em app/static/captures/
      │
      └──→ 🗃️ Registra evento no banco SQLite
                    │
                    ▼
            [Dashboard Web]
```

1. Captura frames da câmera ou vídeo
2. YOLO detecta objetos em tempo real
3. Bounding boxes são desenhadas sobre os objetos
4. Imagem da detecção é salva automaticamente
5. Evento é registrado no banco de dados
6. Resultado é exibido no dashboard

---

## 📊 Banco de Dados

**Arquivo:** `app/detections.db`

| Campo | Descrição |
|---|---|
| 🔑 ID | Identificador único do evento |
| 📅 Data/Hora | Timestamp da detecção |
| 🏷️ Classe | Objeto detectado pelo YOLO |
| 📊 Confiança | Score de confiança da detecção |
| 🖼️ Imagem | Caminho para a evidência salva |

---

## 🖼️ Evidências

As imagens das detecções são salvas automaticamente em:
```
app/static/captures/
```

---

## 🔧 Configuração da Câmera

No arquivo `main.py`, ajuste a variável:
```python
CAMERA_SOURCE = 0          # webcam padrão
# CAMERA_SOURCE = "video.mp4"  # arquivo de vídeo
```

| Valor | Descrição |
|---|---|
| `0` | Webcam padrão do sistema |
| `1`, `2`... | Câmeras adicionais |
| `"video.mp4"` | Arquivo de vídeo local |
| `"rtsp://..."` | Stream de câmera IP |

---

## 🚧 Melhorias Futuras

- [ ] Alertas em tempo real (e-mail / push)
- [ ] Dashboard com gráficos e métricas
- [ ] Filtros por classe detectada
- [ ] Deploy em nuvem (Docker + AWS/GCP)
- [ ] Treinamento de modelo próprio com dados agrícolas

---

## 💡 Possíveis Aplicações

| Setor | Uso |
|---|---|
| 🔒 Segurança | Monitoramento de perímetros |
| 🌾 Agro | Detecção de pragas e animais |
| 🏭 Indústria | Controle de qualidade automatizado |
| 🚪 Acesso | Identificação e controle de entrada |

---

## 👩‍💻 Autora

Desenvolvido com 💚 por **Daniela Scherer**

---

## ⭐ Contribuição

Contribuições são bem-vindas! Siga os passos:

1. 🍴 Faça um **Fork** do projeto
2. 🌿 Crie uma **branch** para sua feature (`git checkout -b feature/MinhaFeature`)
3. 💾 Faça o **commit** das suas alterações (`git commit -m 'Add MinhaFeature'`)
4. 📤 Envie um **Pull Request**

---

<p align="center">
  Feito com 💚 para o agronegócio inteligente
</p>
