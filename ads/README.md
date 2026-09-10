# Feed de anúncios do CNPJ Brazil DB Explorer

O aplicativo consulta `https://cnpjbrazil.github.io/ads/ads.json`. O arquivo raiz é um array de anúncios com esta estrutura:

```json
{
  "enabled": true,
  "title": "Título do anúncio",
  "company": "Nome da empresa",
  "description": "Descrição curta em texto simples.",
  "site": "https://empresa.example/",
  "images": [
    {
      "src": "images/empresa/banner-01.svg",
      "description": "Descrição acessível da imagem"
    }
  ],
  "instagram": "https://www.instagram.com/empresa/",
  "whatsapp": "+55 11 99999-9999",
  "start_date": "2026-09-01",
  "end_date": "2026-09-30"
}
```

Regras:

- `start_date` e `end_date` usam `AAAA-MM-DD`; as duas datas são inclusivas.
- Para ocultar uma campanha imediatamente, altere `enabled` para `false`.
- Use caminhos de imagem relativos à pasta `ads/`; as imagens precisam estar neste mesmo site.
- `site`, `instagram` e `whatsapp` podem ser strings vazias quando não se aplicarem.
- Sites e Instagram precisam usar HTTPS. O aplicativo converte o número do WhatsApp em um link `wa.me`.
- O aplicativo aceita no máximo 25 anúncios válidos e oito imagens por anúncio.

Antes de publicar marcas, textos ou imagens de terceiros, confirme que seu uso foi autorizado.
