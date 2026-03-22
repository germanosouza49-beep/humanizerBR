# WARP.md

Este arquivo fornece orientações ao WARP (warp.dev) ao trabalhar com código neste repositório.

## O que é este repositório
Este repositório é uma **skill do Claude Code** implementada inteiramente em Markdown.

O artefato principal é `SKILL.md`: o Claude Code lê o frontmatter YAML (metadados + ferramentas permitidas) e as instruções que vêm em seguida.

`README.md` é para humanos: instalação, uso e uma visão geral dos padrões detectados.

## Arquivos principais (e como se relacionam)
- `SKILL.md`
  - A definição da skill propriamente dita.
  - Começa com frontmatter YAML (`---` … `---`) contendo `name`, `version`, `description` e `allowed-tools`.
  - Após o frontmatter vem o prompt do editor: a lista canônica e detalhada de padrões com exemplos.
- `README.md`
  - Instruções de instalação e uso.
  - Contém uma tabela resumida dos "25 padrões" e um breve histórico de versões.

Ao alterar comportamento/conteúdo, trate `SKILL.md` como a fonte da verdade e atualize `README.md` para manter a consistência.

## Comandos comuns
### Instalar a skill no Claude Code
Recomendado (clonar diretamente no diretório de skills do Claude Code):
```bash
mkdir -p ~/.claude/skills
git clone https://github.com/germanosouza49-beep/humanizerBR.git ~/.claude/skills/humanizerBR
```

Instalação/atualização manual (apenas o arquivo da skill):
```bash
mkdir -p ~/.claude/skills/humanizerBR
cp SKILL.md ~/.claude/skills/humanizerBR/
```

## Como "executar" (Claude Code)
Invoque a skill:
- `/humanizerBR` e depois cole o texto

## Fazendo alterações com segurança
### Versionamento (manter sincronizado)
- `SKILL.md` tem um campo `version:` no frontmatter YAML.
- `README.md` tem uma seção "Histórico de versões".

Se você alterar a versão, atualize ambos.

### Editando `SKILL.md`
- Preserve a formatação e indentação válidas do frontmatter YAML.
- Mantenha a numeração dos padrões estável, a menos que esteja renumerando intencionalmente (já que a tabela do README e os exemplos referenciam a mesma numeração).

### Documentando correções não óbvias
Se você alterar o prompt para lidar com um modo de falha complicado (ex.: uma edição incorreta repetida ou uma mudança inesperada de tom), adicione uma nota breve ao histórico de versões do `README.md` descrevendo o que foi corrigido e por quê.
