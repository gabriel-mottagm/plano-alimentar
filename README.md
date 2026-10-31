# Plano e diário alimentar

Página pessoal para montar o plano alimentar por ciclos, ver os macros por refeição e por dia, comparar dietas, registrar o diário e acompanhar a evolução.

**Endereço:** https://gabriel-mottagm.github.io/plano-alimentar/

## Onde ficam os dados

- O login é feito com uma conta Microsoft pessoal.
- Os dados ficam no OneDrive de quem entra, numa pasta só deste app: `Aplicativos › Plano alimentar › dados`. A página pede apenas a permissão `Files.ReadWrite.AppFolder`, que dá acesso a essa pasta e a nada mais do OneDrive.
- Este repositório tem **só o código**. Nenhum dado pessoal fica aqui.

## Como funciona

- Uma página HTML única (`index.html`), sem bibliotecas externas: o login usa o fluxo OAuth 2.0 com PKCE direto nos endpoints da Microsoft, e os arquivos são lidos e gravados pelo Microsoft Graph.
- Cada documento é um arquivo JSON: `dados/app/foods.json` (alimentos), `dados/cycles/<id>.json` (ciclos) e `dados/days/<AAAA-MM-DD>.json` (dias registrados).
- A versão para PC (programa em Python distribuído à parte) usa o mesmo formato e encontra a mesma pasta do OneDrive sozinha.

## Configuração do login (já feita)

- Registro de app na Microsoft: ID `b00a9395-4ab6-44d7-b0c5-c93562d2ae1e`, somente contas pessoais da Microsoft.
- Plataforma: aplicativo de página única (SPA), URI de redirecionamento `https://gabriel-mottagm.github.io/plano-alimentar/`.
- GitHub Pages publica o branch `gh-pages`, pasta raiz.

## Créditos

- Composição dos alimentos: Tabela Brasileira de Composição de Alimentos (TACO), 4ª edição, NEPA/Unicamp, 2011 (reprodução permitida citando a fonte).
- Fontes: Archivo e Libre Franklin, licença SIL Open Font License (arquivos em `fontes/`).
