# BOOTSTRAP — Holidays Site / Algarve 2027

**Fonte de verdade do projeto** — decisões comerciais e técnicas resultantes da conversa de planeamento de 19 de novembro de 2026.  
**Estado à data:** projeto planeado; repositório criado pelo proprietário; documentação em preparação. **Nenhum site, domínio, deploy, conteúdo de produção ou parceria aprovada é declarado aqui.**  
**Owner:** proprietário do repositório `martaxi-boss/Holidays-site`.  
**Âmbito:** Algarve, Portugal; público britânico; site em inglês britânico (`en-GB`).  
**Objetivo:** começar antes do inverno de 2026/27 a captar sinais de SEO e estar comercialmente preparado para o verão de **2027**.

## 1. Missão e decisão central (não alterar sem decisão explícita)

Criar um **portal editorial/montra turística independente, especializado exclusivamente no Algarve**, onde um visitante (prioritariamente do Reino Unido) encontra ideias de férias e entra numa das **5 categorias comerciais**. Cada categoria encaminha para **um parceiro afiliado principal**, através de links de tracking autorizados pela Awin. Os parceiros pesquisam disponibilidade, executam a reserva, cobram ao cliente e prestam o serviço/atendimento.

**Não construir agência de viagens nem plataforma própria de checkout.** Não gerir hotéis, casas, motoristas, excursões, pedidos de clientes, inventário, pagamentos ou cancelamentos. A nossa atividade inicial é publicação de guias/curadoria editorial e encaminhamento afiliado, sujeito a validação jurídica do modelo concreto.

A tese de negócio é simples: conteúdo local útil + SEO de pesquisas britânicas específicas + navegação por **localidade e categoria** + clique afiliado para parceiro adequado + validação da comissão pela Awin. **Iniciar e medir é mais importante do que esperar pela perfeição de todos os parceiros.**

## 2. Decisão fechada: 5 categorias, 4 parceiros

| # | Categoria visível em inglês | O que o visitante procura | Parceiro principal planeado | Estado |
|---|---|---|---|---|
| 1 | **Villas & Apartments** | casas de férias, vivendas, apartamentos, holiday rentals | **Holidu UK** | não aderido / candidatura por apresentar |
| 2 | **Hotels & Resorts** | hotéis, resorts, alojamento hoteleiro | **Logitravel** (programa PT identificado) | não aderido / candidatura por apresentar |
| 3 | **Holidays & Cruises** | pacotes de férias, voo+hotel e cruzeiros relevantes para o mercado | **Logitravel** | não aderido / candidatura por apresentar |
| 4 | **Tours & Activities** | grutas de Benagil, barcos, golfinhos, excursões e experiências | **Viator UK** | não aderido / candidatura por apresentar |
| 5 | **Airport Transfers** | Faro Airport → localidades do Algarve, transfers privados/partilhados | **SunTransfers** | não aderido / candidatura por apresentar |

**A Logitravel é deliberadamente o único parceiro repetido:** atende duas categorias diferentes. **Uma categoria = um parceiro principal** na montra inicial; isso não obriga a cinco marcas diferentes. Os programas de backup ficam em reserva para substituição futura.

**Condição crítica da categoria 3:** o programa **Logitravel PT na Awin exclui voos isolados de comissão** segundo os termos consultados. Não anunciar que flights-only geram comissão. A experiência de venda para visitantes britânicos e o tracking transfronteiriço têm de ser confirmados antes de publicar CTA monetizado. Cruzeiros/pacotes devem manter pertinência com férias no Algarve; não abrir uma secção genérica mundial incompatível com o foco territorial.

## 3. Público, posicionamento e idioma

- **Público-alvo primário:** pessoas no Reino Unido a planear férias no Algarve; complementarmente, turistas britânicos já em Portugal a pesquisar atividades, transfers e alojamento.
- **Idioma:** todo o conteúdo comercial/editorial em inglês britânico (`en-GB`), com ortografia, termos e UX dirigidos ao Reino Unido.
- **Moeda na apresentação:** considerar GBP quando os dados/fornecedor permitirem; os valores de venda reais e eventuais câmbios são sempre os do parceiro. Nunca converter ou garantir preços sem fonte atualizada.
- **SEO:** procurar visibilidade no **Google UK**, sem assumir que alojar o site em Portugal ou usar `en-GB` restringe indexação exclusivamente ao Reino Unido. Search Console deve analisar resultados por país=United Kingdom e também tráfego de britânicos presentes fisicamente no Algarve.
- **Domínio:** por decidir (`.com` preferencial a avaliar). Não há compra nem registo autorizados por este bootstrap.
- **Marca comercial:** por definir; "Holidays Site" é o nome do repositório/projeto, não uma marca já aprovada. Não usar marcas de parceiros no domínio ou como se o portal fosse oficial deles.

