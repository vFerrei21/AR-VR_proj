# NEXUS XR — Arquitetura Futurista Cyberpunk

> Projeto de Extended Reality — Realidade Virtual 360° + Realidade Aumentada com Marcador

---

## 🎯 Conceito

**NEXUS** explora uma inquietação sobre o futuro das cidades: quando densidade urbana, automação e desigualdade se combinam, que arquitetura sobra?

O projeto apresenta dois modos de imersão:

- **VR 360°** — Três sectores de uma metrópole cyberpunk para navegar por olhar (gaze)
- **AR com Marcador** — Uma torre neon holográfica que emerge no espaço físico do utilizador

A linguagem visual é consistente: neon sobre escuridão, estruturas wireframe, paleta ciano / magenta / roxo.

---

## 📦 Estrutura do Repositório

```
nexus-xr/
├── index.html              ← Landing Page / Portal
├── vr/
│   └── index.html          ← Projeto A: VR 360° com Hotspots
├── ar/
│   └── index.html          ← Projeto B: AR com Marcador
├── assets/
│   └── markers/
│       ├── nexus-marker.png  ← Imagem do marcador AR (para imprimir)
│       └── nexus.patt        ← Padrão AR.js (.patt)
└── README.md
```

---

## 🔗 Links Diretos (GitHub Pages)

> Substitui `SEU-USER` e `SEU-REPO` pelos teus dados após publicação.

| Página |
|---|---|
| 🏠 Portal Principal |
| 🕶️ VR 360° |
| ✈️ AR |

---

## 🕶️ Projeto A — NEXUS VR 360°

### Descrição
Visor imersivo com três ambientes panorâmicos de uma metrópole distópica:

| Sector | Cor Dominante | Descrição |
|---|---|---|
| **The Core** | Ciano `#00fff7` | Núcleo de poder tecnológico — torres wireframe imponentes |
| **Megacity Grid** | Magenta `#ff00aa` | Grelha infinita de habitação em camadas |
| **Neon Wasteland** | Laranja `#ff6600` | Zonas abandonadas — infraestrutura colapsada |

### Componentes JavaScript Criados
- **`environment-switcher`** — Componente de hotspot que emite evento de mudança de ambiente ao click/gaze
- **`env-manager`** — Gere todas as transições: cor do céu, fog, visibilidade/escala dos grupos, label HUD
- **`hotspot-pulse`** — Animação de pulsação nos portais usando tick
- **`float-anim`** — Flutuação matemática de objetos (sin wave)
- **`slow-rotate`** — Rotação suave e autónoma em qualquer eixo

### Como Testar
1. Abre `vr/index.html` via GitHub Pages (HTTPS)
2. Aguarda o loading screen terminar
3. Olha para os **portais toroidal** (anel brilhante) durante ~1.5 segundos
4. O cursor muda de cor ciano → magenta durante o fuse
5. Navega pelos 3 sectores
6. Em mobile: usa giroscópio para olhar à volta; usa WASD no desktop

---

## ✈️ Projeto B — NEXUS AR

### Descrição
Uma torre neon holográfica cyberpunk materializa-se sobre o marcador NEXUS. Três drones autónomos orbitam a estrutura com cinemática calculada matematicamente.

### Marcador
- Ficheiro: `assets/markers/nexus-marker.png`
- Imprime ou exibe no ecrã de outro dispositivo
- Tamanho recomendado: mínimo 8×8 cm impresso

### Componentes JavaScript Criados
- **`orbit-drone`** — Cinemática autónoma via `tick`: órbita circular + bobbing sinusoidal + inclinação de viragem. Parâmetros: raio, velocidade, offset vertical, amplitude de bobbing
- **`tower-pulse`** — Pulsação de escala + interpolação de cor emissiva (ciano ↔ roxo) em runtime via Three.js
- **`neon-material`** — Baseado no conceito `force-red`: aplica cor, emissive, opacidade e wireframe diretamente nos materiais Three.js após carregamento
- **`ring-spin`** — Rotação autónoma em múltiplos eixos via tick

### Como Testar
1. Abre `ar/index.html` via GitHub Pages num smartphone (HTTPS obrigatório)
2. Lê o conceito e as instruções na GUI Overlay
3. Clica **"INICIAR NEXUS AR"**
4. Concede permissão de câmara
5. Aponta para o marcador `nexus-marker.png` (impresso ou no ecrã)
6. A torre NEXUS aparece — move o telemóvel à volta para ver todos os ângulos

---

## ⚙️ Publicação — GitHub Pages

### Passos
```bash
# 1. Cria repositório no GitHub (público)
# 2. Faz upload de todos os ficheiros mantendo a estrutura de pastas
# 3. Vai a Settings > Pages > Source: Deploy from branch > main / root
# 4. Aguarda ~2 minutos
# 5. Acede a https://SEU-USER.github.io/SEU-REPO/
```
---

## 🎨 Identidade Visual

| Elemento | Valor |
|---|---|
| Cor primária | `#00fff7` (ciano neon) |
| Cor secundária | `#ff00aa` (magenta) |
| Cor terciária | `#7700ff` (roxo) |
| Cor de alerta | `#ff6600` (laranja neon) |
| Fundo | `#000814` (azul noite) |
| Tipografia | Courier New (monospace) |
| Estética | Cyberpunk / Wireframe / Neon |

```

---

## 🛠️ Tecnologias

| Tecnologia | Versão | Uso |
|---|---|---|
| A-Frame | 1.5.0 | Motor WebXR (VR + AR) |
| AR.js | Latest | Deteção de marcador AR |
| Three.js | (bundled) | Manipulação de materiais |
| HTML/CSS/JS | Vanilla | Interface e lógica |
| GitHub Pages | — | Hospedagem HTTPS |

---
