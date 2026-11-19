# PROJECT HANDOFF — Holidays Site / Algarve 2027

**Estado:** `PLANEAMENTO CONSOLIDADO — PRONTO PARA INICIAR IMPLEMENTAÇÃO`  
**Data de referência:** 19 de novembro de 2026  
**Repositório:** https://github.com/martaxi-boss/Holidays-site — `main`  
**Destinatários:** proprietário, ChatGPT Work, Codex, Ferrari e futuros colaboradores técnicos.  
**Este é o ponto de entrada para retomar o trabalho sem repetir a discussão.** Leia primeiro este ficheiro e depois os documentos específicos no índice abaixo.

## 1. Resumo executivo — o negócio em 60 segundos

O proprietário quer um **portal independente sobre férias e turismo em todo o Algarve, Portugal**, com conteúdo exclusivamente em **inglês britânico (`en-GB`)**, dirigido prioritariamente a turistas do **Reino Unido**, com SEO orgânico e perspetiva de ganhar tração antes do **verão de 2027**.

**Modelo comercial:** o site explica, orienta e recomenda; o visitante escolhe uma categoria e é encaminhado por **link afiliado Awin autorizado** para o anunciante, que apresenta ofertas, gere reservas, cobra, presta o serviço e trata do atendimento. **Não temos checkout, motor de reservas, inventário de terceiros, pagamentos dos turistas ou apoio ao cliente de viagens.**

O princípio do proprietário é **começar, medir e melhorar**, não esperar por um sistema gigantesco ou por todas as comissões/perfeição antes de lançar um MVP útil. O site mantém as suas páginas e SEO independentemente da eventual substituição de um parceiro.

## 2. Decisões comerciais fechadas pelo proprietário

| # | Categoria visível no site (`en-GB`) | Parceiro principal planeado | Programa na Awin | Estado |
|---|---|---|---|---|
| 1 | **Villas & Apartments** | **Holidu UK** | `31469` | Not joined / candidatura por fazer |
| 2 | **Hotels & Resorts** | **Logitravel** | PT `11173` | Not joined / candidatura por fazer |
| 3 | **Holidays & Cruises** | **Logitravel** | PT `11173` | Not joined / candidatura por fazer |
| 4 | **Tours & Activities** | **Viator UK** | `7038` | Not joined / candidatura por fazer |
| 5 | **Airport Transfers** | **SunTransfers** | `111238` | Not joined / candidatura por fazer |

**Regra imutável até nova decisão do proprietário:** **cinco categorias, um único parceiro principal por categoria, quatro parceiros diferentes**; **Logitravel é o único parceiro repetido**, nas categorias 2 e 3. Não misturar vários anunciantes na mesma categoria no MVP só para ganhar comissões.

**Questões comerciais críticas por esclarecer antes de botões de reserva em produção:**
- Logitravel **PT**: confirmar se aceita e remunera reservas de turistas UK em site `en-GB`, com destino Algarve; validar idioma e deep links. **Voos isolados não são comissionáveis** nos termos do programa PT consultados; não contar com receita de flights-only.
- Holidu **UK**: confirmar comissão/base de cálculo e que a reserva se conclui na Holidu. Redirecionamentos para terceiros não são necessariamente comissionáveis. Histórico Awin de aprovações baixo; acompanhar.
- Viator UK: confirmar disponibilidade das experiências do Algarve, taxa, exclusões, autorização de conteúdo/deep links e validação após a experiência.
- SunTransfers: confirmar a cobertura de Faro Airport para cada localidade, taxa aplicável, link de destino e atribuição para britânicos.
- Não transportar taxas de programas próprios/ES/PT para o contrato UK como se fossem equivalentes. Ver [docs/PARTNERS_AWIN.md](docs/PARTNERS_AWIN.md).

### Política de substituição de parceiros — decisão expressa do proprietário

Se houver visitas e cliques, mas o link perder tracking, o parceiro não atribuir vendas elegíveis, rejeitar pagamentos, ou não converter depois de dados suficientes, **estudar e substituir exclusivamente o parceiro dessa categoria**, sem remover categorias, páginas de localidades ou URLs indexadas. Antes de substituir: validar cliques locais vs Awin, deep links, dispositivo, origem UK, serviço elegível, último clique, cancelamentos e tempo de validação. **Não assumir que navegar livremente no site do parceiro garante qualquer comissão.**

Candidatos alternativos, com elegibilidade a confirmar: Trip.com UK / Trivago UK (hotelaria); GetYourGuide UK (experiências); Shuttle Direct UK / Holiday Taxis / Hoppa (transfers); Holidu ES & PT (alojamento, apenas se adequado a UK). Guardar histórico de mudanças e métricas. Ver matriz detalhada.

## 3. Âmbito geográfico — SÓ Algarve, mas todo o Algarve

**Prioridade visível e editorial:** **Faro (cidade e aeroporto, com intenções de pesquisa distintas), Vilamoura, Quinta do Lago**, Albufeira, Lagos, Portimão, Praia da Rocha e Tavira.