## 4. Cobertura geográfica — Algarve inteiro

**Compromisso:** não excluir localidades menores. Criar arquitetura que suporte todos os destinos turísticos do Algarve, mas lançar em fases para evitar conteúdo vazio/duplicado.

- **Oeste/Costa Vicentina:** Aljezur, Burgau, Salema; acrescentar localidades próximas conforme procura real.
- **Barlavento:** Lagos, Alvor, Portimão, Praia da Rocha.
- **Centro e área de Loulé:** Albufeira, Armação de Pêra, **Vilamoura**, **Quinta do Lago** e arredores.
- **Sotavento:** **Faro (cidade e aeroporto)**, Olhão, Tavira, Manta Rota, Altura, Monte Gordo.
- Outras localidades do Algarve entram quando existirem pesquisa, informação útil e parceiros relevantes; a lista não é limite rígido.

**Destinos principais e prioridade editorial (a fasear por pesquisa de palavras-chave):** **Faro (cidade e aeroporto), Vilamoura e Quinta do Lago**, além de Albufeira, Lagos, Portimão/Praia da Rocha e Tavira. Estes três destinos foram explicitamente acrescentados pelo proprietário e **não são apenas pontos secundários**. Criar primeiro uma seleção de 10–15 páginas completas; publicar o restante núcleo prioritário nas primeiras ondas. Criar páginas para Aljezur/Burgau/Salema/Alvor/Armação de Pêra/Olhão/Manta Rota/Altura/Monte Gordo em ondas posteriores, **sem abandonar estas zonas**.

**Adenda do proprietário — 2026-11-19:** Faro (a cidade, não só o aeroporto), Vilamoura e Quinta do Lago integram o **grupo dos destinos turísticos principais** a destacar na navegação e no SEO, sem reduzir a cobertura já definida para o Algarve.

## 5. Experiência do utilizador e navegação

Homepage em inglês com:
1. Mensagem "Explore the Algarve" e promessa clara sobre férias no Algarve.
2. Cinco cartões grandes de categorias com descrições curtas, **um parceiro principal por cartão** (sem poluição visual nem dezenas de marcas).
3. Pesquisa/navegação por **localidade**; página própria da localidade com conteúdo original e atalhos para categorias adequadas.
4. Botões concretos: "Find villas", "Search hotels", "Explore holiday packages", "Book activities", "Book airport transfers".
5. Informações locais úteis: sazonalidade, acesso, praias, diferenças entre zonas, aeroporto, duração de passeios, recomendações verificáveis, perguntas frequentes.
6. Aviso de ligações de afiliado, políticas legais e respeito pelas normas de cada parceiro.

**Exemplo:** UK → "Villas & Apartments" → "Lagos" → link afiliado autorizado para pesquisa de alojamentos Lagos na Holidu UK. Se o turista continuar a pesquisar **dentro da Holidu** e reservar alojamento elegível, a venda **pode** gerar comissão se o tracking e as regras de atribuição forem cumpridos. **Nunca prometer que qualquer compra ou mera navegação rende comissão.**

### Rotas de site propostas (não implementadas)
- `/` — Algarve Holiday Guide.
- `/villas-apartments/`
- `/hotels-resorts/`
- `/holidays-cruises/`
- `/tours-activities/`
- `/airport-transfers/`
- `/destinations/faro/`, `/destinations/vilamoura/`, `/destinations/quinta-do-lago/`, `/destinations/albufeira/`, `/destinations/lagos/`, `/destinations/tavira/`, etc.
- Páginas específicas para intenção real, ex.: `/albufeira-boat-trips/`, `/faro-airport-to-lagos/`.
- Evitar criar todas as combinações categoria × localidade como páginas indexáveis sem conteúdo distintivo.

## 6. Parceiros Awin: estado e condições (snapshot, não garantia)

Existe conta Awin Publisher **Lowcost**. A consulta efetuada em 2026-11-19 identificou os programas relevantes como **"Not joined"**. Não afirmar afiliação aprovada; **nenhuma candidatura foi apresentada nesta fase**.

