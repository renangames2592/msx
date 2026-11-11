# Meu Aplicativo — Media Station X

Exemplo completo de aplicativo para o **Media Station X** (grátis, sem registro).

## Estrutura

```
msx-app/
├── start.json          ← objeto inicial (registra seu app no MSX)
└── data/
    ├── menu.json       ← menu lateral (Início, Vídeos, Galeria, Sobre)
    ├── home.json       ← página inicial com hero + botões
    ├── videos.json     ← lista de vídeos (YouTube, Vimeo, MP4, SoundCloud)
    ├── gallery.json    ← galeria de imagens + botão de slideshow
    ├── slideshow.json  ← dados do slideshow
    └── about.json      ← página "Sobre" com links e ações
```

## Testar agora (local)

O servidor já está rodando. Abra no navegador:

```
https://msx.benzac.de/?start=menu:http://localhost:8765/data/menu.json
```

Para reiniciar o servidor depois:

```powershell
cd C:\Users\Renan\msx-app
python -m http.server 8765 --bind 127.0.0.1
```

> Nota: a porta 8080 está bloqueada neste PC (intervalo de portas reservadas do Windows), por isso usamos 8765.

## Publicar de verdade (GitHub Pages, grátis)

1. Crie um repositório chamado `msx` no seu GitHub.
2. Suba esta pasta inteira para ele.
3. Nas configurações do repositório, ative **Pages** → deploy a partir da branch `main`.
4. Troque **todas** as ocorrências de `http://localhost:8765` pelos JSONs pelo seu endereço:
   - `https://SEUUSUARIO.github.io/msx`
   - Arquivos afetados: `start.json`, `data/menu.json`, `data/home.json`, `data/gallery.json`, `data/about.json`
5. No dispositivo: **Settings → Start Parameter → Setup** → defina o security lock e digite `SEUUSUARIO.github.io`.

Referência oficial: https://github.com/benzac-de/msx

## Editar conteúdo

- **Adicionar item no menu**: edite `data/menu.json` e adicione um objeto com `icon`, `label` e `data` (URL de um JSON de conteúdo).
- **Adicionar vídeo**: edite `data/videos.json` e copie um dos itens. Para YouTube, troque o `id=` na URL do plugin.
- **Adicionar imagem**: edite `data/gallery.json`.
- Depois de salvar, o app busca os JSONs novos na próxima abertura (ou use o botão "Recarregar aplicativo" na página Sobre).

## Documentação oficial

- Wiki: https://msx.benzac.de/wiki/
- Exemplo GitHub Pages: https://github.com/benzac-de/msx
- Ícones: https://msx.benzac.de/info/icons.html
