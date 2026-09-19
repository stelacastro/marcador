# Marcador — gerenciador de links e favoritos

Aplicação web de página única (SPA) para salvar, organizar e buscar links, com os dados guardados no próprio navegador. Não precisa de servidor, conta ou instalação: é um único arquivo HTML.

## Como usar

1. Baixe o arquivo `index.html`.
2. Abra com duplo clique em qualquer navegador (Chrome, Firefox, Edge, Safari).
3. Pronto — os links ficam salvos automaticamente no navegador usado.

Não há passo de build nem dependências para instalar.

## Funcionalidades

**Pastas**
- Criar pastas com nome e cor.
- Renomear e excluir pastas (a exclusão avisa quantos links serão apagados junto).
- Visão "Todos os links" reúne tudo, de todas as pastas.

**Links**
- Adicionar com endereço, título opcional, descrição opcional e pasta.
- Se o título ficar em branco, o próprio endereço é usado como título.
- O endereço é validado e normalizado antes de salvar (`exemplo.com` vira `https://exemplo.com` automaticamente).
- Editar e excluir links existentes.
- Copiar o endereço para a área de transferência com um clique.
- Clicar no link abre em uma nova aba.

**Busca e organização**
- Busca em tempo real por título, descrição ou endereço.
- Filtro por pasta na barra lateral.
- Atalho `Ctrl/Cmd + K` foca a busca; `Esc` fecha janelas abertas.

**Aparência**
- Modo escuro e modo claro, com a preferência salva.
- Layout de duas colunas no desktop (pastas à esquerda, links à direita); no celular a barra de pastas vira um menu deslizante.

## Onde os dados ficam guardados

Tudo é salvo em `localStorage`, no navegador e no perfil onde a página foi aberta:

- `marcador:v1` — pastas e links.
- `marcador:theme` — preferência de tema (claro/escuro).

Isso implica em alguns limites importantes:

- Os links **não** aparecem em outro navegador, outro computador ou no modo anônimo — cada lugar tem sua própria cópia.
- Limpar o histórico e os dados de navegação do navegador apaga os links salvos.
- Abrir o mesmo arquivo `index.html` copiado para pastas diferentes do computador pode ser tratado como origens diferentes pelo navegador, resultando em listas separadas.
- Não há backup automático nem sincronização entre dispositivos.

Por segurança, vale copiar o arquivo `index.html` para um lugar fixo e sempre abri-lo do mesmo lugar.

## Tecnologia

- HTML, CSS e JavaScript puro (ES6+), sem frameworks.
- Tailwind CSS, compilado e embutido no próprio arquivo (sem dependência de CDN em tempo de uso).
- Fonte Inter, carregada do Google Fonts (único recurso externo; a aplicação funciona offline exceto por isso).

## Estrutura do arquivo

Todo o projeto vive em `index.html`:

- `<style>` — estilos compilados do Tailwind e estilos adicionais (campos de formulário, botões, itens da lista de pastas).
- `<body>` — estrutura da barra lateral, área principal, cards de link e as três janelas (link, pasta, confirmação).
- `<script>` — toda a lógica: estado da aplicação, leitura/escrita no `localStorage`, renderização das pastas e links, validação de endereço e os manipuladores de clique e teclado.

## Personalização rápida

- **Cores das pastas**: lista `PALETTE` no início do `<script>`.
- **Cores gerais do tema**: objeto `colors` dentro da configuração do Tailwind usada na compilação (veja abaixo para recompilar).
- **Textos da interface**: estão diretamente no HTML e nas strings do JavaScript, em português.

Se quiser alterar as classes do Tailwind usadas no arquivo, é necessário recompilar o CSS (o arquivo não carrega mais o Tailwind de um CDN). Isso exige Node.js e os pacotes `tailwindcss`, mas é opcional — editar cores específicas diretamente no `<style>` também funciona sem recompilar nada.