- **Holidu UK**: programa inglês e categoria de villas/apartamentos. Nota: na Awin tem aprovação histórica relativamente baixa; comissões limitadas a reservas elegíveis efetuadas diretamente na plataforma Holidu, e não redirecionadas a terceiros. O antigo modelo de **20 € por lead de proprietário** foi analisado para **Holidu ES & PT**, mas **não faz parte da monetização inicial do portal de turistas** nem pode ser assumido para o UK.
- **Logitravel PT**: programa para hotéis, pacotes e cruzeiros; **precisa confirmação escrita ou documental de atribuição/comissão quando o público é britânico e reserva alojamento/férias no Algarve**. Voos isolados excluídos no texto de termos PT consultado (documento antigo; reconfirmar).
- **Viator UK**: programa inglês, excursões/experiências, regras contra cópia de conteúdo, usos não autorizados de banners e publicidade paga direta. Exigir aprovação e link afiliado próprio; comissões sujeitas a excursão realizada.
- **SunTransfers (US, UK, ES)**: programa de transferências, útil para Faro Airport; verificar taxa aplicável e destino de links por localidade; comissão só após serviço elegível e validado.

Ver detalhes, métricas, exclusões e alternativas em [docs/PARTNERS_AWIN.md](docs/PARTNERS_AWIN.md).

## 7. Awin: tracking e comissões — regra financeira inegociável

**O que a Awin faz:** recebe o registo da conversão de um anunciante, processa estados (pendente → aprovada → pagável) e faz pagamentos ao Publisher quando as condições se verificam. Ter anunciantes de países diferentes na mesma conta é possível.

**O que NÃO está garantido:** não se recebe por clique isolado, por alguém vasculhar o site do parceiro, por qualquer item da loja, por venda fora da janela de atribuição, por cupão excluído, por ter havido outro afiliado no percurso, por mudança de dispositivo/canal, nem por cancelamentos/reembolsos. A duração e a regra de *last click* variam. Um parceiro pode não comissionar compras de serviços fora da sua categoria contratual.

**Implementação prevista:**
1. Aprovar o site em cada programa; consultar termos atuais e geografias elegíveis.
2. Gerar **links oficiais da Awin** e, se permitido, *deep links* para as páginas de busca/categorias das localidades.
3. Usar um identificador `clickref`/subID por categoria/localidade/campanha **permitido pelo anunciante e Awin**, sem alterar indevidamente URLs ou mascarar redirecionamentos.
4. Fazer testes reais de redirecionamento e contagem de cliques; validar os destinos no navegador/telemóvel, UK locale e HTTPS.
5. Comparar cliques locais, cliques atribuídos pela Awin, conversões pendentes, aprovadas, recusadas e comissões pagáveis.
6. Nunca afirmar que houve comissão sem conversão real registada/validada. Não fazer reservas falsas para testes.

**Muito importante:** compras efetuadas em parceiros diferentes são transações/atribuições independentes. Um clique na Holidu não dá crédito automático por uma compra na Viator ou Logitravel.

## 8. Política de substituição de parceiros (decisão do proprietário)

**Cada categoria é independente.** Se o parceiro:
- não admitir o site/mercado do Reino Unido;
- perder o tracking do link;
- gerar cliques mas pouca ou nenhuma conversão após uma amostra interpretável;
- rejeitar excessivamente comissões;
- pagar demasiado tarde / ficar em incumprimento; ou
- piorar o atendimento/experiência de reserva,

**o parceiro dessa categoria poderá ser substituído, sem mudar o resto do portal.** Manter conteúdo, rotas e SEO; trocar apenas configuração do parceiro e seus links, e medir novamente.

**Auditoria antes de substituir:** (a) a nossa página gera cliques? (b) Awin conta os cliques? (c) destino/geolocalização corretos? (d) condições da campanha e serviços excluídos? (e) há conversões pendentes em validação, sazonalidade ou tempos longos de viagem? (f) só depois comparar EPC real, taxa de aprovação e receitas.

Medições recomendadas: `clicks_out`, `awin_clicks`, `transactions_pending`, `transactions_approved`, `transactions_declined`, `commissions_payable`, `earnings_per_click`, `avg_validation_days`, país do público, dispositivo, categoria, localidade. Evitar decidir com 5–10 cliques ou com pagamentos ainda não maturados.

**Arquitetura:** `category -> partner_configuration -> awin_tracking_link` (um adaptador por categoria). A substituição nunca deve quebrar URLs editoriais indexadas. Guardar histórico de alterações com data e justificação. Ver [docs/PARTNERS_AWIN.md](docs/PARTNERS_AWIN.md).

