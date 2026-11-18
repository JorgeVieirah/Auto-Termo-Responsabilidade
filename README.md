# Gerador Automático de Termos de Responsabilidade

Automação em Python que preenche **termos de responsabilidade de uso de equipamentos** (celular, notebook e periféricos) a partir de modelos `.docx`, eliminando o preenchimento manual que eu fazia no dia a dia de infraestrutura.

## Como funciona

1. O programa pergunta qual tipo de termo gerar (celular, computador ou periférico).
2. Coleta os dados do colaborador (nome e usuário do AD) e do equipamento (marca, modelo, nº de série, IMEI, hostname, estado de conservação…).
3. Substitui as variáveis do modelo (`<<nome>>`, `<<imei>>`, `<<hostname>>`…) nos parágrafos e tabelas do documento.
4. Salva o termo pronto em `Termo_Gerado/<nome do colaborador>.docx`.

Veja o fluxo resumido em [`FLUXO.md`](FLUXO.md).

## Como executar

```bash
pip install -r requirements.txt
python main.py
```

Os arquivos `termo_teste_*.docx` são **modelos de exemplo** com as variáveis entre `<< >>`. Para uso real, troque pelos modelos da sua empresa mantendo os mesmos nomes de variáveis.

> Os documentos em `Termo_Gerado/` são apenas testes com dados fictícios. Termos reais contêm dados pessoais e **não devem ser versionados**.

## Evolução

Este script foi o ponto de partida do projeto [Gestão de Dispositivos](https://github.com/JorgeVieirah/gestao-dispositivos), que transformou a ideia em um sistema completo com API, painel web, app mobile e histórico de movimentações.

## Stack

Python · python-docx
