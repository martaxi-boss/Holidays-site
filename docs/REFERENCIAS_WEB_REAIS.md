# Benchmark WEB REAL — portais do Algarve para estudar a experiência de utilização

**Investigação realizada:** 2026-11-19  
**Estado:** estudo de sites públicos, **não** cópia de código, texto, marcas, fotografias ou direitos.  
**Para quem:** futura equipa que vai implementar o Holidays Site, evitando desenhar a experiência completamente às cegas.  
**Âmbito do nosso produto:** **só Algarve**, `en-GB`, 5 categorias e 4 parceiros Awin.  
**Base GitHub recomendada:** [DECISAO_TECNICA_2026.md](DECISAO_TECNICA_2026.md).

## 1. Referências concretas de UX e concorrência

### 1.1 Algarve Local Guide — estrutura editorial e localidades

**Site:** https://algarvelocalguide.com/  
**Leitura web confirmada:** homepage com navegação **Towns, Beaches, Things to Do, Food & Drink, Plan Your Trip**, secção de destinos, divisão Western/Central/Eastern Algarve e páginas editoriais.  
**Ideias que podemos APRENDER (não copiar):**
- Dar resposta prática à pergunta "em que localidade do Algarve devo ficar?".
- Navegação por **zona** e **cidade**, não só ofertas comerciais.
- Guias que explicam para que tipo de turista cada destino serve.
- Informações como praia, acesso, alojamento, atividades e deslocação, com fontes verificáveis.
**A nossa diferença:** cinco categorias comerciais claramente identificadas e cliques afiliados medidos (Holidu/Logitravel/Viator/SunTransfers). Não copiar textos, contagens de praias ou frases promocionais do concorrente.

### 1.2 VisitAlgarve.co.uk — hero e experiência orientada para o Reino Unido

**Site:** https://www.visitalgarve.co.uk/  
**Evidência:** o motor de pesquisa encontrou uma **imagem de apresentação** com hero fotográfico, zona de pesquisa, navegação Explore/Itineraries/Map e um assistente de perguntas sobre o Algarve. A abertura de HTML em texto não devolveu conteúdo legível, logo **não foi feita auditoria funcional completa**.
**Inspiração:** hero de grande qualidade, busca de destinos em inglês, entrada simples para explorar.
**O que NÃO copiar:** o conceito de AI concierge. Não precisamos de chatbot, modelos pagos ou pesquisas abertas na primeira versão; acrescentariam custos e distrações sem receita demonstrada.

### 1.3 AlgarExperience — apresentação de atividades que as pessoas podem reservar

**Site:** https://algarexperience.com/en/  
**Página de atividades:** https://algarexperience.com/en/algarexperience-experiences/  
**Página local:** https://algarexperience.com/en/algarexperience-experiences/albufeira-experiences/  
**Evidência:** páginas públicas acessíveis por pesquisa mostram cartões concretos por atividade — Benagil, golfinhos, passeios, sunset —, pontos de partida e botões de reserva.  
**Inspiração:** títulos claros, cartões de experiências, identificação da localidade de partida, duração/cancelamento quando confirmado.
**Diferença importante:** AlgarExperience **é operador direto**, enquanto o Holidays Site será um **portal editorial afiliado**. Não usar preços, fotografias, disponibilidade ou material do operador sem autorização. Os nossos botões vão para **Viator UK**, não para um checkout próprio ou para operadores não aderidos.

### 1.4 AlgarveWays — guias de planeamento com intenção de compra

**Site:** https://algarveways.com/blog/  
**Evidência:** biblioteca de guias sobre "getting there", Faro Airport transfers, car hire, when to go, budget, where to stay e férias em família.
**Inspiração:** perguntas reais do turista britânico antes de comprar. Criar artigos que ajudam a escolher onde ficar, como se deslocar e quais as excursões adequadas ao seu perfil.
**A nossa diferenciação:** direcionar para as cinco categorias e para links de afiliado autorizados, mantendo informação original e neutralidade editorial.

### 1.5 Visit Portugal (fonte oficial) — validação geográfica e factual