## 9. SEO e aquisição para verão de 2027

- Prioridade **SEO orgânico**, técnico e editorial; não prometer ranking em 90 dias.
- Conteúdo `en-GB` original, útil e específico por destino/atividade; boas imagens com licença, dados verificados, títulos naturais, breadcrumbs, ligações internas e páginas rápidas para mobile.
- Google Search Console (propriedade verificada), sitemap XML, robots, canonical correto, indexação conferida por inspeção de URL; medir impressões e cliques por país=UK, página e consulta.
- Criar 10–15 páginas realmente boas primeiro; aumentar sem produção automática massiva nem copiar catálogos/descrições de parceiros.
- Pesquisar previamente volume/dificuldade/intenção no Reino Unido. Exemplos **hipotéticos**, não resultados de ferramentas: "best boat trips in Albufeira", "Benagil cave tours", "Faro airport to Lagos transfer", "Faro old town guide", "Vilamoura marina and golf", "Quinta do Lago family holidays", "family things to do in Tavira", "villas in Lagos Algarve".
- Construir reputação com referências genuínas; não comprar links nem criar redes artificiais de backlinks.
- Medição da conversão por categorias e parceiros; orçamento de publicidade **não decidido**.
- Planeamento detalhado: [docs/SEO_ALGARVE_2027.md](docs/SEO_ALGARVE_2027.md).

## 10. Calendário desejado

- **Nov–Dez 2026:** documentação e estudo de procura UK; escolher domínio e identidade; primeiras páginas e estrutura; termos legais; Awin/afiliações; deploy inicial quando autorizado.
- **Jan 2027:** ampliar conteúdos locais e ligações válidas; medir Search Console e tracking.
- **Fev–Mar 2027:** rever resultados dos primeiros ~90 dias, corrigir SEO técnico, melhorar páginas com impressões, avaliar parceiros e alargar destinos.
- **Abr–Jun 2027:** reforçar páginas com intenção de reserva; atualizar ligações, atividades, horários, disponibilidade e conteúdos para verão.
- **Verão 2027:** operação, otimização e substituições de parceiros conforme dados de conversão e validação.

**Meta realista dos três primeiros meses:** site funcional, indexável, medido e com primeiras impressões/cliques a analisar — não primeiro lugar garantido nem lucros garantidos.

## 11. Arquitetura técnica e isolamento

- Repositório exclusivo `martaxi-boss/Holidays-site`; não confundir com Low Cost Europa, Sevelora, sex shop, comparador ou projetos anteriores.
- Deploy a definir e documentar; se usar VPS, respeitar padrão existente **GitHub Actions → SSH → pasta isolada do projeto na VPS**, sem instalar aplicações globalmente por iniciativa própria. Não criar serviços/agentes residentes, segredos no GitHub público nem pontes SSH novas.
- Usar gerador estático/SSR rápido, de fácil manutenção e com SEO verificável; **framework não escolhido**, não impor stack neste bootstrap.
- Manter links e parceiros configuráveis, dados editoriais distintos dos URLs de afiliado; nunca armazenar tokens Awin no repositório público.
- Lighthouse/Core Web Vitals, desktop/mobile, acessibilidade, links, redirecionamentos, sitemap, analytics com consentimento aplicável e testes E2E antes de declarar publicação concluída.
- **Não criar site, abrir candidaturas, comprar domínio, instalar na VPS, alterar DNS ou publicar** apenas porque este plano foi arquivado. São futuras operações explícitas.

## 12. Legal, qualidade, marcas e privacidade

- Indicar claramente "This website contains affiliate links. We may earn a commission..." de modo inteligível e compatível com as regras do programa e publicidade.
- Política de privacidade, cookies/consentimento quando aplicável, contactos reais, termos do portal e acessibilidade.
- Respeitar regras Awin de uso de marcas, banners e *deep links*; não usar `Holidu`, `Viator` ou `Logitravel` de forma enganosa em domínio ou logótipo.
- Não apresentar disponibilidade/preços inventados; mostrar preços apenas se provenientes de feeds/APIs autorizados com atualização adequada.
- Confirmar enquadramento legal da afiliação turística e fronteira face à intermediação de viagens/serviços em Portugal/Reino Unido antes de novas funcionalidades.
- Não copiar texto/fotografia protegidos dos operadores; conteúdo local próprio e licenciado.

## 13. Decisões já tomadas vs. assuntos por fechar

