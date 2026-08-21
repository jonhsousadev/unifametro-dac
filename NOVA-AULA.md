# Como Adicionar uma Nova Aula

## 1. Criar pasta da aula

Crie uma pasta com o nome `aula{Número}` (ex: `aula2`, `aula3`) copiando a estrutura de uma aula existente.

## 2. Adicionar no data.json

Adicione um novo objeto no array `aulas`:

```json
{
  "id": "02",
  "pasta": "aula2",
  "nome": "Nome da Aula",
  "descricao": "Breve descrição do conteúdo"
}
```

## 3. Adicionar CSS de impressão

No `<head>` do `index.html` da nova aula, adicione **antes** do `<script defer src="dist/fontawesome/all.min.js">`:

```html
<style>
  @media print {
    html.print-pdf body {
      background: #020617 !important;
    }
    html.print-pdf .reveal .slide-background {
      background: #020617 !important;
    }
    html.print-pdf .reveal .slides section {
      background-color: #020617 !important;
      color: #fff !important;
    }
    html.print-pdf .reveal .slides section h1,
    html.print-pdf .reveal .slides section h2,
    html.print-pdf .reveal .slides section h3,
    html.print-pdf .reveal .slides section h4,
    html.print-pdf .reveal .slides section h5,
    html.print-pdf .reveal .slides section p,
    html.print-pdf .reveal .slides section li,
    html.print-pdf .reveal .slides section span {
      color: #fff !important;
    }
    html.print-pdf .reveal .slides section a {
      color: #e7ad52 !important;
    }
    html.print-pdf * {
      -webkit-print-color-adjust: exact !important;
      print-color-adjust: exact !important;
    }
  }
</style>
```

Esse CSS garante que o fundo escuro e as cores sejam preservados ao gerar PDF.

## 4. Estrutura esperada

```
aula2/
├── index.html          # Apresentação Reveal.js
├── css/
│   ├── layout.css
│   ├── mattropolis.css
│   └── ...
├── dist/               # Core do Reveal.js
└── plugin/             # Plugins do Reveal.js
```

## Checklist

- [ ] Pasta criada com estrutura Reveal.js
- [ ] Adicionado no `data.json`
- [ ] CSS de impressão adicionado no `index.html`
- [ ] Testar abrindo a aula normalmente
- [ ] Testar clicando no ícone de PDF (fundo deve ficar escuro)
