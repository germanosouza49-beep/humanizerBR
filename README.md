# HumanizerBR

Uma skill do Claude Code que remove sinais de escrita gerada por IA em textos em português, tornando-os mais naturais e humanos.

## Instalação

### Recomendado (clonar diretamente no diretório de skills do Claude Code)

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/germanosouza49-beep/humanizerBR.git ~/.claude/skills/humanizerBR
```

### Instalação/atualização manual (apenas o arquivo da skill)

Se você já clonou este repositório (ou baixou o `SKILL.md`), copie o arquivo da skill para o diretório de skills do Claude Code:

```bash
mkdir -p ~/.claude/skills/humanizerBR
cp SKILL.md ~/.claude/skills/humanizerBR/
```

## Uso

No Claude Code, invoque a skill:

```
/humanizerBR

[cole seu texto aqui]
```

Ou peça ao Claude para humanizar o texto diretamente:

```
Por favor, humanize este texto: [seu texto]
```

## Visão geral

Baseada no guia ["Signs of AI writing" da Wikipédia](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing), mantido pelo WikiProject AI Cleanup, adaptada para textos em português brasileiro. Este guia abrangente vem da observação de milhares de instâncias de texto gerado por IA.

A skill também inclui uma passagem final de auditoria "obviamente gerado por IA" e uma segunda reescrita, para capturar padrões de IA remanescentes no primeiro rascunho.

### Insight-chave da Wikipédia

> "LLMs usam algoritmos estatísticos para adivinhar o que deve vir a seguir. O resultado tende ao resultado estatisticamente mais provável que se aplica à maior variedade de casos."

## 31 Padrões detectados (com exemplos Antes/Depois)

### Padrões de conteúdo

| # | Padrão | Antes | Depois |
|---|--------|-------|--------|
| 1 | **Inflação de importância** | "marcando um momento crucial na evolução de..." | "foi criado em 1989 para coletar estatísticas regionais" |
| 2 | **Ostentação de notabilidade** | "citada no NYT, BBC, FT e The Hindu" | "Em entrevista de 2024 ao NYT, ela argumentou..." |
| 3 | **Análises superficiais com gerúndio** | "destacando... refletindo... evidenciando..." | Remover ou expandir com fontes reais |
| 4 | **Linguagem promocional** | "aninhada na deslumbrante região de..." | "é uma cidade na região de..." |
| 5 | **Atribuições vagas** | "Especialistas acreditam que desempenha papel crucial" | "de acordo com levantamento de 2019 da..." |
| 6 | **Seções formulaicas de desafios** | "Apesar dos desafios... continua a prosperar" | Fatos específicos sobre os desafios reais |

### Padrões de linguagem

| # | Padrão | Antes | Depois |
|---|--------|-------|--------|
| 7 | **Vocabulário de IA** | "Ademais... testemunho... panorama... evidenciando" | "também... continuam comuns" |
| 8 | **Evitação de "é"/"são"** | "funciona como... se destaca como... ostenta" | "é... tem" |
| 9 | **Paralelismos negativos** | "Não se trata apenas de X, mas sim de Y" | Dizer o ponto diretamente |
| 10 | **Regra de três** | "inovação, inspiração e insights" | Usar o número natural de itens |
| 11 | **Variação elegante (ciclagem de sinônimos)** | "o protagonista... o personagem principal... a figura central... o herói" | "o protagonista" (repetir quando for mais claro) |
| 12 | **Faixas falsas** | "do Big Bang à matéria escura" | Listar os tópicos diretamente |

### Padrões de estilo

| # | Padrão | Antes | Depois |
|---|--------|-------|--------|
| 13 | **Uso excessivo de travessão** | "instituições — não pelo povo — mesmo assim continua —" | Usar vírgulas ou pontos |
| 14 | **Uso excessivo de negrito** | "**OKRs**, **KPIs**, **BMC**" | "OKRs, KPIs, BMC" |
| 15 | **Listas verticais com cabeçalho inline** | "**Performance:** A performance foi aprimorada" | Converter em prosa |
| 16 | **Capitalização de títulos** | "Negociações Estratégicas E Parcerias Globais" | "Negociações estratégicas e parcerias globais" |
| 17 | **Emojis** | "🚀 Fase de lançamento: 💡 Insight principal:" | Remover emojis |
| 18 | **Aspas tipográficas** | `disse \u201co projeto está no prazo\u201d` | `disse "o projeto está no prazo"` |
| 25 | **Uso excessivo de palavras compostas** | "multifuncional, orientado a dados, voltado ao cliente" | Simplificar construções compostas |

### Padrões de comunicação

| # | Padrão | Antes | Depois |
|---|--------|-------|--------|
| 19 | **Artefatos de conversa** | "Espero que isso ajude! Me avise se..." | Remover completamente |
| 20 | **Disclaimers de corte de conhecimento** | "Embora detalhes específicos sejam limitados..." | Buscar fontes ou remover |
| 21 | **Tom bajulador** | "Ótima pergunta! Você está absolutamente certo!" | Responder diretamente |

### Enchimento e atenuação

| # | Padrão | Antes | Depois |
|---|--------|-------|--------|
| 22 | **Frases de enchimento** | "Com o objetivo de", "Devido ao fato de que" | "Para", "Porque" |
| 23 | **Atenuação excessiva** | "poderia potencialmente talvez" | "pode" |
| 24 | **Conclusões genéricas e fechamentos dramáticos** | "O futuro é promissor", "Isso muda tudo" | Planos ou fatos específicos |

### Padrões adicionais PT-BR

| # | Padrão | Antes | Depois |
|---|--------|-------|--------|
| 26 | **Aberturas formulaicas e suspense artificial** | "Imagine que...", "A solução?", "Você já se perguntou...?" | Ir direto ao ponto |
| 27 | **Conectivos e transições de IA** | "Além disso, vale ressaltar... Contudo, cabe destacar... Em suma" | Conectar ideias naturalmente ou remover |
| 28 | **Anglicismos e jargão corporativo** | "O mindset mudou, o approach trouxe um breakthrough" | "A equipe mudou a forma de trabalhar" |
| 29 | **Vocabulário aspiracional vago** | "jornada de propósito, essência, autenticidade, florescimento" | Descrever o que realmente aconteceu |
| 30 | **Névoa emocional e agência mística** | "energia inexplicável", "O universo conspirou" | Descrever a cena concretamente |
| 31 | **Problemas de estrutura e substância** | Adjetivos empilhados, voz passiva sem sujeito, paráfrase imediata, títulos genéricos | Substantivos precisos, sujeitos explícitos, especificidade |

## Exemplo completo

**Antes (com cara de IA):**
> Ótima pergunta! Aqui está um ensaio sobre este tema. Espero que ajude!
>
> A codificação assistida por IA serve como um testemunho duradouro do potencial transformador dos grandes modelos de linguagem, marcando um momento crucial na evolução do desenvolvimento de software. No cenário tecnológico em rápida evolução de hoje, essas ferramentas revolucionárias — aninhadas na interseção entre pesquisa e prática — estão remodelando a forma como os engenheiros idealizam, iteram e entregam, ressaltando seu papel vital nos fluxos de trabalho modernos.
>
> Em sua essência, a proposta de valor é clara: otimizar processos, aprimorar a colaboração e fomentar o alinhamento. Não se trata apenas de autocompletar; trata-se de liberar a criatividade em escala, garantindo que as organizações permaneçam ágeis enquanto entregam experiências fluidas, intuitivas e poderosas aos usuários. A ferramenta funciona como um catalisador. O assistente serve como um parceiro. O sistema se estabelece como uma base para a inovação.
>
> Observadores do setor notaram que a adoção acelerou de experimentos de entusiastas para implementações corporativas, de desenvolvedores solo para equipes multifuncionais. A tecnologia foi destaque no The New York Times, Wired e The Verge. Ademais, a capacidade de gerar documentação, testes e refatorações evidencia como a IA pode contribuir para melhores resultados, destacando a intrincada interação entre automação e julgamento humano.
>
> - 💡 **Velocidade:** A geração de código é significativamente mais rápida, reduzindo atrito e empoderando desenvolvedores.
> - 🚀 **Qualidade:** A qualidade do output foi aprimorada por meio de treinamento otimizado, contribuindo para padrões mais altos.
> - ✅ **Adoção:** O uso continua a crescer, refletindo tendências mais amplas do setor.
>
> Embora detalhes específicos sejam limitados com base nas informações disponíveis, poderia potencialmente ser argumentado que essas ferramentas podem ter algum efeito positivo. Apesar dos desafios típicos de tecnologias emergentes — incluindo alucinações, viés e responsabilidade — o ecossistema continua a prosperar. Com o objetivo de realizar plenamente esse potencial, as equipes devem se alinhar às melhores práticas.
>
> Em conclusão, o futuro é promissor. Tempos empolgantes nos aguardam enquanto continuamos essa jornada rumo à excelência. Me avise se quiser que eu expanda alguma seção!

**Depois (humanizado):**
> Assistentes de código com IA aceleram as partes chatas do trabalho. São bons com boilerplate: arquivos de configuração, scaffolding de testes, refatorações repetitivas. Também são bons em parecer corretos quando estão errados.
>
> Já aceitei sugestões que compilaram, passaram no lint e mesmo assim erraram o ponto porque eu parei de prestar atenção.
>
> As pessoas que conheço se dividem em dois grupos. Alguns usam como autocomplete para tarefas chatas e revisam cada linha. Outros desativam depois que a ferramenta insiste em sugerir padrões que eles não querem. Os dois lados fazem sentido.
>
> As métricas de produtividade são escorregadias. O GitHub diz que usuários do Copilot "aceitam 30% das sugestões", mas aceitar não é acertar, e acertar não é gerar valor. Se você não tem testes, está basicamente chutando.

## Referências

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) - Fonte primária
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) - Organização mantenedora

## Histórico de versões

- **3.1.0** - Adicionados 6 novos padrões PT-BR (#26-#31): aberturas formulaicas, conectivos de IA, anglicismos, vocabulário aspiracional, névoa emocional, problemas de estrutura; expandidos padrões existentes
- **3.0.0** - Tradução completa para português brasileiro (fork do [humanizer](https://github.com/blader/humanizer))
- **2.3.0** - Adicionado padrão #25: uso excessivo de palavras hifenizadas
- **2.2.0** - Adicionada auditoria final "obviamente gerado por IA" + prompts de segunda passagem
- **2.1.1** - Corrigido exemplo do padrão #18 (aspas tipográficas vs retas)
- **2.1.0** - Adicionados exemplos antes/depois para todos os 24 padrões
- **2.0.0** - Reescrita completa baseada no conteúdo bruto do artigo da Wikipédia
- **1.0.0** - Lançamento inicial

## Licença

MIT
