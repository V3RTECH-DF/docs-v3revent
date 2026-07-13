# Manual do usuário — V3REvent

Site Jekyll ([just-the-docs](https://just-the-docs.com/)) do **Manual do Usuário** do
V3REvent. Publicado em **https://docs.v3revent.v3rtech.com.br/** via GitHub Pages.

> Frente do manual (V3RTECH), desacoplada do plugin — o plugin apenas **linka** para este
> endereço. Segue o modelo de gestão da família (ref. V3RLGPD).

## Como é publicado

Esta pasta `manual/` **é o clone** do repositório dedicado
**[V3RTECH-DF/docs-v3revent](https://github.com/V3RTECH-DF/docs-v3revent)**. Edite aqui e
publique com `bin/publish-manual.sh` (commita + empurra + garante o CNAME). O GitHub Actions
(`.github/workflows/pages.yml`) builda o Jekyll e publica no GitHub Pages.

```bash
bin/publish-manual.sh                 # publica o pendente em manual/
bin/publish-manual.sh -m "mensagem"   # commit personalizado
```

O `CNAME` (domínio próprio `docs.v3revent.v3rtech.com.br`) e o workflow ficam versionados
aqui e viajam no push.

## Rodar localmente

```bash
bundle install
bundle exec jekyll serve   # http://127.0.0.1:4000
```

## Estrutura

- `_config.yml` — configuração do tema (just-the-docs remoto), busca, callouts, rodapé.
- `_sass/color_schemes/v3revent.scss` — cores da marca (provisório; refinar com visual-identity).
- `_includes/` — favicon e overrides de tema.
- `assets/` — logo e favicon (V3REvent).
- `index.md`, `disclaimer.md`, … — conteúdo do manual (em construção).