**Cobertura a alargar sem esquecer:** Aljezur, Burgau, Salema, Alvor, Armação de Pêra, Olhão, Manta Rota, Altura, Monte Gordo e outras localidades do Algarve com conteúdo de valor. Navegação possível por Algarve ocidental/central/oriental.

Os destinos geográficos **não são mais categorias comerciais**. O utilizador escolhe por categoria ou por localidade; uma página local apresenta apenas as categorias pertinentes e o parceiro único correspondente.

**SEO:** Google UK e pesquisas sobre Algarve, com `en-GB`. Não existe garantia de ranking, indexação ou comissões em 3 meses. O foco inicial são termos específicos e páginas completas/úteis, não páginas vazias duplicadas. Medir impressões/cliques UK no Search Console e os visitantes já fisicamente no Algarve separadamente.

## 4. Solução técnica recomendada — aproveitar código aberto existente

**Preferência para PRIMEIRO PROTÓTIPO:** [MasuRii / travelblog-website-template](https://github.com/MasuRii/travelblog-website-template), código **MIT**, em Astro + TypeScript, com páginas de destinos, hero, cards, pesquisa, mapa, componentes responsivos e SEO. Referência upstream pesquisada: `c1d76edd3240c041aa9a437f189aec5424c23dd4` (confirmar versão/licença no momento do teste).

**Fallback concreto:** [themefisher/bookworm-light-astro](https://github.com/themefisher/bookworm-light-astro), MIT, mais simples para blog/guias/SEO. Outra opção: [satnaing/astro-paper](https://github.com/satnaing/astro-paper), MIT, para estrutura editorial. **Não juntar vários templates inteiros.**

**Decisão de arquitetura:** site preferencialmente **estático em Astro**, sem DB, sem contas de utilizadores, sem checkout, sem serviços pagos obrigatórios, sem servidores adicionais nem AI/chatbot. Remover da base conteúdos/dados/fotos das Filipinas, avaliações fictícias, experiências de demonstração, PWA e complexidade que não sirva o MVP. Só usar fotos e assets com licença adequada.

**Critério antes de adotar:** testar clone isolado, dependências/licenças, build, lint, testes, páginas mobile/desktop, SEO `en-GB`, canonical, sitemap, acessibilidade e desempenho. **Até à data esses testes ainda NÃO ocorreram e nenhuma base foi copiada.** Para mapa, Pagefind/Leaflet apenas se necessário; a pesquisa interna não é busca em inventário ao vivo de hotéis.

**Experiência proposta:** homepage `Explore the Algarve` → cinco cartões de serviços → destinos principais → guias locais → links afiliados quando autorizados. Páginas `/destinations/faro/`, `/destinations/vilamoura/`, `/destinations/quinta-do-lago/`, etc. Páginas canónicas `/villas-apartments/`, `/hotels-resorts/`, `/holidays-cruises/`, `/tours-activities/`, `/airport-transfers/`.

**Arquitetura essencial para não perder SEO:** manter `categories`, `destinations`, `partners` separados no código. O CTA resolve `category -> activePartner -> approvedTrackingLink`; a troca do parceiro **não altera a URL editorial**.

**Exemplos reais consultados como inspiração editorial e UX:** Algarve Local Guide, VisitAlgarve.co.uk, AlgarExperience, AlgarveWays e Visit Portugal. Não copiar textos, código, fotografias, logos ou designs protegidos. Ver ficheiros de benchmark.

## 5. O que realmente existe hoje (não confundir com site construído)

| Área | Estado em 19/11/2026 |
|---|---|
| GitHub `martaxi-boss/Holidays-site` | Existe; documentação guardada |
| Decisão de 5 categorias/4 parceiros | Fechada e documentada |
| Matriz Awin, termos e alternativas | Pesquisa documentada; candidatos **não aderidos** |
| Estratégia Algarve/UK, localidades, SEO e calendário | Documentada; não é auditoria de procura real |
| Templates GitHub e sites reais de referência | Estudados e guardados |
| Blueprint da UI e modelos de dados | Especificado; não programado |
| Código do website / clone do template | **Não iniciado** |
| Marca/domínio próprio | **Por definir** |
| Deploy/VPS | **Não iniciado** |
| Site público/Google Search Console | **Não iniciado** |
| Visitas reais, cliques afiliados e conversões | **Sem dados do novo projeto** |
| Candidaturas/links oficiais Awin | **Não iniciados** |

**Importante:** 'documentação guardada no GitHub' é prova de planeamento, não de implementação, aprovação, indexação ou receita.

## 6. Ordem de execução na próxima sessão — sem voltar à fase da ideia

1. **Ler este handoff + BOOTSTRAP + DECISAO_TECNICA + BLUEPRINT + PARTNERS_AWIN.** Confirmar a árvore atual do repositório.
2. **Testar a base MasuRii isoladamente**, com licença MIT e commit pinado: build, lint, QA de dependências, SEO e experiência de destinos. Se o custo de simplificação for excessivo, fallback Bookworm; escolher uma única base.
3. **Preparar primeira versão Algarve em `en-GB`**: cinco categorias, quatro parceiros ainda em estado não aderido, homepage sem marcas enganadoras, destinos prioritários e páginas legais, conteúdo útil original.
4. **Escolher marca/domínio e deploy** com autorização própria; seguir GitHub Actions → SSH/VPS em pasta isolada do projeto caso se use a infraestrutura já existente. Não alterar Low Cost Europa ou outros projetos.
5. **Lançar páginas reais, configurar Search Console/sitemap e analytics** com privacidade adequada. Não afirmar indexação com base apenas em sitemap submetido.
6. **Registar novo site como espaço promocional na conta Awin e candidatar os parceiros**, verificando UK/idioma/Algarve. Só ativar CTA monetizado com aprovação e deep link de tracking oficial.
7. **Medir por categoria, localidade e parceiro**: impressões e cliques Google UK; cliques de saída; cliques reconhecidos Awin; vendas pendentes/aprovadas/rejeitadas; comissões pagáveis. Comparar tracking e substituir parceiro se dados justificarem.
8. **Expandir gradualmente localidades** e melhorar SEO para verão de 2027, preservando páginas e decisões.

**Se não houver parceria aprovada no lançamento:** deixar a página editorial útil e sem CTA falsamente afiliado, prosseguindo SEO técnico e candidaturas. O proprietário prefere lançar/medir a paralisar.

## 7. Guardrails do proprietário e do projeto

- **Novo repositório independente e pasta VPS isolada.** Não misturar com Low Cost Europa, projetos de SEO anteriores, comparadores ou sex shop.
- Não instalar ferramentas globalmente nem inventar novas pontes SSH/agentes residentes. Evitar APIs pagas.
- Não comprar domínio, publicar site, candidatar parceiros ou alterar DNS automaticamente só porque há documentação — são trabalhos seguintes.
- Não guardar secrets, tokens ou dados privados no repositório público.
- Não usar fake clicks, cookie stuffing, reservas fictícias, avaliações falsas, preços/descontos inventados, scraping não autorizado, ou conteúdo protegido.
- Transparência de publicidade afiliada, privacidade/cookies e validação do enquadramento legal.
- Não alterar as **5 categorias, 4 parceiros, Algarve-only, UK/en-GB** sem instrução explícita. Diferenciar decisões fechadas de recomendações técnicas ainda sujeitas a QA.
- Atualizar este handoff **sempre que uma decisão material mudar**, com data/razão e ligação ao commit e testes.

## 8. Índice canónico — todos os documentos que importam

| Documento | Fonte de verdade para |
|---|---|
| [BOOTSTRAP.md](BOOTSTRAP.md) | Missão, decisões comerciais, princípios, âmbito, continuidade |
| [docs/PARTNERS_AWIN.md](docs/PARTNERS_AWIN.md) | 4 parceiros/5 categorias, contratos, IDs, atribuição, backups e trocas |
| [docs/SEO_ALGARVE_2027.md](docs/SEO_ALGARVE_2027.md) | Localidades, conteúdo, keywords a investigar, Search Console e calendário |
| [docs/EXECUTION_PLAN.md](docs/EXECUTION_PLAN.md) | Checklist de implementação, testes, deploy, tracking e lançamento |
| [docs/GITHUB_PUBLIC_REFERENCES.md](docs/GITHUB_PUBLIC_REFERENCES.md) | Templates e ferramentas públicas, licenças, demos e riscos |
| [docs/DECISAO_TECNICA_2026.md](docs/DECISAO_TECNICA_2026.md) | Base Astro preferida, alternativa e análise de ficheiros e QA |
| [docs/REFERENCIAS_WEB_REAIS.md](docs/REFERENCIAS_WEB_REAIS.md) | Referências reais de portais turísticos e navegação |
| [docs/BLUEPRINT_MVP_ALGARVE.md](docs/BLUEPRINT_MVP_ALGARVE.md) | Wireframe de homepage, UX, rotas, dados, CTAs e gates de qualidade |
| [README.md](README.md) | Entrada do repositório e ligações |

### Mudanças de estado (modelo)

| Data | O que mudou | Fonte / commit / prova | Impacto nas 5 categorias |
|---|---|---|---|
| 2026-11-19 | Consolidação de missão, estratégia, parceiros, bases GitHub, benchmark e blueprint | Documentos deste repositório | Nenhuma alteração; decisões preservadas |

**Regra de continuidade final:** quando o proprietário disser **“vamos construir o Holidays Site”**, começar pelo passo 1 da secção 6, depois executar e testar. **Não pedir novamente definições que já estão documentadas.** Reportar apenas bloqueios concretos e novas decisões indispensáveis.
