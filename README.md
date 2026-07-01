# GraceForge — Vitrine

Vitrine estática pra colocar o link no Instagram: pessoa clica, abre a
página, vê os produtos, clica num card e vai direto pra listagem na Shopee.

Rastreabilidade do tráfego Insta → Shopee via cupom **INSTA10** (banner
laranja no topo da vitrine).

## Como funciona

- 100% estático: `index.html` + `produtos.json` + `img/`.
- Hospedado no GitHub Pages (branch `main`, pasta raiz).
- Sem backend, sem build. Editou o JSON, push, tá no ar.

## Editar produtos

Abre `produtos.json` e edita. Schema de cada item:

```json
{
  "id": "slug-curto",
  "nome": "Nome exibido no card",
  "preco": 31.41,
  "imagem": "img/arquivo.png",
  "shopee_url": "https://shopee.com.br/…"
}
```

- `preco` é number (sem R$, ponto como decimal — a página formata).
- `imagem` pode ser caminho relativo no repo (`img/xxx.png`) ou URL externa.
- `shopee_url` abre em nova aba com `noopener`.

## Rodar local

```bash
python3 -m http.server 5502
# abre http://localhost:5502
```

Precisa servir por HTTP (o `fetch` do `produtos.json` não funciona via `file://`).

## A fazer

- [ ] **Layout mobile-first refinado** — hoje é responsivo mas foi pensado
      desktop-em-baixo. Dedicar o design pro celular (é de lá que vem o
      tráfego do Insta): tipografia, tamanho de toque, densidade, hero.
- [ ] **Cadastrar mais produtos** — só o Suporte Notebook está lá.
      Ir adicionando conforme os listings da Shopee.
