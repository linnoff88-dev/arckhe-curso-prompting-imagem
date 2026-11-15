# Prompting de Imagem v6.2

Curso aberto e gratuito, com 7 mÃ³dulos e 21 aulas de aproximadamente 15 minutos.
Enquadramento, luz, composiÃ§Ã£o, referÃªncias, ediÃ§Ã£o e organizaÃ§Ã£o de imagens de produto.

[PortuguÃªs](https://inematds.github.io/curso-prompting-imagem/) Â· [English](https://inematds.github.io/curso-prompting-imagem/en/) Â· [EspaÃ±ol](https://inematds.github.io/curso-prompting-imagem/es/).

## Estrutura

- `landing.html`: apresentaÃ§Ã£o e mÃ³dulos. `index.html`: entrada pÃºblica.
- `aulas/`: aulas montadas a partir das fontes editoriais em `context/`.
- `curso.html`: pÃ¡gina Ãºnica com progresso local, prÃ¡ticas e revisÃ£o espaÃ§ada.
- `assets/`: motor oficial INEMA v6 e 21 ilustraÃ§Ãµes geradas com Codex image_gen.
- `context/curriculo.md`: pÃºblico e objetivos; `context/leitor-*.md`: revisÃµes simuladas.

A referÃªncia visual Ã© OSWork v6.2: tema papel, leitura em uma coluna e aprendizagem discreta.
A identificaÃ§Ã£o v6.2 indica o formato educacional; a versÃ£o deste conteÃºdo Ã© 1.1.0.
As imagens sÃ£o ilustraÃ§Ãµes didÃ¡ticas, nÃ£o comparaÃ§Ãµes experimentais entre geradores.
O conteÃºdo Ã© autoral; nÃ£o inclui vÃ­deos nem transcriÃ§Ãµes do acervo privado que originou o planejamento.

## Montagem e validaÃ§Ã£o

Requer Python 3 e a skill `formato-curso-v6` instalada. `montar.py` usa o caminho local definido em `SKILL`.

```sh
python3 montar.py
node /caminho/formato-curso-v6/scripts/auditar-curso.cjs curso.html --json context/auditoria.json
node /caminho/formato-curso-v6/scripts/testar-motor.cjs curso.html
```

Os scripts de validaÃ§Ã£o precisam de Playwright instalado; `PLAYWRIGHT_PATH` pode apontar para o pacote.
NÃ£o editar `curso.html` manualmente. Editar os JSON editoriais e montar novamente.
`revisar_conteudo.py` registra as correÃ§Ãµes da primeira ediÃ§Ã£o; nÃ£o Ã© necessÃ¡rio rodÃ¡-lo para montar.

ValidaÃ§Ã£o desta ediÃ§Ã£o: 21/21 aulas com 10/10 na auditoria automÃ¡tica; 26/26 comportamentos do motor aprovados;
leitura simulada de todas as aulas com nota â‰¥9. Isso nÃ£o equivale a um teste com alunos reais.
Detalhes em `context/validacao.md`.

## Mais no INEMA.CLUB

- [Ficha deste curso](https://www.inema.club/cursos/283-prompting-de-imagem-v6-2-pense-como-diretor-de-fotografia/)
- [Guia para aprender inteligÃªncia artificial](https://www.inema.club/aprender-inteligencia-artificial/)
- [CatÃ¡logo de cursos](https://www.inema.club/cursos/)

## EdiÃ§Ãµes EN/ES

Os catÃ¡logos atuais em `i18n/` foram traduzidos com GPT-6 Luna pela assinatura Codex, sem API externa. Novas traduÃ§Ãµes e retraduÃ§Ãµes passam pelo tradutor central do INEMA (`inema-traduz`, variÃ¡veis `INEMA_TRADUCAO_*`, hoje Sonnet 5.5 pela assinatura).
As 21 aulas, cartÃµes, prÃ¡ticas, glossÃ¡rio e controles estÃ£o em cada idioma; imagens sÃ£o compartilhadas.
Progresso e anotaÃ§Ãµes ficam separados por idioma. ExportaÃ§Ãµes identificam a ediÃ§Ã£o; uma ediÃ§Ã£o rejeita o progresso da outra.
RevisÃµes em `context/revisao-i18n-*.md` sÃ£o simuladas, nÃ£o testes com alunos reais.

ApÃ³s montar o portuguÃªs, reaplique as traduÃ§Ãµes salvas (Python com BeautifulSoup):

```sh
python3 scripts/i18n_local.py build .
python3 scripts/verify_i18n.py .
node scripts/check_i18n_browser.cjs . /tmp/prompting-i18n-checks
```

A montagem nÃ£o chama modelos nem redes. CatÃ¡logos traduzidos estÃ£o em `i18n/`; mudanÃ§as no texto portuguÃªs exigem atualizar o catÃ¡logo e revisar as novas traduÃ§Ãµes. Os scripts de JS e navegador usam os pacotes locais Babel/Playwright indicados em seus arquivos. O motor original `assets/curso.js` Ã© preservado; `assets/curso-i18n.js` Ã© a versÃ£o gerada com proteÃ§Ã£o de importaÃ§Ã£o por idioma.

<!-- inema-backlink:v1 -->
## Mais no INEMA.CLUB

- [Ficha completa deste curso](https://www.inema.club/cursos/283-prompting-de-imagem-v6-2-pense-como-diretor-de-fotografia/)
- [Guia: como aprender inteligÃªncia artificial](https://www.inema.club/aprender-inteligencia-artificial/)
- [Todos os cursos](https://www.inema.club/cursos/)
<!-- /inema-backlink:v1 -->

---

Projeto adaptado da comunidade INEMA TDS - Marca Arckhe