**Decidido:**
- Portal exclusivamente sobre o Algarve, em inglês britânico, prioritariamente turistas UK.
- Cinco categorias e quatro parceiros planeados, com a Logitravel em duas categorias.
- Um parceiro principal por categoria; substituição individual por dados e tracking.
- Modelo editorial de links afiliados; parceiros tratam reservas/pagamentos.
- SEO e arranque com horizonte verão 2027, sem dependência de anúncios pagos.

**Em aberto (não inventar como resolvido):**
- Nome de marca, domínio e identidade visual.
- Aceitação/aprovação de todos os programas Awin e taxas contratualizadas.
- Logitravel PT: reservas por público britânico, idioma, atribuição e comissões.
- Holidu UK: remuneração exata aplicável a alojamentos do Algarve e cancelamentos/redirecionamentos.
- Viator UK/SunTransfers: campanhas elegíveis, percentagens exatas e links locais.
- Acesso a feeds e APIs, cobertura de todas as localidades, legal/compliance, stack, hospedagem e orçamento.
- Validação de pesquisa real no Google UK, datas de deploy e metas quantitativas baseadas em dados.

## 14. Reutilização e exemplos de GitHub público (pesquisa 2026-11-19)

Foi feita uma pesquisa de projetos **públicos de terceiros** para evitar criar toda a base de origem. A lista documentada está em [docs/GITHUB_PUBLIC_REFERENCES.md](docs/GITHUB_PUBLIC_REFERENCES.md), com links, demos, licenças e riscos. **Candidatos a protótipo:** MasuRii Travelblog (Astro, destinos, mapa, pesquisa; MIT) e Themefisher Bookworm Light Astro (base editorial e SEO; MIT); AstroPaper MIT é alternativa forte de conteúdo. Travello e Tourism Website servem como referências de apresentação. Pagefind, Leaflet e Lychee são funcionalidades pontuais.

**Decisão técnica RECOMENDADA para o primeiro protótipo (ainda sujeita a testes reais):** **Astro com páginas estáticas**, aproveitando [MasuRii Travelblog](https://github.com/MasuRii/travelblog-website-template) (MIT) como base inicial, com **Bookworm Light Astro** (MIT) como fallback. O código foi parcialmente inspecionado por ficheiros específicos; **não houve clone, build, teste de segurança ou publicação**. A recomendação e os critérios de aceitação estão em [docs/DECISAO_TECNICA_2026.md](docs/DECISAO_TECNICA_2026.md). Sites reais e ideias visuais em [docs/REFERENCIAS_WEB_REAIS.md](docs/REFERENCIAS_WEB_REAIS.md); modelo da homepage, cinco categorias, localidades e ligação afiliada em [docs/BLUEPRINT_MVP_ALGARVE.md](docs/BLUEPRINT_MVP_ALGARVE.md). Os repositórios de terceiros não têm autorização para alterar o âmbito comercial do projeto. Testar isoladamente, sem instalações globais nem fotografias sem licença.

## 15. Documentação e continuidade

| Documento | Função |
|---|---|
| [README.md](README.md) | Entrada e visão rápida |
| **BOOTSTRAP.md** | Fonte de verdade: decisões e princípios |
| [docs/PARTNERS_AWIN.md](docs/PARTNERS_AWIN.md) | Parceiros, métricas, termos e backups |
| [docs/SEO_ALGARVE_2027.md](docs/SEO_ALGARVE_2027.md) | Estratégia geográfica, conteúdo e SEO |
| [docs/EXECUTION_PLAN.md](docs/EXECUTION_PLAN.md) | Próximos passos, tarefas, QA e acompanhamento |
| [docs/GITHUB_PUBLIC_REFERENCES.md](docs/GITHUB_PUBLIC_REFERENCES.md) | Projetos de terceiros, demos e licenças |
| [docs/DECISAO_TECNICA_2026.md](docs/DECISAO_TECNICA_2026.md) | Escolha de base Astro para protótipo, mapeamento de código e gates |
| [docs/REFERENCIAS_WEB_REAIS.md](docs/REFERENCIAS_WEB_REAIS.md) | Benchmark de portais e sites reais do Algarve |
| [docs/BLUEPRINT_MVP_ALGARVE.md](docs/BLUEPRINT_MVP_ALGARVE.md) | Plano de UI/UX, páginas, dados, categorias e testes |

**Regra para futuros trabalhos:** ler estes ficheiros antes de começar; conservar a arquitetura comercial, **não alterar decisões já aprovadas sem pedido do proprietário**; acrescentar evidência nova e estado comprovado. A documentação de hoje é um **plano**, não um relatório de implementação.