**Portal oficial:** https://www.visitportugal.com/en/destinos/algarve  
**Uso correto:** confirmar pontos de interesse, características de regiões, roteiros e dados turísticos, com atribuições quando necessárias.
**O que NÃO fazer:** copiar texto editorial/fotografias ou afirmar parcerias com Turismo de Portugal. Fonte informativa não é licença de reutilização.
**O que traz ao nosso site:** credibilidade das explicações sobre Faro, Lagos, Tavira, Ria Formosa, praias, golf, interior e Costa Vicentina.

### 1.6 JO&SO — referência de apresentação de hotéis e resorts

**Exemplo visual:** https://www.awwwards.com/inspiration/jo-so-hotels-in-portugal-jo-so-2  
**Evidência:** grelha editorial de hotéis do Algarve com fotografias, nomes, pequenas descrições e etiquetas.
**Inspiração:** páginas de hotéis e resorts em grelha elegante, imagens de boa qualidade, títulos legíveis, CTA associado a uma categoria.
**Limite:** **não copiar** design gráfico, logos, fotografias, cards nem conteúdo protegido; criar a nossa identidade e usar imagens licenciadas.

### 1.7 Algarve Circle — inspiração de diretório regional

**Site:** https://algarvecircle.com/  
**Evidência:** resultado web descreve diretório regional com locais onde ficar, o que fazer, serviços e outras empresas.  
**Inspiração:** arquitetura regional com entradas por assunto e lugar.
**Diferenciação:** não criar um diretório infinito de restaurantes e serviços, porque a decisão do proprietário é só **5 categorias comerciais**.

## 2. Qual a combinação visual com mais sentido?

Não replicar nenhum destes sites. A proposta é combinar:

1. **Homepage limpa de portal turístico** (hero e pesquisa por localidade, inspiração VisitAlgarve.co.uk).
2. **Guia por localidades/zona** (inspiração Algarve Local Guide).
3. **Cinco cartões comerciais grandes** (nosso produto próprio e decisão comercial já fechada).
4. **Cartões editoriais de atividades relevantes** (inspirado na clareza da AlgarExperience, mas sem copiar ofertas).
5. **Guias para tirar dúvidas e melhorar SEO** (ideia editorial semelhante à AlgarveWays).
6. **Fontes factuais verificadas** (Turismo de Portugal e fontes locais), sem cópia de obras de terceiros.

**O nosso diferencial não é inventário ou preços próprios:** é ajudar britânicos a escolher o destino/serviço no Algarve e encaminhar para um único parceiro por categoria.

## 3. Estrutura recomendada da homepage (desktop)

```text
[LOGOTIPO PRÓPRIO]   Destinations   Holiday Services   Guides   About
-------------------------------------------------------------------
FOTOGRAFIA LICENCIADA DO ALGARVE (imagem optimizada)
           Discover the Algarve, your way
      Villas, hotels, experiences and transfers
       [Choose an Algarve destination ▾]  [Explore]
-------------------------------------------------------------------
                     PLAN YOUR HOLIDAY
 [1 Villas & Apartments] [2 Hotels & Resorts] [3 Holidays & Cruises]
       [4 Tours & Activities] [5 Airport Transfers]
-------------------------------------------------------------------
                    EXPLORE BY DESTINATION
  Faro | Vilamoura | Quinta do Lago | Albufeira | Lagos | Portimão
  Praia da Rocha | Tavira | West Algarve | East Algarve | All places
-------------------------------------------------------------------
                USEFUL LOCAL GUIDES
   Faro Airport transfers | Benagil boat trips | Where to stay
-------------------------------------------------------------------
How it works (research here -> book securely with partner)
Affiliate disclosure | About | Contact | Privacy | Terms
```

No **telemóvel**: hero pequeno, **5 cartões numa coluna ou grelha de 2** conforme legibilidade, localidades em cartões horizontais, menus acessíveis, sem popups e com CTA não enganador.

## 4. Estrutura da página de localidade

Exemplo hipotético `/destinations/vilamoura/`:

- H1: **Vilamoura, Algarve — Holiday Guide**.
- Resumo original em inglês britânico: perfil do visitante, localização, praias, marina/golfe quando factual e útil.
- Como chegar do Aeroporto de Faro, com informação verificada.
- Quatro a cinco atalhos **contextuais** para as categorias existentes; cada categoria preserva o seu parceiro:
  - Villas & Apartments → Holidu UK.
  - Hotels & Resorts → Logitravel (se programa/mercado compatível).
  - Holidays & Cruises → Logitravel (apenas ofertas elegíveis e relevantes).
  - Tours & Activities → Viator UK.
  - Airport Transfers → SunTransfers.
- Links internos para Faro, Albufeira, Quinta do Lago e outras localidades vizinhas quando relevante.
- FAQ original e links para guias mais profundos.
- Transparência de afiliação e fonte/atualização do conteúdo.

**Não preencher todas as categorias com links artificiais:** se um parceiro não tiver ofertas pertinentes naquela localidade, a página explica a limitação e prioriza informação útil.

## 5. Navegação das cinco categorias

| Categoria | Pergunta que resolvemos | CTA de destino quando aprovado |
|---|---|---|
| Villas & Apartments | Where can I find a holiday villa or apartment in the Algarve? | Search holiday rentals |
| Hotels & Resorts | Which hotel or resort area suits my holiday? | Explore hotels |
| Holidays & Cruises | What holiday packages or cruise options are relevant? | Explore holiday packages |
| Tours & Activities | What can I do near my accommodation? | Browse Algarve experiences |
| Airport Transfers | How do I get from Faro Airport to my destination? | Search airport transfers |

**Regra comercial:** Logitravel ocupa duas categorias. Os voos isolados constam como **não comissionáveis** nos termos Awin PT consultados; não anunciar voos isolados como receita garantida. O programa PT ainda precisa de validação para público britânico.

## 6. Diferenciação editorial/SEO face a sites existentes

- `en-GB` escrito por/para turista britânico, sem mistura de variantes.
- **Uma região bem coberta**, não 50 destinos internacionais genéricos.
- Incluir **Faro (cidade, não apenas aeroporto), Vilamoura e Quinta do Lago** como prioridades.
- Estender a Aljezur, Burgau, Salema, Lagos, Alvor, Portimão, Praia da Rocha, Albufeira, Armação de Pêra, Olhão, Tavira, Manta Rota, Altura, Monte Gordo e mais localidades com valor real.
- Guias com experiência e informação local verificáveis, não artigos produzidos em massa trocando nomes de cidades.
- **Não tentar vencer concorrentes replicando-lhes texto e títulos**. Conteúdos devem responder perguntas concretas com informação única.
- A Google recomenda conteúdo feito para pessoas: https://developers.google.com/search/docs/fundamentals/creating-helpful-content
- Critérios contra geração massiva de páginas sem valor: https://developers.google.com/search/docs/essentials/spam-policies

## 7. O que esta pesquisa web NÃO provou

- Não há dados reais de Search Console / tráfego orgânico destes concorrentes.
- Não foram medidos rankings, procura de palavras-chave no UK ou conversões de qualquer site concorrente.
- Não houve teste completo do funcionamento mobile e formulários dos sites; algumas páginas impediram leitura web.
- Não se pode concluir que qualquer layout acima seja livre para cópia. **Todos são referências visuais/editoriais apenas**.
- Os preços, avaliações e contagens de ofertas devem vir exclusivamente de fontes verificadas e autorizadas, se forem mostrados.

## 8. Portas de revisão antes do desenvolvimento

- Definir uma identidade visual própria (ver [BLUEPRINT_MVP_ALGARVE.md](BLUEPRINT_MVP_ALGARVE.md)).
- Adotar uma base técnica **MIT** após build e QA do [DECISAO_TECNICA_2026.md](DECISAO_TECNICA_2026.md).
- Confirmar direitos das fotografias e dados, se existirem.
- Verificar critérios SEO/relevância UK e regras Awin por categoria.
- Publicar apenas quando as páginas e a experiência de navegação funcionarem — sem checkout.

**Resultado do trabalho de 2026-11-19:** há **exemplos concretos** de conteúdo e UX; o próximo desenvolvimento **não precisa começar com uma página em branco**, mas não importa conteúdo protegido de concorrentes.
