# 🌱 AgroVision AI

Sistema de monitoramento inteligente com detecção de objetos em tempo real utilizando **Visão Computacional + IA (YOLO)**.

---

## 🚀 Sobre o projeto

O **AgroVision AI** é uma aplicação desenvolvida em Python que realiza:

- 📡 Captura de vídeo em tempo real (câmera ou vídeo)
- 🧠 Detecção automática de objetos com YOLO (Ultralytics)
- 📸 Geração de evidências (imagens salvas)
- 💾 Registro de eventos em banco SQLite
- 🌐 Dashboard web moderno com FastAPI

---

## 🎯 Funcionalidades

✔ Monitoramento ao vivo  
✔ Detecção automática de objetos  
✔ Salvamento de evidências  
✔ Registro de eventos  
✔ Dashboard web moderno  
✔ Interface responsiva  

---

## 🧠 Tecnologias utilizadas

- FastAPI  
- Uvicorn  
- OpenCV  
- Ultralytics YOLO  
- SQLite  
- Jinja2  
- HTML + CSS  

---

# ⚙️ INSTALAÇÃO COMPLETA (PASSO A PASSO)

## 1. Criar pasta do projeto

```bash
mkdir agrovision_ai
cd agrovision_ai

chat transforme esse texto em markdown:

2. Criar ambiente virtual

```
python -m venv .venv
```

3. Ativar ambiente virtual
Windows (PowerShell)

```
.\.venv\Scripts\Activate.ps1
```

4. Atualizar o pip

```
python -m pip install --upgrade pip
```

5. Instalar dependências

```
pip install fastapi uvicorn python-multipart jinja2
pip install opencv-python pillow
pip install ultralytics
```

📁 CRIAÇÃO DA ESTRUTURA DO PROJETO
6. Criar pastas

```
mkdir app
mkdir app\templates
mkdir app\static
mkdir app\uploads
mkdir app\models
mkdir app\static\captures

mkdir dataset_agro
mkdir dataset_agro\images
mkdir dataset_agro\images\train
mkdir dataset_agro\images\val
mkdir dataset_agro\labels
mkdir dataset_agro\labels\train
mkdir dataset_agro\labels\val
```

📂 Estrutura final esperada

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
│   └── labels/
│
├── .venv/
└── README.md
```

🧠 MODELO DE IA
Baixe o modelo YOLO:

```
yolov8n.pt
```

Coloque o arquivo em:

```
app/models/
```

▶️ EXECUTANDO O PROJETO

```
python -m uvicorn app.main:app --reload
```

Abra no navegador:

```
http://127.0.0.1:8000
```

📸 COMO O SISTEMA FUNCIONA
1.  Captura frames da câmera 
2.  YOLO detecta objetos 
3.  Desenha bounding boxes 
4.  Salva imagem da detecção 
5.  Registra evento no banco 
6.  Exibe no dashboard 
📊 BANCO DE DADOS
Arquivo:

```
app/detections.db
```

Contém:
*  ID do evento 
*  Data/Hora 
*  Classe detectada 
*  Confiança 
*  Caminho da imagem 
🖼️ EVIDÊNCIAS
Salvas automaticamente em:

```
app/static/captures/
```

🔧 CONFIGURAÇÃO DA CÂMERA
No arquivo `main.py`:

```
CAMERA_SOURCE = 0
```

* `0` → webcam 
* `"video.mp4"` → arquivo de vídeo 
🚧 MELHORIAS FUTURAS
*  Alertas em tempo real 
*  Dashboard com gráficos 
*  Filtros por classe 
*  Deploy em nuvem 
*  Treinamento de modelo próprio 
💡 POSSÍVEIS APLICAÇÕES
*  Segurança 
*  Monitoramento agrícola 
*  Automação industrial 
*  Controle de acesso 
👨‍💻 AUTOR
Desenvolvido por Daniela Scherer
⭐ CONTRIBUIÇÃO
1.  Fork o projeto 
2.  Crie uma branch 
3.  Commit 
4.  Pull Request
