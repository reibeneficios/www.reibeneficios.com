# Cartão REI — Pronto para GitHub Pages

Esta pasta já está pronta para publicar. Não precisa editar nada, só seguir os passos.

## 1. Criar o repositório

1. Acesse https://github.com e crie uma conta (se ainda não tiver).
2. Clique em **New repository** (botão verde no canto superior direito, ou https://github.com/new).
3. Nome do repositório: `cartao-rei` (pode ser outro nome, mas anote — ele vai aparecer na URL final).
4. Marque como **Public**.
5. NÃO marque "Add a README file" (já temos um).
6. Clique em **Create repository**.

## 2. Subir os arquivos

### Opção A — Pelo navegador (mais simples, sem instalar nada)
1. Na página do repositório recém-criado, clique em **uploading an existing file**.
2. Arraste TODOS os arquivos e pastas desta pasta (`index.html`, `manifest.json`, `sw.js`, `.nojekyll`, e a pasta `icons/` com todo o conteúdo dela) para a área de upload.
   - Atenção: arraste a pasta `icons` inteira, não os arquivos um por um — o GitHub mantém a estrutura de pastas.
3. Role para baixo, escreva uma mensagem como "primeira versão do site" e clique em **Commit changes**.

### Opção B — Por linha de comando (se já usa Git)
```bash
cd caminho/para/esta/pasta
git init
git add .
git commit -m "primeira versão do site"
git branch -M main
git remote add origin https://github.com/SEU-USUARIO/cartao-rei.git
git push -u origin main
```

## 3. Ativar o GitHub Pages

1. No repositório, vá em **Settings** (aba no topo).
2. No menu lateral esquerdo, clique em **Pages**.
3. Em **Source**, selecione **Deploy from a branch**.
4. Em **Branch**, selecione `main` e a pasta `/ (root)`. Clique em **Save**.
5. Aguarde 1–2 minutos. A página vai mostrar o link final, algo como:

```
https://SEU-USUARIO.github.io/cartao-rei/
```

Esse já é o site no ar, gratuito, com HTTPS automático. Pode compartilhar esse link com qualquer pessoa.

## 4. Testar a instalação como app (PWA)

No celular Android, abra esse link no Chrome. Vai aparecer (ou o Chrome vai oferecer) a opção de **instalar o app** — ele vira um ícone na tela inicial e abre em tela cheia, como um aplicativo nativo.

## 5. (Opcional) Usar um domínio próprio depois

Se mais adiante quiser algo como `www.cartaorei.com.br` em vez do link do GitHub:

1. Registre o domínio em um registrador (ex: Registro.br para `.com.br`, ou GoDaddy/Namecheap para `.com`).
2. Volte em **Settings > Pages** neste repositório e, no campo **Custom domain**, digite o domínio (ex: `www.cartaorei.com.br`) e salve — isso cria automaticamente um arquivo `CNAME` no repositório.
3. No painel do seu registrador de domínio, configure o DNS:
   - Se for um subdomínio (`www`): crie um registro **CNAME** apontando para `SEU-USUARIO.github.io`.
   - Se for o domínio raiz (sem `www`): crie 4 registros **A** apontando para:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
4. Aguarde a propagação do DNS (de minutos a algumas horas) e marque **Enforce HTTPS** em Settings > Pages.

## Estrutura desta pasta

```
index.html        → o site completo (Cartão REI)
manifest.json      → configuração do PWA (nome, ícones, cor)
sw.js              → service worker (cache offline básico)
.nojekyll          → impede o GitHub de processar os arquivos como Jekyll
icons/             → ícones do app em vários tamanhos
```
