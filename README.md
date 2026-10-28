# Páginas de venda: Guia "Seu cliente te encontra no Google?"

Site estático (HTML + CSS + JS puro), pronto para GitHub + Vercel.

| Página | Arquivo | URL na Vercel |
|---|---|---|
| Landing page | `index.html` | `/` |
| Obrigado + upsell (Raio-X) | `obrigado.html` | `/obrigado` |
| Back redirect | `raio-x.html` | `/raio-x` |

## O que editar
Tudo fica em **`config.js`**:
- `checkout`: link do checkout da Cakto.
- `raioxObrigado` / `raioxBack`: links do Raio-X (um por página, para rastrear a origem do lead).
- `preco` / `precoParcelado`.
- `cases`: cases reais com números. Com a lista vazia, a seção de prova social fica escondida.

## Fluxo
1. Anúncio → `/` (landing). Os parâmetros UTM são repassados para o checkout.
2. Se a pessoa aperta "voltar" → `/raio-x` (captura o lead para o WhatsApp).
3. Compra aprovada → Cakto redireciona para `/obrigado` (configurar na Cakto, em "Página de obrigado").

## Publicar
```bash
git init && git add . && git commit -m "Páginas de venda"
gh repo create phar-paginas-venda --private --source=. --push
```
Na Vercel: **Add New → Project → importar o repositório → Deploy** (sem build, framework "Other").
