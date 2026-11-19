# DECISÃO TÉCNICA FUNDAMENTADA — base para o Holidays Site

**Data:** 2026-11-19  
**Fase:** pesquisa/arquitetura pronta para implementação; **não é código implantado**.  
**Objetivo:** decidir a melhor base de software livre para portal turístico **só Algarve**, `en-GB`, 5 categorias, 4 parceiros afiliados, SEO orgânico dirigido ao Reino Unido e manutenção simples.  
**Fonte de verdade comercial:** [../BOOTSTRAP.md](../BOOTSTRAP.md). **Referências GitHub:** [GITHUB_PUBLIC_REFERENCES.md](GITHUB_PUBLIC_REFERENCES.md). **Sites de inspiração:** [REFERENCIAS_WEB_REAIS.md](REFERENCIAS_WEB_REAIS.md).

## 1. Recomendação concreta

**Tecnologia recomendada: Astro com geração estática de páginas + TypeScript + conteúdo versionado em Git + CSS/Tailwind de um único template.** Não precisamos de uma base de dados, contas de clientes, carrinho, motores de reservas nem um servidor Node permanente para começar.

**Base principal recomendada para o primeiro protótipo:** [MasuRii/travelblog-website-template](https://github.com/MasuRii/travelblog-website-template).  
**Licença de código:** MIT, validada em `LICENSE`.  
**Commit de referência do upstream consultado:** `c1d76edd3240c041aa9a437f189aec5424c23dd4` (último commit da branch main obtido na pesquisa em 2026-11-19; data interna 2026-01-17). **Fixar SHA ao realizar os testes; confirmar novamente antes de copiar.**

### Razão da escolha

A nossa necessidade não é só um blog: precisamos de páginas estruturadas por **localidade**, navegação entre destinos e **cinco portas comerciais**. Nesse template verifiquei código concreto (não apenas publicidade do README):

- `src/pages/index.astro`: homepage montada com `Hero`, `QuickSearch`, `FeaturedDestinations`, `CategoriesShowcase`, `MapPreview`, artigos e newsletter.
- `src/pages/destinations/[slug].astro`: rota dinâmica de destinos; `src/pages/destinations/index.astro`: listagem de destinos.
- `src/data/destinations/*.ts` e `src/data/destinations/types.ts`: modelo estruturado de destinos com descrições, imagens, coordenadas, informações práticas e outros campos.
- `src/constants/categories.ts`: filtros de temas existentes, **a substituir** pela nossa separação de categorias comerciais e etiquetas editoriais.
- `src/layouts/BaseLayout.astro`: layout e SEO; atualmente utiliza `lang = 'en'`, **mudar explicitamente para `en-GB`**.
- `src/components/DestinationCard.astro`, `CategoriesShowcase.astro`, `QuickSearch.tsx`, `MapPreview.astro`: peças de UI que podem diminuir tempo de construção.
- `package.json` contém scripts de build, lint, testes unitários, Playwright, acessibilidade, validação de dados e SEO.

**Limitações reais:**
- Base **pouco validada socialmente** (a página pública indicava apenas ~2 estrelas na pesquisa). Não confundir documentação detalhada com robustez confirmada.
- Stack com Astro + React + Nanostores + Leaflet + Fuse.js + PWA/service worker; **complexidade excessiva se transplantada toda**.
- Código destinado às Filipinas, com imagens, exemplos, itinerários, avaliações e outras funcionalidades que não queremos.
- A demo estava indicada pelo autor em https://masurii.github.io/travelblog-website-template/ , mas **a abertura pelo serviço de consulta web não foi possível** nesta pesquisa. Não afirmar inspeção visual completa da demo.
- **Nenhum build/lint/Playwright/auditoria de dependências foi executado**; seleção é uma **recomendação para protótipo**, não aprovação de produção.

**Porta de decisão:** avançar com MasuRii *somente se* o protótipo isolado compilar, os testes-chave passarem, o bundle puder ser simplificado e a adaptação a `en-GB` + cinco categorias for razoável. Se falhar a porta, usar a alternativa abaixo; **não recomeçar a pesquisa**.

## 2. Alternativa prioritária (fallback)

[themefisher/bookworm-light-astro](https://github.com/themefisher/bookworm-light-astro).  
**Licença:** MIT, verificada no ficheiro `LICENSE`.  
**Commit de referência consultado:** `b94f01efcf2296568902975118305cd0da9cd80e`, data interna 2026-06-27.  
**Demo aberta:** https://bookworm-light-astro.vercel.app/

**Vantagens:** base de artigos e categorias, SEO, MDX/Markdown, procura interna com Fuse.js, design editorial, configuração mais previsível para conteúdo. Facilita o arranque se o portal for sobretudo guias de localidades. **Desvantagens:** teria de criar estrutura de destinos, mapa e componente específico de cinco categorias; a demo é um blog genérico.

**Terceira opção de segurança:** [satnaing/astro-paper](https://github.com/satnaing/astro-paper), MIT, atualizada na pesquisa (commit `4bc2dafac5405c6c4f06d1daba275e836e656097`, 2026-11-15). Excelente para artigos e pesquisa Pagefind, mas requer acrescentar camada de portal de destinos. **Não instalar os três projetos conjuntamente.**

**Mais uma referência funcional:** [Camino-lk/SriGuide](https://github.com/Camino-lk/SriGuide), MIT verificada, Astro + Starlight, commit `818c3a64e41bcd0b7d03c4a2da059cb9ac0dd3bf` (2026-11-18). Guia de turismo regional estruturado por transportes, alojamento e atividades. Útil para pensar a arquitetura editorial, mas a interface tipo documentação não é ideal como montra comercial.

## 3. Matriz de decisão por critérios do nosso negócio

Valores **qualitativos de adequação documental**, não resultados de benchmark ou Lighthouse.

| Critério | MasuRii | Bookworm | AstroPaper | SriGuide |
|---|---|---|---|---|
| Estrutura de destinos de raiz | **Sim** | A criar | A criar | Guias regionais, modelo distinto |
| Página inicial turística | **Sim** | Precisa adaptação | Precisa adaptação | Guia informativo |
| Navegação por cinco categorias | Adaptar componentes | Adaptar categorias | Criar | Adaptar navegação |
| SEO estático | Sim, anunciado/código visto | Sim, anunciado | Sim, anunciado | Sim, anunciado |
| Pesquisa local | Fuse.js | Fuse.js | Pagefind | Estrutura Starlight |
| Mapa | Leaflet já integrado | Não central | Não central | Leaflet como dependência |
| Complexidade do MVP | Mais elevada; simplificar | Moderada | Moderada | Moderada |
| Licença de código | MIT | MIT | MIT | MIT |
| Teste real de build neste estudo | **Pendente** | **Pendente** | **Pendente** | **Pendente** |

**Conclusão:** usar MasuRii se passar nos testes; caso contrário, Bookworm. Não faz sentido desenvolver uma plataforma de reservas. A decisão de MVP deve minimizar **tempo para publicar páginas locais úteis + fiabilidade de links afiliados**, não maximizar funcionalidades.

## 4. O que adaptar do MasuRii — mapeamento de ficheiros

| Origem do upstream | Ação no Holidays Site |
|---|---|
| `src/pages/index.astro` | manter como base, reescrever para hero Algarve, localização + **5 cartões** |
| `src/pages/destinations/[slug].astro` | manter padrão de páginas por cidade/localidade do Algarve |
| `src/data/destinations/*.ts` | **substituir dados** das Filipinas por Faro, Vilamoura, Quinta do Lago, Albufeira, Lagos, Portimão, Praia da Rocha, Tavira e restante Algarve |
| `src/data/destinations/types.ts` | simplificar o tipo; campos apenas verificáveis |
| `src/constants/categories.ts` | separar **categorias comerciais** das **tags** de temas/destinos |
| `src/components/CategoriesShowcase.astro` | exatamente cinco categorias; cada uma usa configuração de UM parceiro |
| `src/components/QuickSearch.tsx` | pesquisar **páginas do nosso portal** por nome/localidade, não prometer procurar inventário ao vivo de parceiros |
| `src/components/MapPreview.astro` | manter opcional/de carregamento tardio; foco primeiro em navegação rápida |
| `src/layouts/BaseLayout.astro` | `en-GB`, SEO/canonical/OG, consentimento adequado |
| `src/pages/privacy.astro`, `terms.astro` | substituir pelos nossos textos legais revistos; NUNCA reutilizar dados/identidade do autor |
| `src/pages/map.astro` | fase 2 se mobile, mapa e custos de tiles justificarem |
| `src/components/DemoLinkModal.tsx` | **remover** — demo não faz parte do produto |
| `NewsletterSignup` | remover do MVP; não colecionar emails sem necessidade |
| `src/pages/itineraries.astro`, `packing-list.astro` | adiar, não precisamos para lançar com as cinco categorias |
| Service worker/PWA em `BaseLayout.astro` | **desativar no MVP**, evita caching obsoleto de links e dados |
| Dados de `rating`, `author`, `stats.budget` dos exemplos | eliminar/usar só se comprovados; **nunca publicar classificações falsas, preços fictícios ou falsa autoria** |

### A arquitetura alvo é independente do tema

- `src/content/destinations` — um documento por destino, com conteúdo original, coordenadas verificadas e hierarquia da região.
- `src/content/guides` — artigos com intenção de pesquisa real.
- `src/config/categories.ts` — **5 chaves fixas** e URLs editoriais imutáveis.
- `src/config/partners.ts` — ID Awin, estado de adesão e links oficiais por categoria/localidade.
- `src/lib/affiliate.ts` — validação de URL e preparação de deep links **só após aprovação**, sem qualquer fake click/tracking.
- `src/components/AffiliateCTA.astro` — CTA que se apresenta apenas com URL autorizada; e.g., `rel="sponsored noopener noreferrer"` em links externos quando aplicável.
- `src/pages/destinations/[slug].astro` — página editorial com blocos contextuais para serviços e destinos relacionados.
- `src/pages/<category-slug>/` — páginas comerciais com orientação local original; cada uma aponta ao parceiro definido.

**A marca e o domínio final continuam pendentes.** Não usar `Holidu`, `Viator` ou `Logitravel` no nome do site.

## 5. Princípio técnico chave: trocar parceiro, manter SEO

A lógica não deve ligar páginas diretamente à empresa. O vínculo permanente é **categoria → parceiro ativo**.

```text
Category: villas-apartments
  └── activePartnerKey: holidu-uk
        └── approved: false/true
        └── awinAdvertiserId: 31469
        └── linkPolicy: authorized_deep_link_or_default

Category: hotels-resorts
  └── activePartnerKey: logitravel-pt

Category: holidays-cruises
  └── activePartnerKey: logitravel-pt

Category: tours-activities
  └── activePartnerKey: viator-uk

Category: airport-transfers
  └── activePartnerKey: suntransfers
```

**Um parceiro pode operar duas categorias**, mas cada categoria tem um parceiro ativo único. Quando não houver programa aprovado ou link validado, **não mostrar CTA falsamente afiliado**; manter conteúdo editorial e navegação interna. Quando se troca parceiro, só muda configuração e testes, nunca `/hotels-resorts/` ou `/destinations/lagos/`.

Não guardar credenciais privadas no GitHub público. Se houver tokens Awin/feeds, secrets no mecanismo existente e config pública limitada aos IDs/links que podem ser divulgados.

## 6. Critérios técnicos obrigatórios (gate de adoção)

**G0 — legal e integridade:**
- Licença upstream e avisos de copyright presentes e compatíveis com uso comercial; sem cópia de imagens do template sem direitos demonstrados.
- Excluir dados de demonstração, componentes de reservas falsas, avaliações e preços inventados.
- Sem chaves, segredos, acessos ou downloads privados no repositório público.

**G1 — ambiente:**
- Projeto temporário **isolado**; não instalar runtimes/dependências globalmente na VPS.
- Fixar commit upstream e dependências reprodutíveis, usar `npm ci` ou equivalente suportado; auditoria de dependências.

**G2 — build/testes:**
- Build completo, verificação de tipos, lint, testes unitários e E2E disponíveis.
- Inspeção mobile e desktop, SEO, links internos, imagens, console, overflow e teclado.

**G3 — experiência Algarve:**
- Homepage com **cinco** cartões e **quatro** parceiros configurados;
- Faro cidade/aeroporto, Vilamoura e Quinta do Lago presentes como principais, junto de Albufeira, Lagos, Portimão/Praia da Rocha e Tavira;
- páginas editoriais `en-GB`, metadados únicos, sitemap sem páginas vazias;
- sem sistema de reservas nem pagamentos do nosso lado.

**G4 — cliques Awin:**
- Zero tracking links ativos antes de adesão; geração oficial/deep links com consentimento/regras;
- testes reais de destino e contagem Awin quando aderido;
- métricas separadas por categoria/localidade;
- substituição de um parceiro não altera as páginas SEO.

**G5 — publicação:**
- Deploy próprio, versionado com rollback, via **GitHub Actions → SSH → pasta isolada VPS**, quando especificamente autorizado. Nada foi instalado/publicado por esta investigação.

## 7. Estado e limites

- **PASS documental:** repositórios localizados, licença MIT lida para os quatro candidatos, `package.json` e ficheiros de UI/destinos de MasuRii inspecionados; vários sites reais analisados como inspiração.
- **PENDENTE:** clonagem, build, testes, auditoria de segurança, QA visual próprio, validação de performance e deploy.
- **RECOMENDAÇÃO:** MasuRii como primeira base a testar; **Bookworm como alternativa fechada**, não há necessidade de continuar a procurar templates indefinidamente.
- **NÃO INICIADO:** desenvolvimento do site Holidays Site, candidaturas Awin, compra de domínio, SEO indexado e dados de tráfego.
