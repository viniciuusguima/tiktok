# Plano do Animensante

**Situação em 30/10/2026:** o planejamento foi feito no notebook com o grill (`/grill-with-docs`) e **ainda não terminou**. Faltam as perguntas da seção [Perguntas em aberto](#perguntas-em-aberto). Ainda não existem spec nem tickets, e nada foi implementado.

O vocabulário do projeto está em [GLOSSARY.md](GLOSSARY.md). As palavras com inicial maiúscula (Cena, Trecho, Narração, Vídeo, Post…) têm o sentido definido lá. As decisões difíceis de desfazer estão em [docs/adr/](docs/adr/).

---

## Como continuar no PC de casa

1. **Clonar o repositório** e abrir o Claude Code dentro da pasta dele.
2. **Instalar as skills** do Matt Pocock (precisa do Node.js). Se o instalador perguntar, escolha o Claude Code:

   ```bash
   npx skills@latest add mattpocock/skills --skill=grill-with-docs
   npx skills@latest add mattpocock/skills --skill=grilling
   npx skills@latest add mattpocock/skills --skill=domain-modeling
   npx skills@latest add mattpocock/skills --skill=setup-matt-pocock-skills
   npx skills@latest add mattpocock/skills --skill=to-spec
   npx skills@latest add mattpocock/skills --skill=to-tickets
   npx skills@latest add mattpocock/skills --skill=implement
   npx skills@latest add mattpocock/skills --skill=tdd
   ```

   O `grill-with-docs` só funciona com `grilling` e `domain-modeling`. O `to-spec` e o `to-tickets` precisam do `setup-matt-pocock-skills`. O `implement` usa o `tdd`. **Não** instale o `code-review` do repositório, porque ele substitui o `/code-review` que já vem no Claude Code.

   Sem Node.js, dá para clonar `https://github.com/mattpocock/skills` e copiar as pastas `skills/engineering/<nome>` e `skills/productivity/grilling` para `~/.claude/skills/`.
3. **Terminar o grill:** rode `/grill-with-docs` e peça para continuar pelas [Perguntas em aberto](#perguntas-em-aberto) deste arquivo. Cada pergunta já tem uma recomendação.
4. **`/setup-matt-pocock-skills`:** configura onde ficam os tickets. A recomendação está na pergunta 6.
5. **`/to-spec`:** transforma este plano numa spec.
6. **`/to-tickets`:** quebra a spec em tickets.
7. **`/implement`:** implementa os tickets.

---

## O canal

**Animensante** é um canal de TikTok que analisa Cenas de anime por um olhar filosófico. Os Vídeos têm de 1:30 a 2:00 e são narrados pela voz do dono do canal. O objetivo é monetizar.

## Decisões tomadas

### Conteúdo

- **Nicho:** só animes.
- **Animes ativos:** Frieren, Jujutsu Kaisen e Naruto clássico (sem Shippuden). Hunter x Hunter fica fora até existir Dublagem oficial no YouTube.
- **Potencial de sucesso, do maior para o menor:** Frieren, Jujutsu Kaisen, Naruto.
- **Primeiros 3 Vídeos:**
  1. **Frieren, o funeral do Himmel:** "por que eu não tentei conhecê-lo melhor?". A ideia é que a gente só percebe o valor das pessoas quando elas vão embora.
  2. **Jujutsu Kaisen, Nanami:** trabalho, vida adulta e o que dá sentido a ela.
  3. **Naruto, Haku e Zabuza:** ser uma ferramenta ou ser uma pessoa.
- **Rodízio:** fixo entre os animes nas 2 primeiras semanas. Depois, mais Vídeos do anime com melhor desempenho.
- **Estrutura de todo Vídeo:**
  1. **Gancho** (0 a 3 s).
  2. **Contexto** (cerca de 15 s).
  3. **Análise** (cerca de 60 s).
  4. **Fala marcante:** no máximo 5 s, com o som original alto.
  5. **Pergunta final.**
- **Tom:** só a voz, sem rosto. Calmo e reflexivo como um ensaio, ficando mais intenso perto da Fala marcante.
- **Como nasce o Roteiro:** o Claude propõe 3 temas, o dono escolhe, o Claude escreve e o dono ajusta antes de gravar.

### Material

- **De onde vêm os Trechos:** do YouTube, baixados com yt-dlp. O Claude mostra o link e **espera a aprovação** antes de baixar. Nada de site pirata ou torrent.
- **Fonte principal:** o canal Crunchyroll Brasil (`@CrunchyrollBR`). Na pesquisa de 30/10/2026 ele tinha cenas dubladas de Frieren, Jujutsu Kaisen e Naruto clássico.
- **Sempre Dublagem em português.** Se uma Cena não tiver Dublagem no YouTube, troca-se de Cena. Japonês nunca entra.
- **Cenas:** um Vídeo tem uma Cena principal e pode usar Cenas de apoio do mesmo anime para cobrir o Contexto.

### Regras de originalidade (fixas)

Servem para o TikTok tratar o Vídeo como conteúdo original:

- A Narração cobre pelo menos 80% do Vídeo.
- Todo Trecho é reenquadrado ou tem zoom, nunca a tela original parada.
- A Fala marcante dura no máximo 5 segundos.
- Legenda, Capa e Música-tema são sempre nossas.

### Áudio

- **Gravação da Narração:** gravador de voz do celular, lugar silencioso, tudo de uma vez. Se errar, o dono pausa e repete a frase, e o Claude corta o erro na edição.
- **Transferência:** as Narrações vão do celular para o PC de casa pelo **Google Drive**.
- **Som da Cena:** baixo durante a Narração e alto só na Fala marcante.
- **Música-tema:** em aberto, ver a pergunta 1.

### Visual

- **Formato:** vertical, 1080x1920.
- **Legenda:** gerada automaticamente da Narração (Whisper). Mostra 2 ou 3 palavras por vez, com letras grandes no centro e a palavra falada destacada em amarelo.
- **Capa:** um quadro forte da Cena com um título de 3 a 5 palavras, por exemplo "Ela chorou tarde demais".

### Publicação

- **Conta:** nova, do tipo **Pessoal** (não Comercial), com o nome **Animensante**. Em 30/10/2026 o @animensante não existia no TikTok. Quem cria a conta é o dono.
- **Ritmo:** 1 Vídeo por dia, às **20h (horário de Brasília)**. Depois de 14 dias, o horário é ajustado pelos dados da aba "Seguidores" do TikTok Studio.
- **Rotina semanal:**
  - **Sexta:** o Claude entrega os 7 Roteiros.
  - **Fim de semana:** o dono grava as 7 Narrações.
  - **Domingo à noite:** o Claude agenda os 7 Posts no TikTok Studio, pelo navegador do app do Claude.
- **Aprovação:** o dono aprova **cada** Post antes de o Claude confirmar o agendamento.

### Monetização (por fases)

1. **0 a 1 mil seguidores:** só crescer.
2. **1 mil seguidores:** TikTok Shop Afiliado e link na bio com afiliados da Shopee e da Amazon (mangás e figures do anime do Vídeo).
3. **10 mil seguidores e 100 mil visualizações em 30 dias:** Programa de Recompensas do TikTok. Exige conta Pessoal e Vídeos de 1 minuto ou mais.

### Ferramenta

- **Scripts em Python** que o Claude Code roda no PC de casa, sem um app com interface ([ADR 0001](docs/adr/0001-scripts-python-rodados-pelo-claude-code.md)).
- **O PC de casa é o estúdio:** lá ficam instalados ffmpeg, yt-dlp e Whisper, e é onde se baixa, edita e posta.
- **Repositório:** GitHub privado. Os Roteiros ficam na pasta `roteiros/`. O `CLAUDE.md` guarda as regras do projeto.

---

## O que a pesquisa encontrou (30/10/2026)

São resumos de pesquisa na web. Confira antes de depender deles.

- **Programa de Recompensas:**
  - O Brasil participa.
  - Exige 18 anos ou mais, 10 mil seguidores, 100 mil visualizações em 30 dias, conta Pessoal e vídeos de 1 minuto ou mais.
  - Paga por visualização qualificada. O TikTok não publica quanto paga por mil visualizações.
  - Fonte: newsroom.tiktok.com/introducing-the-new-creator-rewards-program
- **Originalidade:**
  - Desde setembro de 2026, as diretrizes tiram do For You o material reaproveitado de terceiros que não acrescenta nada novo.
  - Não existe regra oficial liberando análise feita com trechos de anime. A Narração própria ajuda, mas a entrada no Programa de Recompensas é incerta.
  - Fonte: tiktok.com/community-guidelines/en/integrity-authenticity
- **Direitos autorais:**
  - Conteúdo que infringe direitos é removido, e quem infringe repetidamente tem a conta banida. O número de avisos até o banimento não é público.
  - Infrações podem tirar a conta do programa de monetização.
  - Fonte: tiktok.com/legal/page/global/copyright-policy/en
- **TikTok Shop Afiliado:**
  - Chegou ao Brasil em 05/2025.
  - Exige 18 anos ou mais e 1 mil seguidores.
- **Afiliados fora do TikTok:** Shopee e Amazon não exigem número mínimo de seguidores.
- **Hunter x Hunter:** não achei cenas dubladas oficiais, e a Crunchyroll tirou o anime do catálogo em 2026.

---

## Perguntas em aberto

Continue o grill por aqui. Cada pergunta tem a recomendação do Claude.

**1. Música-tema.** O dono escolheu **"Me Desculpa Jay Z" na versão de flauta, sem voz**, que é comum nesse tipo de vídeo. Isso conflita com uma regra já aceita: como o canal vai ser monetizado, a música precisa ser liberada para uso comercial, e o TikTok pode silenciar, remover ou desqualificar da monetização vídeos com música não autorizada. Opções:
- **(a)** Colocar a música **dentro do TikTok, na hora de postar**, usando a biblioteca de sons do próprio TikTok em vez de gravá-la no arquivo do Vídeo. A licença do TikTok cobre sons da biblioteca em conta Pessoal. Nesse caso, os scripts exportam o Vídeo sem música.
- **(b)** Gravar a música direto no arquivo do Vídeo. Risco alto de o som ser cortado e de a conta levar aviso.
- **(c)** Usar uma música de flauta livre de direitos, com a mesma vibe (Pixabay Music, YouTube Audio Library).

➡️ Recomendação: **(a)**, se der. Antes de decidir, falta confirmar duas coisas:
- se essa versão de flauta existe na biblioteca de sons do TikTok;
- se o TikTok Studio no navegador deixa adicionar um som da biblioteca **ao agendar** um Post.

Se não der, **(c)**. A pesquisa sobre isso não foi concluída no notebook.

**2. Google Drive no PC de casa.** Instalar o "Google Drive para computador" no PC de casa, com uma pasta `Narrações` que sincroniza sozinha e que o script lê direto.
➡️ Sim.

**3. Modelo de Descrição.** Uma frase-gancho, a Pergunta final, o nome do anime e de 4 a 5 hashtags, por exemplo `#animensante #filosofia #anime #frieren #animebrasil`.
➡️ Sim.

**4. Legenda na Fala marcante.** A Legenda continua aparecendo durante a Fala marcante, mostrando a fala dublada.
➡️ Sim.

**5. Marca d'água.** Um `@animensante` pequeno no canto do Vídeo, para dificultar que outros repostem como se fosse deles.
➡️ Sim.

**6. Onde ficam os tickets.** Como arquivos Markdown dentro do repositório (`.scratch/`), e não como Issues do GitHub. Assim tudo fica num lugar só, e o PC de casa não precisa de nada além do git.
➡️ Sim, arquivos no repositório.

Quando essas perguntas estiverem respondidas, o grill termina: confirme que o plano está completo e siga para o `/setup-matt-pocock-skills`.
