# 🥛 TechnoLeite — Especialista IA em Laticínios

Site com IA especialista em laticínios. Qualidade, produção, custos, impostos, laboratório e legislação. Usa sua chave Anthropic de forma segura no servidor — os usuários só acessam o site e perguntam, sem precisar de chave ou cadastro.

---

## 🚀 DEPLOY — PASSO A PASSO COMPLETO

Tempo estimado: **15 minutos**. Não precisa saber programar.

---

### ETAPA 1 — Criar conta no GitHub (se não tiver)

1. Acesse **github.com** e clique em "Sign up"
2. Crie uma conta gratuita (pode usar seu e-mail normal)
3. Confirme o e-mail

---

### ETAPA 2 — Criar o repositório no GitHub

1. No GitHub, clique em **"New repository"** (botão verde)
2. Nome: `technoleite`
3. Visibilidade: **Public** (necessário para Vercel grátis)
4. Clique em **"Create repository"**

---

### ETAPA 3 — Enviar os arquivos para o GitHub

**Opção A — Pelo site do GitHub (mais fácil):**

1. Na página do repositório criado, clique em **"uploading an existing file"**
2. Faça upload de TODOS os arquivos mantendo a estrutura de pastas:
   ```
   technoleite/
   ├── vercel.json
   ├── package.json
   ├── api/
   │   ├── chat.js
   │   └── health.js
   └── public/
       └── index.html
   ```
3. Clique em **"Commit changes"**

**Opção B — Pelo terminal (se souber usar):**
```bash
git clone https://github.com/SEU_USUARIO/technoleite
# copie os arquivos para a pasta
git add .
git commit -m "TechnoLeite inicial"
git push
```

---

### ETAPA 4 — Criar conta na Vercel

1. Acesse **vercel.com**
2. Clique em **"Sign Up"**
3. Escolha **"Continue with GitHub"** — conecta automaticamente
4. Autorize o acesso

---

### ETAPA 5 — Fazer o deploy na Vercel

1. No painel da Vercel, clique em **"Add New Project"**
2. Selecione o repositório **technoleite**
3. Clique em **"Import"**
4. Na tela de configuração:
   - Framework Preset: **Other**
   - Root Directory: deixe vazio (raiz)
5. Clique em **"Deploy"**
6. Aguarde 1-2 minutos

✅ Seu site vai ficar disponível em: `https://technoleite.vercel.app` (ou similar)

---

### ETAPA 6 — Configurar a chave API da Anthropic ⚠️ PASSO MAIS IMPORTANTE

Sem isso o site não vai funcionar.

1. Acesse **console.anthropic.com**
2. Vá em **"API Keys"** → **"Create Key"**
3. Copie a chave (começa com `sk-ant-...`)
4. No painel da Vercel, vá em:
   - **Settings** → **Environment Variables**
5. Adicione:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** cole sua chave `sk-ant-...`
   - Clique em **Save**
6. Vá em **Deployments** → clique nos três pontinhos do último deploy → **Redeploy**

✅ Pronto! O site agora funciona com sua chave protegida no servidor.

---

### ETAPA 7 — Testar

1. Acesse a URL do seu site (ex: `https://technoleite.vercel.app`)
2. Clique em qualquer área de especialidade ou faça uma pergunta
3. Deve responder em alguns segundos

---

## 💰 CUSTOS

| Item | Custo |
|------|-------|
| GitHub | Grátis |
| Vercel (hospedagem) | Grátis |
| Anthropic (IA) | ~$0,003-0,006 por pergunta |

Com **$4,90** você tem aproximadamente **800 a 1.500 perguntas** antes de precisar recarregar.

Para monitorar o uso: **console.anthropic.com → Usage**

---

## 🔗 DOMÍNIO PERSONALIZADO (opcional)

Se quiser um endereço como `www.technoleite.com.br`:
1. Compre o domínio (RegistroBR, Hostgator, GoDaddy — ~R$40/ano)
2. Na Vercel: **Settings → Domains → Add Domain**
3. Siga as instruções para apontar o DNS

---

## 🛠️ PERSONALIZAÇÃO

Para mudar textos, cores ou especialidades:
- Edite o arquivo `public/index.html`
- O sistema prompt do especialista está em `api/chat.js`
- Após editar, faça commit no GitHub e a Vercel faz o deploy automático

---

## 📊 FUTURO — MONETIZAÇÃO

Algumas ideias para monetizar:
- **Assinatura mensal**: plano free (X perguntas/mês) + plano pago (ilimitado)
- **Licença B2B**: vender acesso para laticínios e cooperativas
- **Versão white-label**: customizar para outras empresas do setor
- **Integração com WhatsApp Business**: via Twilio ou Z-API

Para implementar qualquer uma dessas, a base já está pronta — só precisa adicionar autenticação e pagamentos (Stripe, Mercado Pago).

---

## ❓ PROBLEMAS COMUNS

**Site abre mas dá erro ao perguntar:**
→ Verifique se a variável `ANTHROPIC_API_KEY` foi adicionada e se fez Redeploy

**"Service temporarily unavailable":**
→ Verifique saldo na Anthropic (console.anthropic.com → Usage)

**Demora muito para responder:**
→ Normal nas primeiras perguntas (cold start ~2s). Perguntas seguintes são mais rápidas.

---

Dúvidas? Qualquer problema, abra uma issue no GitHub ou contate o desenvolvedor.
