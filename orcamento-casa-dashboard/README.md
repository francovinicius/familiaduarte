# Orçamento da Casa — Dashboard (Jul / Ago / Set 2026)

Dashboard interativo (site estático) com os ganhos, despesas e saldo do 3º trimestre de 2026.
Feito para apresentação: responsivo (celular, tablet e projetor), com drill-down por categoria.

## Conteúdo do projeto

```
orcamento-casa-dashboard/
├── index.html      # o dashboard (tudo em um arquivo, sem build)
├── vercel.json     # configuração do Vercel (opcional)
└── README.md
```

Não precisa instalar nada nem rodar build. É HTML puro + Chart.js via CDN.

## Como colocar no Vercel

Escolha **uma** das 3 formas abaixo (a nº 1 é a mais rápida).

### 1) Arrastar e soltar (mais fácil, ~1 min)
1. Acesse https://vercel.com e faça login (pode usar conta Google/GitHub).
2. Clique em **Add New… → Project**.
3. Procure a opção de **importar / deploy manual** e **arraste a pasta `orcamento-casa-dashboard`** inteira (ou use a CLI abaixo).
   - Dica: se a tela pedir um repositório, use a opção da CLI (nº 2), que aceita a pasta local direto.
4. Aguarde o deploy. O Vercel te dá uma URL do tipo `https://seu-projeto.vercel.app`.

### 2) Vercel CLI (deploy da pasta local, sem GitHub)
```bash
npm i -g vercel          # instala a CLI (uma vez)
cd orcamento-casa-dashboard
vercel                   # login + deploy de preview
vercel --prod            # publica a versão final
```
Responda "yes" às perguntas e aceite os padrões. Ao final ele mostra a URL pública.

### 3) Pelo GitHub (bom se você quiser versionar)
1. Crie um repositório no GitHub e suba estes arquivos:
   ```bash
   cd orcamento-casa-dashboard
   git init
   git add .
   git commit -m "Dashboard orçamento da casa"
   git branch -M main
   git remote add origin https://github.com/SEU_USUARIO/orcamento-casa-dashboard.git
   git push -u origin main
   ```
2. No Vercel: **Add New… → Project → Import** e selecione o repositório.
3. **Framework Preset:** deixe em **Other** (é site estático). Sem build command, sem output dir.
4. Clique em **Deploy**.

## Configurações no Vercel
- **Framework Preset:** Other / Static
- **Build Command:** (vazio)
- **Output Directory:** (vazio — a raiz já tem o index.html)

## Observações
- Os valores estão embutidos no `index.html` (dados de Julho, Agosto e Setembro de 2026), então o site funciona offline depois de carregado.
- Para atualizar os números, edite os blocos `expenseCats` e `incomeCats` dentro do `<script>` no final do `index.html` e faça o deploy de novo.
- Precisa de internet só para carregar o Chart.js (via CDN). Se quiser 100% offline para a apresentação, dá para baixar o Chart.js e referenciar localmente — me avise que eu ajusto.
