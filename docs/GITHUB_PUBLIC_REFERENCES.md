# Pesquisa de repositórios GitHub públicos — referências para o Holidays Site

**Data da pesquisa:** 19 de novembro de 2026  
**Projeto de destino:** [martaxi-boss/Holidays-site](https://github.com/martaxi-boss/Holidays-site)  
**Estado:** **REFERÊNCIAS DOCUMENTADAS** e recomendação de protótipo em [DECISAO_TECNICA_2026.md](DECISAO_TECNICA_2026.md); não é código incorporado, fork, instalação, build testado nem site publicado.  
**Objetivo:** evitar reconstruir do zero um portal de conteúdos turísticos, exclusivamente sobre o **Algarve**, em inglês britânico, com **5 categorias comerciais e 4 parceiros Awin**.

> **Invariantes comerciais:** Villas & Apartments → **Holidu UK**; Hotels & Resorts → **Logitravel**; Holidays & Cruises → **Logitravel**; Tours & Activities → **Viator UK**; Airport Transfers → **SunTransfers**. Um parceiro principal por categoria, substituível por configuração/links sem destruir URLs e SEO. Não desenvolver checkout ou reservas próprias. Ver [BOOTSTRAP](../BOOTSTRAP.md).

## 1. Resumo executivo — o que reutilizar e porquê

A pesquisa encontrou **um template diretamente próximo da nossa necessidade** (blog de viagens com destinos, mapa e pesquisa), **duas alternativas muito boas para SEO editorial**, alguns projetos interessantes de apresentação e bibliotecas maduras para funcionalidades pontuais.

**Decisão recomendada nesta fase (2026-11-19):** primeiro protótipo com **MasuRii/travelblog-website-template** (já tem destinos, mapa e pesquisa); **themefisher/bookworm-light-astro** é fallback se o primeiro não passar build, QA ou simplificação. **AstroPaper** é terceira opção de arquitetura editorial. Licenças MIT foram verificadas nos três casos. Ver [decisão técnica](DECISAO_TECNICA_2026.md) e [planta do MVP](BLUEPRINT_MVP_ALGARVE.md). Não instalar vários templates juntos.

**Estratégia de reutilização:** escolher **uma base de código**, adaptar rotas, dados e layout para o Algarve, e aproveitar componentes pontuais com licenças compatíveis. Não misturar vários templates inteiros, o que multiplicaria dependências e problemas de manutenção. O modelo comercial continua a ser **links de afiliado**, não motor de reservas.

## 2. Projetos concretos para analisar e reutilizar

### A. Candidatos a base técnica

#### A1. MasuRii — Philippine Travel Blog Template (PRIMEIRO CANDIDATO A TESTAR)

- **Repositório:** https://github.com/MasuRii/travelblog-website-template
- **Demo indicada pelo projeto:** https://masurii.github.io/travelblog-website-template/
- **Licença:** **MIT — verificada em** [LICENSE](https://github.com/MasuRii/travelblog-website-template/blob/main/LICENSE), copyright 2026. Preservar aviso de licença/atribuição se houver reutilização.
- **Stack declarada e inspecionada em package.json:** Astro 5, TypeScript, React 19, Tailwind CSS 4, Leaflet/React Leaflet, Fuse.js, Sharp e Nanostores. Tem scripts de build, lint, testes Vitest, Playwright, acessibilidade e validação de dados.
- **Elementos que interessam ao Algarve:** dados estruturados por destino em `src/data/destinations/`, páginas de destinos, mapa interativo com marcadores, pesquisa local, cartões, hero, galeria, SEO/JSON-LD, organização de conteúdo e UX mobile.
- **Adaptação necessária:** substituir integralmente destinos das Filipinas, textos, imagens e categorias; reduzir para **5 categorias fixas**; colocar Faro, Vilamoura, Quinta do Lago, Albufeira, Lagos, Portimão/Praia da Rocha, Tavira e restantes localidades; adicionar a configuração de **um parceiro Awin por categoria** e `en-GB`.
- **Riscos/custos:** base relativamente complexa para um portal de links; React/PWA, stores, mapas e scripts de imagens podem ser desnecessários para o MVP. Requer QA de dependências, rotas, conteúdo e copyright das fotografias. **O README anuncia boas métricas, mas não se efetuaram testes próprios nem auditoria de segurança.**
- **Decisão:** **CANDIDATO PRIORITÁRIO, não escolhido nem instalado**. Testar uma versão simplificada com Astro estático.

#### A2. Themefisher — Bookworm Light Astro (ALTERNATIVA EDITORIAL)

- **Repositório:** https://github.com/themefisher/bookworm-light-astro
- **Demo do README:** https://bookworm-light-astro.vercel.app/
- **Licença:** **código MIT — verificada em** [LICENSE](https://github.com/themefisher/bookworm-light-astro/blob/main/LICENSE).
- **Stack:** Astro, componentes React, Markdown/MDX, Fuse.js para pesquisa; o README indica categorias, etiquetas, posts relacionados, meta tags SEO, partilha e edição de conteúdo.
- **Para reutilizar:** base de guias e artigos `en-GB`, cartões por localidade, navegação por temas, pesquisa textual e metadados.
- **O que falta:** não é um portal turístico específico, pelo que seriam necessários páginas próprias das cinco categorias, página por destino, mapas opcionais e integração de parceiros.
- **Riscos:** o projeto declara explicitamente que **as fotografias de demonstração NÃO são licenciadas para reutilização**; substituir. A referência a CMS/serviço de terceiros não o torna obrigatório nem autorizado para o nosso projeto.
- **Decisão:** **FORTE ALTERNATIVA** caso se prefira simplicidade, velocidade e conteúdos à experiência de mapa do A1.

#### A3. Sat Naing — AstroPaper (BASE SEO/CONTEÚDO)

- **Repositório:** https://github.com/satnaing/astro-paper
- **Demo:** https://astro-paper.pages.dev/
- **Licença:** **MIT — verificada em** [LICENSE](https://github.com/satnaing/astro-paper/blob/main/LICENSE).
- **Stack:** Astro, TypeScript, Markdown/MDX, Tailwind, Pagefind (pesquisa estática), RSS, sitemap; scripts `build`, `lint` e `format`.
- **Pontos úteis:** bom ponto de partida para conteúdos editoriais, paginação, sitemap, canonicals, pesquisa, SEO, acessibilidade e rotas estáveis.
- **Riscos:** a aparência é de blog, não de portal turístico com cinco grandes categorias; a estrutura de destinos/montra teria de ser adicionada. O `package.json` consultado exige **Node >=22.23.4**; verificar runtime isolado antes de testar.
- **Decisão:** **ALTERNATIVA SEO** se o primeiro release for maioritariamente editorial.

#### A4. Lonestone — Astro Website Template (OPÇÃO DE CONTEÚDO EDITÁVEL)

- **Repositório:** https://github.com/lonestone/astro-template
- **Licença:** **MIT — verificada em** [LICENSE](https://github.com/lonestone/astro-template/blob/main/LICENSE).
- **Stack:** Astro 6, MDX, Tailwind 4, coleções de conteúdo tipadas e CMS baseado em ficheiros. README refere conteúdo em Git e site estático, com integração/adaptador de Netlify.
- **Pontos úteis:** estrutura de conteúdo e guias, breadcrumbs e organização reutilizável, eventualmente edição por interface no futuro.
- **Riscos:** inclui funções de documentação/API e dependências de Netlify/CMS que **não precisamos para o MVP**; evitar trazer infraestrutura externa ou novos custos sem decisão.
- **Decisão:** **ALTERNATIVA COMPLEMENTAR**, não misturar como segundo motor com A1/A2.

### B. Exemplos de UX e apresentação turística (inspirar, não adotar o backend)

#### B1. Travello — Travel Agency Landing Page

- **Repositório:** https://github.com/hakangokdev/travello
- **Licença:** **MIT — verificada em** [LICENSE](https://github.com/hakangokdev/travello/blob/main/LICENSE).
- **Stack:** Next.js 15, TypeScript e Tailwind; landing page com hero, grelha de destinos, cartões, blog, sliders e design responsivo.
- **Inspiração concreta:** homepage mais apelativa, layout dos **cinco cartões**, secção de destinos e imagens grandes, adaptação mobile.
- **Adaptação importante:** o formulário de reserva de demonstração **NÃO deve virar checkout próprio**. Trocar eventuais formulários por links afiliados e guias locais. Não precisamos de instalar Next.js apenas para copiar ideias de layout.
- **Decisão:** **REFERÊNCIA VISUAL**, não base preferida.

#### B2. PritamSarbajna — Tourism Website / ADVENTURE

- **Repositório:** https://github.com/PritamSarbajna/tourism-website
- **Demo:** https://simple-tourism-organization.netlify.app/
- **Licença:** **MIT — verificada em** [LICENSE](https://github.com/PritamSarbajna/tourism-website/blob/main/LICENSE).
- **Stack:** HTML, CSS e JavaScript puros.
- **Inspiração:** cartões de excursões, secção explorar destinos, hero simples e componentes fáceis de estudar.
- **Limite:** não oferece a organização SEO/conteúdo estruturado de um portal grande; servir como **inspiração visual** ou para protótipos de componentes, não para escalar centenas de páginas.
- **Decisão:** REFERÊNCIA VISUAL SIMPLES.

#### B3. Charca — Astro Blog Template (referência técnica mínima)

- **Repositório:** https://github.com/Charca/astro-blog-template
- **Demo:** https://astro-blog-template.netlify.app/
- **Licença:** **MIT — verificada em** [LICENSE](https://github.com/Charca/astro-blog-template/blob/main/LICENSE).
- **Funcionalidades anunciadas:** Astro, Markdown, SEO, canonical, OpenGraph, sitemap, robots e componente `Tour.astro`.
- **Limite:** README menciona Astro 4; **não tratar como stack atual pronta sem atualização/testes**.
- **Decisão:** inspiração de estrutura limpa, não candidato principal face a A1–A3.

### C. Bibliotecas/funcionalidades reutilizáveis

#### C1. Pagefind — Pesquisa sem base de dados

- **Repositório:** https://github.com/pagefind/pagefind
- **Documentação:** https://pagefind.app/
- **Licença:** MIT, verificada em `LICENSE`.
- **Para quê:** pesquisar guias, localidades e atividades **no nosso próprio portal** sem servidor de pesquisa ou API paga.
- **Quando:** integrar apenas se a base escolhida ainda não incluir uma pesquisa local suficiente. **AstroPaper já inclui Pagefind; MasuRii usa Fuse.js** — não adicionar os dois sem necessidade.

#### C2. Leaflet — Mapa de localidades do Algarve

- **Repositório:** https://github.com/Leaflet/Leaflet
- **Documentação:** https://leafletjs.com/
- **Licença:** **BSD-2-Clause**, verificada em `LICENSE`.
- **Para quê:** mapa navegável de localidades do Algarve, se o valor para o visitante justificar peso e manutenção. A1 já usa Leaflet.
- **Cuidados:** mapas e tiles têm **termos de licença e limites próprios**, distintos da biblioteca JavaScript. Não presumir mapas/serviços pagos gratuitos para tráfego ilimitado.

#### C3. Lychee — Auditoria de links

- **Repositório:** https://github.com/lycheeverse/lychee
- **Documentação:** https://lychee.cli.rs/
- **Licença:** README declara dupla **MIT/Apache-2.0** (licenças em `LICENSE-MIT` e `LICENSE-APACHE`).
- **Para quê:** encontrar ligações editoriais quebradas em páginas/Markdown e integrar verificações não intrusivas no CI.
- **Restrição:** **não fazer cliques automáticos repetidos nos links de tracking Awin**, pois isso pode produzir cliques artificiais e violar regras de afiliação. Excluir tracking de testes automáticos de crawling; validar destinos afiliados manualmente e com processos autorizados.
- **Quando:** fase de QA, após existir site.

### A5. SriGuide — exemplo open source de guia turístico regional

- **Repositório:** https://github.com/Camino-lk/SriGuide
- **Licença:** **MIT — verificada** em https://github.com/Camino-lk/SriGuide/blob/main/LICENSE
- **Stack:** Astro + Starlight, estrutura por Transport, Accommodation, Attractions, Safety, etc.; site para uma região-país específico.
- **Utilidade:** arquitetura de navegação e guias de viagem, páginas de informação prática; não é montra afiliada nem base preferida pela estética documental.
- **Commit de referência no estudo:** `818c3a64e41bcd0b7d03c4a2da059cb9ac0dd3bf`.

## 3. Repositórios encontrados que NÃO se recomendam como base

**Estarem públicos no GitHub não significa que o código ou os assets possam ser copiados.** Exemplos revistos:

| Projeto | URL | Motivo da cautela |
|---|---|---|
| Viatours Voyage | https://github.com/basudevkumer/viatours-voyage | README declara **all rights reserved**, apesar do código ser público. Só consultar como inspiração geral; **não copiar código, fotografias ou design**. |
| Jadoo / Nuxt 3 | https://github.com/thecodingmontana/jadoo | Não foi encontrado `LICENSE` na raiz durante a consulta; **não incorporar código sem permissão/licença confirmada**. |
| Quickship Affiliate Landing | https://github.com/quickship-labs/landing-page-template | README diz MIT, mas `LICENSE` não foi encontrado na raiz. Útil como referência de estrutura de afiliados/SEO; **não copiar até clarificar licença**. |
| Site.Set | https://github.com/joaocruzzo/site-set | Template de afiliados Next.js/Contentlayer; não foi encontrado `LICENSE` na raiz e há stack adicional para manter. Inspiração apenas até esclarecer direitos. |
| Cult Directory Template | https://github.com/nolly-studio/cult-directory-template | Documentação apresenta versão gratuita GPL, funções de admin pagas e um `LICENSE.md` com termos de utilização específicos. Complexo e com restrições: **não importar como base sem revisão jurídica/técnica**. |
| Astroship | https://github.com/surjithctly/astroship | README indica licença **GPL-2.0** para a versão gratuita e funcionalidades Pro pagas; não é a escolha simples de licença permissiva para o nosso portal. |
| Apps completas de reservas | Ex.: https://github.com/mojahidhasan/fullstack-nextjs-golobe-travel-agency | Construir checkout, contas e inventário não faz parte do nosso modelo. Custos e riscos desnecessários nesta fase. |

## 4. Comparação rápida para a decisão de MVP

| Candidato | Destinos e mapa | Conteúdo/SEO | Simplicidade | Adequação inicial |
|---|---|---|---|---|
| **MasuRii Travelblog** | **Já inclui** estruturas de destinos e mapa | Inclui mecanismos declarados | Média-baixa (stack maior) | **Muito alta**, se simplificado |
| **Bookworm Light Astro** | A criar | **Forte** para artigos/categorias | Alta | **Muito alta** para MVP editorial |
| **AstroPaper** | A criar | **Forte** para artigos, sitemap, Pagefind | Alta | Alta para SEO editorial |
| **Lonestone Astro** | A criar | Conteúdos tipados + CMS | Média | Útil se edição de conteúdo for prioritária |
| **Travello** | UI demonstrativa de destinos | Menos focado em gestão editorial | Média | Inspiração estética |
| **Pritam Tourism** | UI simples | Gestão editorial a desenvolver | Alta no protótipo, baixa na escala | Inspiração/experiência visual |

**Escolha preliminar de estudo:** começar por **A1 MasuRii** e **A2 Bookworm Light Astro**. Selecionar **uma** base definitiva **após build e testes reais** (não foram executados hoje).

## 5. Como transformar a referência escolhida no nosso site

### Páginas e modelo de dados a preservar

```text
Holidays Site — único projeto
├── /
│   ├── Villas & Apartments  -> Holidu UK
│   ├── Hotels & Resorts      -> Logitravel
│   ├── Holidays & Cruises    -> Logitravel
│   ├── Tours & Activities    -> Viator UK
│   └── Airport Transfers     -> SunTransfers
├── /destinations/
│   ├── faro/
│   ├── vilamoura/
│   ├── quinta-do-lago/
│   ├── albufeira/
│   ├── lagos/
│   ├── portimao/
│   ├── praia-da-rocha/
│   ├── tavira/
│   └── restantes localidades do Algarve...
├── /guides/... (artigos únicos e verificados)
└── /legal/...  (privacidade, transparência de afiliados)
```

O código deverá separar três entidades:
1. **Categoria editorial/comercial**, com slug, nome `en-GB`, imagem licenciada, descrição e `primaryPartnerKey`.
2. **Destino Algarve**, com slug, geografia, conteúdo original, atividades pertinentes e ligações internas.
3. **Parceiro**, com ID Awin, estado de aprovação, política de atribuição, URL oficial de tracking/deep-link autorizado, `clickref` sem dados pessoais, histórico de trocas e testes.

**Evitar o anti-padrão:** colar links Holidu/Viator/Logitravel diretamente em cada texto ou cartão. **Um parceiro por categoria deve ser substituível por configuração**, preservando as URLs SEO e o histórico.

### O que reaproveitar do template

- Header / hero / cinco cartões, responsividade.
- Estrutura dos destinos e guias.
- Meta tags, canonical, sitemap, breadcrumbs e pesquisa.
- Componentes de imagem / galeria com imagens próprias ou licenciadas.
- Mapa se realmente melhorar a navegação (não obrigatório no primeiro release).

### O que retirar

- Reservas, carrinho, checkout, motor de preços e contas de utilizadores.
- Dados, estatísticas, avaliações e testemunhos fictícios do template.
- PWA, scripts de imagens, CMS, IA, mapas ou integrações externas **sem necessidade demonstrada**.
- Qualquer conteúdo associado às Filipinas/viagens globais que quebre o âmbito "só Algarve".
- Banners, imagens ou marcas sem direitos comerciais demonstrados.

## 6. Porta de qualidade antes de copiar ou incorporar código

1. Confirmar repositório e **commit/versão** escolhidos; ler `LICENSE`, atribuições de dependências e direitos de imagens, fontes e iconografia.
2. **Testar num ambiente isolado e temporário**, sem instalações globais na VPS; dependências pinadas, `npm ci` ou equivalente, e varrimento de vulnerabilidades.
3. Executar build, lint, testes existentes e pelo menos um teste de navegador mobile/desktop; **não declarar aprovação com apenas README ou prints da demo**.
4. Verificar HTML gerado, routes, links, sitemap, canonical, meta tags, localização `en-GB`, performance e acessibilidade.
5. Eliminar funções não necessárias antes de publicar; manter documentação e licença original quando aplicável.
6. Definir deploy em pasta isolada e por **GitHub Actions → SSH/VPS**, se autorizado, respeitando o workflow existente do proprietário; sem pontes novas.
7. Configurar Awin e links apenas após aprovação; **nenhum programa aqui foi aderido automaticamente**.
8. Após QA, integrar a base escolhida no mesmo repositório Holidays-site (e não como vários projetos separados), com commit auditável e rollback.

## 7. Plano para a primeira comparação prática (AINDA NÃO EXECUTADO)

| Prova | MasuRii | Bookworm |
|---|---|---|
| Repositório/clonagem no ambiente isolado | pendente | pendente |
| Licença do código lida | **MIT verificada** | **MIT verificada** |
| Build reproduzível | pendente | pendente |
| Dependências / segurança | pendente | pendente |
| Home com 5 cartões + mobile | pendente | pendente |
| Páginas Faro, Vilamoura e Quinta do Lago | pendente | pendente |
| 5 categorias / 4 parceiros configuráveis | pendente | pendente |
| Sitemap, canonical e SEO `en-GB` | pendente | pendente |
| Custo de manutenção e complexidade | pendente | pendente |
| Decisão final de base | **não tomada** | **não tomada** |

**Critério de escolha:** o menor conjunto de alterações que permita lançar, medir cliques Awin e publicar guias úteis com bom SEO até ao verão de 2027, sem backend desnecessário.

## 8. Fontes e rastreabilidade

Esta pesquisa foi feita em GitHub público e verificada diretamente pelos **README, LICENSE e, quando aplicável, package.json** de cada candidato. Alguns repositórios sem ficheiro de licença foram explicitamente limitados a inspiração.

**Não foi feito:** fork, clone integral, cópia de assets/código, validação de performance por Lighthouse própria, auditoria de segurança, deploy, instalação ou candidatura Awin. As demos e métricas descritas pelos autores **não foram tomadas como testes independentes**.

**Referências de projeto relacionadas:**
- [Decisões do negócio](../BOOTSTRAP.md)
- [Parceiros e atribuição Awin](PARTNERS_AWIN.md)
- [SEO e localidades Algarve](SEO_ALGARVE_2027.md)
- [Plano de execução](EXECUTION_PLAN.md)

**Regra para futuras alterações:** manter este documento como catálogo de referências; registar testes e decisões concretas sem apagar os candidatos rejeitados nem as razões de licença/manutenção.
