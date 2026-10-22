# Site: Gih D'Oliveira (Educadora · MPE 360°)

Site estático em HTML, CSS e JavaScript puros. Não tem build nem dependências: basta abrir o `index.html` no navegador.

```
gih-doliveira/
├── index.html        ← todo o texto das seções (separadas por comentários)
├── css/style.css     ← cores, fontes, layout e responsivo
├── js/main.js        ← menu, galeria, formulário (WhatsApp ou webhook)
├── assets/img/       ← 13 fotos reais do Instagram, recortadas sem texto e otimizadas (~860 KB no total)
└── _fonte/           ← material bruto (não vai para o ar)
    ├── ig/                  24 capas originais dos posts
    └── gih-ig-bundle.json   arquivo único usado no download
```

## O que o Instagram mostrou (coleta em 22/10/2026, via HasData)

- **Perfil:** @educadora.gihdoliveira, "ESPECIALISTA EM DEPILAÇÃO / GIH D'OLIVEIRA", com 2.188 seguidores.
- **Bio:** "Treinamento para barbeiros · Faturamento estratégico com serviços extras na área da beleza".
- **Produto:** o Treinamento **MPE 360° (Método Profissional Evolution 360°)**. O slogan dela é "Sua profissão pode ser a mesma, mas sua visão nunca mais será".
- **Cursos (keepo.bio):** Depilação, Design de sobrancelhas, Limpeza de pele, e Remoção de verrugas e sinais.
- **WhatsApp (keepo.bio):** +55 21 98040-4676.
- **Provas reais:**
  - turma com certificados na @barbeariaclubrj
  - print de feedback de aluno ("só hoje fiz 3 nariz, 45 reais a mais")
  - vídeo do barbeiro Vanderson
  - entrevista com Max dos Santos na Professional Fair RJ

## Design da outra IA × site

| Mockup | Site | Por quê |
|---|---|---|
| "Make by Gabi", Gabriely Pereira, maquiadora de noivas | Gih D'Oliveira, educadora de barbeiros | O mockup descrevia outra pessoa |
| Fotos de modelos geradas por IA | Fotos reais das turmas, das aulas e da depilação | Prova real gera confiança |
| "Entre as 10 melhores maquiadoras do RJ", "+ de milhares" | Fatos verificáveis: Barbearia Club RJ, Professional Fair RJ | Número inventado é risco de reputação |
| Serviços: Noivas, Eventos… | Serviços extras: nariz, orelha, nuca, prática | É o que ela ensina |
| Seção "Belezas reais" | "Por dentro do treinamento" + 2 depoimentos reais | Mesmo papel, com conteúdo dela |
| "Aprenda comigo" | "Leve o método para a sua barbearia" + os 4 cursos | Público é dono de barbearia e barbeiro |

A identidade visual do mockup continua no site: café escuro e nude, títulos em serifa, botões arredondados, foto em arco e assinatura manuscrita.

## ⚠️ Confirmar com a Gih antes de publicar

1. **Remoção de verrugas e sinais.** No Brasil, remover sinais e verrugas pode ser considerado procedimento médico. Confirme se ela quer divulgar esse curso. Para tirar do site, apague a linha no `index.html` (seção `#treinamento`) e a `<option>` no formulário. No keepo.bio ela promete "faturamento de mais de 100%"; essa frase ficou de fora de propósito.
2. **Depoimentos.** O print do aluno aparece sem nome. O do Vanderson foi tirado da legenda do vídeo. Peça autorização aos dois antes de publicar.
3. **"7 dias".** O site diz "7 dias aplicando com clientes reais", como está nas legendas. A frase "resultado comprovado em 7 dias" ficou de fora porque é uma promessa.
4. **Fotos.** As fotos vêm de capas de Reels, então a nitidez é de vídeo. Se ela mandar 3 ou 4 fotos originais (retrato e turma), o topo do site melhora bastante.

## Formulário: WhatsApp ou lista de interessados

Em `js/main.js`, no bloco `CONFIG`:

- `whatsapp`: número que recebe a mensagem montada pelo formulário. Esse é o padrão.
- `webhook`: cole aqui a URL de um webhook (n8n, Formspree, Google Apps Script). Com isso, o formulário envia os dados para esse endereço em vez de abrir o WhatsApp. É o caminho para montar uma lista de interessados. O texto do botão muda sozinho para "Enviar meus dados".

## Decisões de UX writing

- **Título principal:** usa o slogan dela, que os alunos já reconhecem: "Sua profissão pode ser a mesma. Sua visão, nunca mais."
- **Botões:** começam com verbo e dizem o que acontece. Exemplos: "Quero levar para minha equipe" e "Enviar pelo WhatsApp".
- **Erros:** explicam como corrigir. Ex.: "Digite o WhatsApp com DDD. Ex.: (21) 98765-4321". O erro aparece quando a pessoa sai do campo e some assim que ela corrige.
- **Cursos:** tocar em um curso já marca o interesse no formulário.
- **Privacidade:** um aviso fica junto ao botão: "Nada fica salvo neste site".
- **Frases:** até cerca de 20 palavras, em segunda pessoa e voz ativa. Usamos a palavra "faturamento" porque é a que ela usa nos posts.
- **Acessibilidade:**
  - link "Pular para o conteúdo"
  - `aria-invalid` nos campos com erro
  - alvos de toque com pelo menos 44 px
  - `alt` descritivo em todas as fotos
  - suporte a `prefers-reduced-motion`

## Publicar

Arraste a pasta para o Netlify Drop, a Vercel ou o GitHub Pages. Não envie a pasta `_fonte`.
