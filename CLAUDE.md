# Controle Assistência Técnica — instruções para o Claude Code

Leia isto sempre que abrir uma sessão nova neste repositório, antes de mexer em qualquer código.

Este arquivo é só o ponto de entrada. Toda a memória do projeto (convenções, decisões, roadmap, handoff, modelo de dados) vive em
`Controle_Assis_Tec_docs`. Este repositório só leva o que o sistema precisa para rodar (o deploy espelha o repo inteiro para o servidor).

## O que é

Sistema web de controle do departamento de Assistência Técnica da Gigante (fabricante de equipamentos médicos): atendimentos
RATI/RATG/RATFG, SPG, base instalada, dashboard de KPIs, assinaturas do cliente e do técnico por link, Portal do Representante.
Dono/produto: Wall. Multi-tenant desde o início (futuro: venda). Stack: PHP 8 + MariaDB, **sem etapa de build**.

## Antes de qualquer coisa

Se `Controle_Assis_Tec_docs` não estiver clonado nesta sessão, anexe-o (`add_repo`, owner `wdsertori`, repo `Controle_Assis_Tec_docs`) e clone.
Leia, em `claude/`, nesta ordem: `HANDOFF.md`, `CONVENCOES.md`, `DECISOES-TECNICAS.md`, `ROADMAP.md`. O SQL está em `sql/schema.sql`.
O código de referência (peças a copiar) está em `wdsertori/sertto.com-SaaS` (privado) — o `HANDOFF.md` lista o que portar.

## Regras que nunca podem ser esquecidas

- **Dados reais nunca no Git** (planilhas, CNPJs, contatos). Demo só com dados fictícios.
- `empresa_id` nunca vem do navegador; tokens públicos aleatórios de 32 caracteres.
- Perguntar ao Wall antes de mudanças grandes; apresentar 1–3 caminhos com recomendação.
- Migração de schema: aviso destacado "⚠️ Antes de usar: rode `sql/...`".
- Depois de trabalho relevante, atualizar `HANDOFF.md`/`ROADMAP.md`/`DECISOES-TECNICAS.md` no repo de docs.
