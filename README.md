# Speak & Go — Landing Page

Redesign da landing page do curso **Speak & Go** (inglês para viagens), da Teacher Renata Bettarello. Site estático (HTML + CSS + JS puro, sem build step), pronto para deploy direto no Vercel.

## Stack

- HTML5 + CSS3 (custom properties, grid/flexbox) + JavaScript vanilla
- Fontes: Google Fonts (Space Grotesk, Space Mono, Inter)
- Sem framework, sem bundler, sem dependências — é só abrir e publicar

## Estrutura

```
.
├── index.html          # página inteira (markup + estilos + script)
└── assets/
    ├── logo.png                    # logo oficial Speak & Go
    ├── teacher-hero.png            # foto da Renata usada no hero (boarding pass)
    ├── teacher-about.jpg           # foto da Renata usada na seção "Conheça a Teacher"
    ├── video-apresentacao-curso.mp4    # vídeo de apresentação do curso (seção #boas-vindas)
    ├── video-apresentacao-poster.jpg   # capa do vídeo de apresentação
    ├── testimonial-iasmin.jpg      # foto real da depoente Iasmin
    └── testimonial-adriana.jpg     # foto real da depoente Adriana
```

## Rodar localmente

Não precisa de servidor especial. Duas opções:

```bash
# Opção 1: abrir direto no navegador
open index.html        # macOS
start index.html       # Windows

# Opção 2: servidor local simples (recomendado, evita problemas de path)
npx serve .
# ou
python3 -m http.server 8080
```

## Deploy — GitHub + Vercel

1. **Suba o projeto para um repositório novo no GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Landing page Speak & Go"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/speak-and-go.git
   git push -u origin main
   ```

2. **No Vercel:**
   - "Add New… → Project" → importe o repositório
   - Framework Preset: **Other** (site estático, sem build)
   - Build Command: deixe em branco
   - Output Directory: deixe em branco (raiz do projeto)
   - Deploy

Não é necessário nenhum `vercel.json` — é um site de uma página só, sem rotas.

3. **Domínio próprio (opcional):** em Project → Settings → Domains, aponte o domínio da Renata (ex.: `speakandgo.com.br`) e siga as instruções de DNS que o Vercel mostra.

## Links importantes para manter atualizados

Se algum desses links mudar no futuro, procure por eles no `index.html` (usa Ctrl+F) e troque em todas as ocorrências:

| O que | Link atual | Onde aparece |
|---|---|---|
| Checkout (compra do curso) | `https://pay.kiwify.com.br/IBIOUE1` | Botões "Garantir minha vaga" |
| WhatsApp | `https://wa.me/message/LBCAYCZMLCZON1` | Header, hero, seção da teacher, botão flutuante |
| Instagram | `https://www.instagram.com/teacherrenatabettarello/` | Rodapé |

## Vídeo de apresentação

O `<video>` da seção "Antes de embarcar" (`#boas-vindas`) usa o arquivo local `assets/video-apresentacao-curso.mp4`, com a capa `assets/video-apresentacao-poster.jpg`. Para trocar o vídeo, substitua esses dois arquivos mantendo os nomes (ou ajuste os caminhos no `index.html`). Mantenha o vídeo abaixo de ~50 MB: o GitHub avisa a partir disso e bloqueia acima de 100 MB.

## Origem do conteúdo

Todo o conteúdo (textos, preços, depoimentos, bio da professora, paleta de cores, logo) foi extraído do site real em produção (`speakandgo.com.br`) — nada foi inventado. Consulte o histórico da conversa com a Claude para o levantamento completo caso precise justificar alguma escolha de copy para a cliente.
