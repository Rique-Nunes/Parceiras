# Site — Karoll Tavares (Instrutora & Nail Designer)

Site estático em HTML, CSS e JavaScript puros. Sem build e sem dependências: abra `index.html` no navegador.

```
karoll-tavares/
├── index.html          ← todo o texto das seções
├── css/style.css       ← cores, fontes, layout e responsivo
├── js/main.js          ← menu, formulário → WhatsApp, animações
├── assets/img/         ← 14 fotos reais do Instagram, já recortadas e otimizadas
│                         (karoll-recorte.webp/.png = foto da Karoll sem fundo, usada no topo)
└── _fonte/ig/          ← fotos originais baixadas do Instagram (não vão para o ar)
```

## Origem dos dados

Os dados foram coletados do perfil público @karolltavaress_nails em 21/10/2026, via HasData:

- Bio: "Nail Designer & Instrutora · Ensino o que vivo na mesa, na prática · +20 anos de experiência · Master Instrutora @uzenails"
- WhatsApp do link da bio: +55 21 98731-2196
- 25,6 mil seguidores
- Legendas reais usadas no site:
  - "Comecei aos 12 anos e nunca mais parei"
  - "Você não precisa ser perfeito, só precisa começar"
  - "Às vezes, o que você precisa não é de um espaço maior… é de uma visão maior"
  - Beauty Fair com a Uze
- Depoimentos: comentários reais de alunas nos posts de turma (Dd3mi5PFoLV e DcKQsP3GmDz). Estão sem o @, assinados como "Aluna, no Instagram".

## O que mudou em relação aos mockups

| Mockup (outra IA) | No site | Por quê |
|---|---|---|
| Fotos geradas por IA (modelo e unhas fictícias) | Fotos reais da Karoll, do espaço, das turmas e dos trabalhos | Prova real gera confiança |
| "Milhares de alunas formadas" | "25 mil acompanham no Instagram" | Esse número é verificável |
| Depoimentos inventados (Jéssica, Camila, Fernanda) | Comentários reais de alunas | Depoimento falso é risco legal e de reputação |
| Formulário sem destino | O formulário monta a mensagem e abre o WhatsApp | Funciona sem servidor e cai direto no canal que ela já usa |
| Paleta rosa genérica | Mármore, nude, dourado e café, tirados do espaço real | Coerente com a marca física |
| Só cursos | Cursos e também "Agendar atendimento" | A bio diz "Atendimentos & Cursos" |

## ⚠️ Confirmar com a Karoll antes de publicar

1. **Nomes dos cursos.** Os 4 cards (Alongamento, Aperfeiçoamento, Nail art e decoração, Acabamento premium) são uma proposta: o Instagram não lista a grade oficial. Edite no `index.html` (seção `#cursos`) e no `<select id="curso">`.
2. **Serviços do espaço.** "Alongamento, manutenção e nail art" está na seção Espaço.
3. **Depoimentos.** Vale pedir autorização às alunas, ou trocar por prints dos destaques "Feedback".
4. **Logo.** O monograma "K" dos destaques do Instagram não estava disponível. Hoje o site usa o nome em fonte cursiva (Pinyon Script). Quando tiver o arquivo, troque em `.brand`.
5. **Fotos extras.** Existem mais 50 fotos listadas em `_fonte/urls.tsv`. Os links expiram em alguns dias.

## Como editar

- **Textos:** todos ficam no `index.html`, separados por comentários (`<!-- ============ CURSOS ============ -->`).
- **Número do WhatsApp:** altere só `CONFIG.whatsapp` no `js/main.js`.
- **Cores:** variáveis no topo do `css/style.css` (`--rose`, `--gold`, `--espresso`…).

## Decisões de UX writing

- Os botões começam com verbo e dizem o que acontece: "Enviar pelo WhatsApp", não "Enviar".
- As mensagens de erro explicam como corrigir: "Digite o WhatsApp com DDD. Ex.: (21) 98765-4321".
- O erro aparece quando a pessoa sai do campo e some assim que ela corrige.
- "Quero esse curso" já preenche o curso no formulário.
- Um aviso de privacidade fica junto ao botão: "Nada fica salvo neste site".
- As frases têm até ~20 palavras, em segunda pessoa e voz ativa.
- A acessibilidade foi cuidada:
  - link "Pular para o conteúdo"
  - `aria-invalid` nos campos com erro
  - alvos de toque com pelo menos 44 px
  - contraste AA no botão principal
  - suporte a `prefers-reduced-motion`

## Publicar

Arraste a pasta para o Netlify Drop, a Vercel ou o GitHub Pages. Não envie a pasta `_fonte`.
