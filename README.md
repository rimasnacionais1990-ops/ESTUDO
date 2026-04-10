# Google Sheets para NotebookLM - Vercel

Este projeto cria uma página web simples que exibe sua planilha do Google Sheets publicada, permitindo que o NotebookLM acesse o conteúdo.

## 📋 O que este projeto faz

- Exibe sua planilha do Google Sheets através de um iframe
- Atualiza automaticamente o conteúdo quando a planilha é modificada
- Fornece uma URL pública acessível pelo NotebookLM

## 🚀 Como fazer deploy na Vercel

### Opção 1: Deploy Automático (Recomendado)

1. **Instale a Vercel CLI** (opcional, para deploy via terminal):
   ```bash
   npm install -g vercel
   ```

2. **Faça deploy**:
   ```bash
   vercel
   ```
   
   Ou simplesmente:
   ```bash
   vercel --prod
   ```

3. Siga as instruções no terminal e faça login na sua conta Vercel se necessário.

### Opção 2: Deploy via GitHub

1. **Crie um repositório no GitHub** e faça push deste código:
   ```bash
   git add .
   git commit -m "Initial commit - Google Sheets for NotebookLM"
   git remote add origin https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git
   git push -u origin main
   ```

2. **Acesse [vercel.com](https://vercel.com)**

3. **Conecte seu repositório GitHub**:
   - Clique em "New Project"
   - Importe o repositório que você acabou de criar
   - Clique em "Deploy"

4. Pronto! Seu site estará online em segundos.

## 🔄 Como funciona a atualização automática

O Google Sheets publicado atualiza automaticamente quando:
- Você faz alterações na planilha original
- A página é recarregada (o iframe busca a versão mais recente)
- O script JavaScript incluído recarrega o iframe a cada 60 segundos

**Importante:** As mudanças na planilha podem levar alguns segundos para aparecer na versão publicada do Google Sheets.

## 📝 URL da sua planilha

Sua planilha está configurada com este link de publicação:
```
https://docs.google.com/spreadsheets/d/e/2PACX-1vTw8xiesIkLeVZzonLOKADUxOpVQp8vVrtlIW67gpTOF9EVVdIFbOEXjN2VYLYGjJDbKZcsHxOX47g0/pubhtml
```

## 🎯 Usando com o NotebookLM

Após fazer o deploy na Vercel:
1. Copie a URL do seu site Vercel (ex: `https://seu-projeto.vercel.app`)
2. No NotebookLM, adicione esta URL como fonte
3. O NotebookLM conseguirá acessar o conteúdo da sua planilha

## 📁 Estrutura do projeto

```
├── index.html          # Página principal com o iframe da planilha
├── package.json        # Configuração do projeto Node.js
└── README.md           # Este arquivo
```

## ⚙️ Personalização

Se quiser alterar algo:

- **Tempo de auto-refresh**: Edite o valor `60000` (milissegundos) no `<script>` do `index.html`
- **Estilos**: Modifique o CSS na seção `<style>` do `index.html`
- **URL da planilha**: Altere o `src` do iframe se precisar mudar de planilha

---

**Criado para facilitar o acesso do NotebookLM a planilhas do Google Sheets**
