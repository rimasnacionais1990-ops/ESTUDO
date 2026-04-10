# Google Sheets CSV para NotebookLM - Vercel

Este projeto cria uma página web que exibe os dados da sua planilha do Google Sheets em formato CSV, permitindo que o NotebookLM acesse o conteúdo diretamente.

## 📋 O que este projeto faz

- Busca e exibe os dados da sua planilha do Google Sheets em formato CSV
- Atualiza automaticamente a cada 30 segundos quando a planilha é modificada
- Fornece uma URL pública acessível pelo NotebookLM
- Mostra timestamp da última atualização
- Inclui botão para download direto do CSV

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
   git commit -m "Initial commit - Google Sheets CSV for NotebookLM"
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

O sistema busca automaticamente os dados mais recentes da sua planilha:
- **Atualização automática**: A cada 30 segundos, o JavaScript faz uma nova requisição ao Google Sheets
- **Cache bypass**: Cada requisição inclui um timestamp único para evitar cache
- **Display em tempo real**: Os dados são exibidos imediatamente após o carregamento
- **Indicador de atualização**: Mostra data/hora da última atualização

**Importante:** As mudanças na planilha podem levar alguns segundos para aparecer na versão publicada do Google Sheets.

## 📝 URL da sua planilha CSV

Sua planilha está configurada com este link de publicação CSV:
```
https://docs.google.com/spreadsheets/d/e/2PACX-1vTw8xiesIkLeVZzonLOKADUxOpVQp8vVrtlIW67gpTOF9EVVdIFbOEXjN2VYLYGjJDbKZcsHxOX47g0/pub?gid=282526832&single=true&output=csv
```

## 🎯 Usando com o NotebookLM

Após fazer o deploy na Vercel:
1. Copie a URL do seu site Vercel (ex: `https://seu-projeto.vercel.app`)
2. No NotebookLM, adicione esta URL como fonte
3. O NotebookLM conseguirá acessar todo o conteúdo da sua planilha em formato CSV

**Dica:** O formato CSV é ideal para o NotebookLM pois é facilmente processável e estruturado.

## 📁 Estrutura do projeto

```
├── index.html          # Página principal que busca e exibe o CSV
├── package.json        # Configuração do projeto Node.js
└── README.md           # Este arquivo
```

## ⚙️ Personalização

Se quiser alterar algo:

- **Tempo de auto-refresh**: Edite o valor `30000` (milissegundos) no `<script>` do `index.html`
- **Estilos**: Modifique o CSS na seção `<style>` do `index.html`
- **URL da planilha**: Altere a constante `CSV_URL` no JavaScript se precisar mudar de planilha ou aba
- **Parâmetros da URL**: 
  - `gid=282526832` - ID da aba específica da planilha
  - `single=true` - Retorna apenas uma aba
  - `output=csv` - Formato de saída

---

**Criado para facilitar o acesso do NotebookLM a planilhas do Google Sheets via CSV**
