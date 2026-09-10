# Smart Fit Banner Loop

Automação simples de **looping de banners** para telas/TVs de academias e recepções — o navegador carrega uma lista de imagens a partir de um arquivo de configuração e as exibe em tela cheia, em rotação contínua com transição suave.

Feito para rodar em um computador, mini-PC ou Raspberry Pi conectado a uma TV, sem precisar de nenhum software além do navegador.

## ✨ Funcionalidades

- Rotação automática de banners com tempo individual configurável por imagem
- Transição com fade suave entre banners
- Modo tela cheia (tecla `F`) e cursor oculto — ideal para monitores públicos
- Configuração 100% via `config.json`, sem precisar mexer no código
- Suporta qualquer imagem (JPG, PNG, SVG) — os banners de exemplo em `banners/` são placeholders genéricos, é só substituir pelas artes reais

## 🛠️ Tecnologias

- HTML5 / CSS3 (transições)
- JavaScript puro (Vanilla JS), sem dependências

## ⚙️ Configuração (`config.json`)

```json
{
  "durationSeconds": 8,
  "transitionMs": 800,
  "banners": [
    { "src": "banners/banner-01.svg", "durationSeconds": 8 },
    { "src": "banners/banner-02.svg", "durationSeconds": 8 }
  ]
}
```

- `durationSeconds`: tempo padrão de exibição (usado quando o banner não define o próprio tempo)
- `transitionMs`: duração da transição de fade
- `banners`: lista ordenada de imagens exibidas em loop

## ▶️ Como rodar

```bash
git clone https://github.com/marquxst/smartfit-banner-loop.git
cd smartfit-banner-loop
# abra o index.html no navegador em tela cheia (F11 ou tecla F)
```

Para deixar rodando 24/7 numa TV da academia:

1. Configure o computador/mini-PC para abrir o Chrome direto no `index.html` ao ligar (modo kiosk: `chrome --kiosk index.html`)
2. Desative a suspensão de tela do sistema operacional
3. Atualize os arquivos em `banners/` sempre que trocar as promoções — não precisa reiniciar nada além de recarregar a página

## 📌 Próximos passos (ideias)

- Agendamento por dia/hora (ex: banner de aula só aparece no horário da aula)
- Painel de administração simples para trocar banners sem editar JSON manualmente
- Suporte a vídeos além de imagens
