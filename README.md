# 🎮 EMSCORD

Clone do Discord em **um único arquivo HTML** — chat, voz, vídeo e compartilhamento de tela em tempo real. Tema vermelho/dourado ("EMS").

## ✨ Funcionalidades

- 💬 **Chat em tempo real** (servidores, canais, DMs)
- 🔊 **Chamadas de voz/vídeo** (WebRTC mesh via PeerJS)
- 🖥 **Compartilhamento de tela** com fullscreen
- 🔄 **Flip de câmera** (mobile e desktop)
- 👥 **Amizades** com pedidos, status online/idle/dnd/offline
- 🛡 **Admin de grupo** (dono pode silenciar 48h, kick, editar)
- 🎨 **Tema customizado** vermelho/dourado
- 📱 **Responsivo** (mobile + desktop)
- ⚡ **Cache offline** via IndexedDB

## 🚀 Deploy rápido

### Opção A — Vercel (recomendado)

1. Faça upload dos arquivos para um repositório no GitHub
2. Vá em https://vercel.com/new
3. Importe o repositório
4. Framework Preset: Other
5. Build Command: (deixe vazio)
6. Output Directory: (deixe vazio)
7. Deploy

Sua URL será https://SEU-PROJETO.vercel.app

### Opção B — GitHub Pages

1. Settings → Pages
2. Source: Deploy from a branch
3. Branch: main / (root)
4. Salve e aguarde 1-2 min

URL: https://SEU-USUARIO.github.io/emscord/

## 🔧 Configuração obrigatória

### 1. Firebase

1. Crie um projeto em https://console.firebase.google.com
2. Ative Firestore Database (modo produção)
3. Em Authentication → Sign-in method, ative Google
4. Copie o firebaseConfig e cole em FIREBASE_CONFIG no index.html

### 2. Google OAuth

1. https://console.cloud.google.com/apis/credentials
2. Edite seu OAuth Client ID
3. Origens JavaScript autorizadas — adicione:
   - https://SEU-PROJETO.vercel.app
   - https://SEU-USUARIO.github.io
   - http://localhost:8000
4. Copie o Client ID e cole em GOOGLE_CLIENT_ID no index.html

### 3. Autorizar domínios no Firebase

Console Firebase → Authentication → Settings → Authorized domains → adicione:

- SEU-PROJETO.vercel.app
- SEU-USUARIO.github.io

## 🛠 Desenvolvimento local

Google OAuth não funciona via file://. Use servidor local:

    python -m http.server 8000

ou

    npx serve .

Acesse http://localhost:8000

## 📁 Estrutura

- index.html — app completo (HTML + CSS + JS)
- README.md — este arquivo
- LICENSE — licença MIT
- .gitignore — arquivos ignorados pelo Git

## ⚠️ Aviso de segurança

Este projeto usa autenticação própria (SHA-256 no cliente) em vez do Firebase Auth. As regras do Firestore devem ser configuradas manualmente no console. Não use em produção com dados sensíveis sem antes migrar para Firebase Auth + regras restritas.

## 📜 Licença

MIT — veja LICENSE.

## 🙌 Créditos

- Firebase (https://firebase.google.com) — backend
- PeerJS (https://peerjs.com) — WebRTC
- Inspirado no Discord