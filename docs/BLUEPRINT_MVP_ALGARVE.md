# BLUEPRINT DO MVP — Holidays Site Algarve (implementação preparada)

**Versão do plano:** 2026-11-19  
**Estado:** especificação detalhada, **sem código web criado**.  
**Base proposta:** [MasuRii travelblog](https://github.com/MasuRii/travelblog-website-template) após testes; [Bookworm Astro](https://github.com/themefisher/bookworm-light-astro) como fallback.  
**Regras comerciais vinculativas:** [../BOOTSTRAP.md](../BOOTSTRAP.md); [PARTNERS_AWIN.md](PARTNERS_AWIN.md).  
**Mercado:** UK; `en-GB`. **Âmbito geográfico exclusivo:** Algarve. **Horizonte:** verão 2027.

## 1. Conceito funcional numa frase

> Um visitante britânico descobre **em que parte do Algarve ficar e o que fazer**, escolhe uma das cinco categorias do nosso site e clica num link de um **parceiro afiliado validado** para pesquisar/reservar no site desse parceiro.

**Não há preços, calendários, pagamento ou checkout próprios**. Não simular pesquisas aos inventários externos sem API autorizada.

## 2. Identidade visual proposta (ideia, não aprovada)

- Estilo: editorial turístico contemporâneo, limpo, premium mas acolhedor.
- Contraste e legibilidade prioritários; fundo claro com detalhes cor de areia e azul/verde do mar.
- Proposta de paleta para mockup: base `#FAFAF7` (quase branco), texto `#173447` (azul-escuro), mar `#075E69`, areia `#F3EBDE`, realce `#C36B45`. **Validar WCAG em todos os contrastes, especialmente CTA.**
- Tipografia: Inter ou outra fonte livre otimizada; uma fonte de títulos apenas se justificar o custo de performance.
- Fotografias licenciadas e reais do Algarve, redimensionadas, com alt text descritivo. Não reutilizar imagens do template das Filipinas.
- Cartões de parceiros com indicação discreta de afiliação e texto genuinamente explicativo; sem ostentação de logotipos oficiais não autorizados.
- Sem PWA, chatbot IA, animações pesadas, reviews fabricadas ou pop-ups na primeira versão.

## 3. Menu principal — navegação direta

```text
[Holidays Site / marca futura]   Destinations   Holiday Services   Algarve Guides   About

Destinations: Faro | Vilamoura | Quinta do Lago | Albufeira | Lagos |
              Portimão | Praia da Rocha | Tavira | View all Algarve

Holiday Services:
  1 Villas & Apartments
  2 Hotels & Resorts
  3 Holidays & Cruises
  4 Tours & Activities
  5 Airport Transfers
```

**Mobile:** menu hambúrguer acessível, destinos com pesquisa textual leve, cartões visíveis sem rolagem horizontal.

## 4. Homepage — estrutura final do primeiro protótipo

1. **Hero** com fotografia própria/licenciada e título "Discover the Algarve, your way". Subtítulo útil (holiday villas, hotels, activities and transfers in one regional guide).
2. **Explore Algarve destinations**: campo de pesquisa **local** por destino; autocomplete apenas para localidades de que temos páginas reais. Não chamar a isto pesquisa de hotéis ao vivo.
3. **Choose your holiday service**: **5 cartões** grandes, texto curto, ícone/imagem e link para página interna da categoria.
4. **Popular Algarve destinations**: Faro, Vilamoura, Quinta do Lago, Albufeira, Lagos, Portimão/Praia da Rocha, Tavira; acrescentar lugares menores progressivamente.
5. **West / Central / East Algarve**: 3 blocos com explicação da diferença entre zonas (conteúdo factual original).
6. **Useful Algarve guides**: Faro Airport, Benagil tours, travelling with children, Vilamoura vs Albufeira, etc. Só publicar guias efetivamente escritos e revistos.
7. **Como funciona**: "Explore our Algarve guide. Complete your booking securely with our travel partners." + transparência da afiliação.
8. **Rodapé**: About, Contact, Affiliate Disclosure, Privacy, Terms e ligações editoriais úteis.

## 5. Páginas por categoria — cinco e apenas cinco

| Rota canónica proposta | Label inglês britânico | Parceiro único configurado | CTA previsto após aprovação |
|---|---|---|---|
| `/villas-apartments/` | Villas & Apartments | Holidu UK `31469` | Search villas and apartments |
| `/hotels-resorts/` | Hotels & Resorts | Logitravel `11173` | Explore Algarve hotels |
| `/holidays-cruises/` | Holidays & Cruises | Logitravel `11173` | Explore holidays and cruises |
| `/tours-activities/` | Tours & Activities | Viator UK `7038` | Find Algarve experiences |
| `/airport-transfers/` | Airport Transfers | SunTransfers `111238` | Search Faro airport transfers |

**Logitravel em duas categorias intencionalmente.** Voos isolados não comissionáveis no programa PT consultado. O programa Logitravel PT ainda não foi validado para clientes britânicos; não ativar links até confirmação de elegibilidade e funcionalidade. Holidu UK só remunera reservas elegíveis realizadas diretamente no seu ecossistema, segundo termos consultados.

### Template de página de categoria

- Título natural e orientado para Algarve.
- Explicação do tipo de serviço, para quem se aplica e o que esperar.
- 3–6 localidades pertinentes com links internos para guias.
- Perguntas frequentes sem promessas de preços ou disponibilidade.
- Um CTA afiliado **apenas** se houver `partner.approved === true` e um link validado para destino real.
- Informação de reserva/cancelamento remetida ao operador, sem fazer promessas em seu nome.

## 6. Páginas por destino — estrutura uniforme, conteúdo diferente

Exemplo `/destinations/quinta-do-lago/`:
1. Hero + H1 único, `en-GB`.
2. Quem deverá escolher este destino e porquê, com fatos verificáveis.
3. Acesso do Aeroporto de Faro; como chegar ao local.
4. Tipo de alojamentos e resorts na área, sem inventário falso.
5. Atividades adequadas (golfe, natureza, passeios, etc., se confirmadas).
6. Cartões de **serviços disponíveis** vinculados às cinco categorias.
7. FAQ local, destinos vizinhos e guias relacionados.
8. Atualização editorial visível quando houve revisão real e fontes.

**Prioridades geográficas determinadas pelo proprietário:** Faro cidade/aeroporto, Vilamoura, Quinta do Lago, Albufeira, Lagos, Portimão/Praia da Rocha, Tavira.  
**Cobertura futura prevista:** Aljezur, Burgau, Salema, Alvor, Armação de Pêra, Olhão, Manta Rota, Altura, Monte Gordo, restantes localidades com páginas úteis e informação própria.

Não criar automaticamente todas as combinações `cidade × 5 categorias` como páginas indexáveis sem conteúdo único.

## 7. Modelo de dados proposto — para evitar refazer ao trocar parceiro

```ts
// ESPECIFICAÇÃO ilustrativa, NÃO código implantado.
type CategoryId =
  | "villas-apartments"
  | "hotels-resorts"
  | "holidays-cruises"
  | "tours-activities"
  | "airport-transfers";

type PartnerKey =
  | "holidu-uk"
  | "logitravel-pt"
  | "viator-uk"
  | "suntransfers";

interface Category {
  id: CategoryId;
  titleEnGB: string;
  summaryEnGB: string;
  slug: string;              // URL editorial estável
  activePartner: PartnerKey; // um e só um parceiro
}

interface Partner {
  key: PartnerKey;
  awinAdvertiserId: number;
  status: "notjoined" | "pending" | "joined" | "rejected" | "suspended";
  locale: "en-GB" | "pt-PT" | "other";
  ukVisitorsEligible: boolean | null;  // null = por confirmar
  algarveBookingsEligible: boolean | null;
  trackingUrl?: string;     // APENAS URL oficial aprovada
}

interface Destination {
  slug: string;
  name: string;
  zone: "west" | "central" | "east";
  coordinates?: { lat: number; lon: number }; // verificar
  introEnGB: string;        // conteúdo original
  services: CategoryId[];   // categorias relevantes no local
  guideSlugs: string[];
  photos: { src: string; alt: string; license: string }[];
}
```

**Observação:** `status: joined` **não implica automaticamente que qualquer destino/serviço seja comissionável**. Os CTAs dependem de elegibilidade real por operação. `trackingUrl` não deve ser inventada nem mascarada. Se o utilizador mudar de parceiro, guardar histórico de alterações e QA.

### Exemplo de identidade estável

```text
/destinations/faro/             -> nunca muda por troca de anunciante
/destinations/vilamoura/        -> nunca muda
/airport-transfers/            -> nunca muda
                           configuração partner: suntransfers
                           [se for substituído] partner: shuttle-direct
                           -> apenas o CTA e os termos são atualizados
```

## 8. Métricas incorporadas no projeto (mesmo sem vendas)

- `search_console_impressions_uk`, `search_console_clicks_uk`, `landing_page`.
- `outbound_clicks` por `category`, `destination`, `partner`, `date` e origem, sem identificadores pessoais.
- Awin `clicks` + `clickref` quando autorizado; `transactions_pending`, `approved`, `declined`, `payable`.
- Controlo de links válidos vs destino correto, com auditoria não intrusiva.
- **Nenhum clique significa venda garantida.** Acompanhamento da perda de tracking antes de trocar um parceiro.

Sem cookies de análise não necessários se não houver consentimento exigível; selecionar ferramenta de analítica com enquadramento de privacidade antes do lançamento.

## 9. Ordem das primeiras páginas

**Lote A: fundamento comercial/editorial**
- Home;
- cinco categorias;
- Faro cidade, Vilamoura, Quinta do Lago;
- Albufeira e Lagos;
- textos legais reais e disclaimer.

**Lote B: completar destinos principais e intenção comercial**
- Portimão, Praia da Rocha, Tavira;
- Faro Airport to Albufeira, Faro Airport to Lagos, Faro Airport to Vilamoura;
- Benagil Caves tours / Algarve boat trips, com conteúdo próprio.

**Lote C: expandir para todo o Algarve**
- Alvor, Armação de Pêra, Olhão, Aljezur, Burgau, Salema, Manta Rota, Altura, Monte Gordo, mais localidades após pesquisa de intenção UK.

O objetivo não é atingir um número artificial de URLs; cada página deve ter razões para existir sem depender do clique afiliado.

## 10. Fluxo futuro de criação (sem instalar agora)

| Ordem | Entrega real | Prova de aceitação |
|---:|---|---|
| 1 | Fixar versão MasuRii e testar isoladamente | MIT e dependências verificadas, `build`, `lint`, testes QA |
| 2 | Retirar demos/Philippines/reviews falsas/PWA/funcionalidades extras | sem conteúdo de demonstração, site rápido |
| 3 | Aplicar identidade Algarve `en-GB` e 5 categorias | homepage desktop/mobile aprovada |
| 4 | Criar modelo destino + parceiro substituível | testes garantem **5 categorias, 4 parceiros**, sem CTA não aprovado |
| 5 | Publicar páginas locais originais | conteúdo QA, direitos de imagens, sitemap/canonical |
| 6 | Configurar domínio/GSC/indexação | propriedade, sitemap, inspeções de URL reais |
| 7 | Aprovar Awin e testar links reais | conta e estados corretos, redirecionamentos e tracking |
| 8 | Medir visitas, cliques, transações | relatórios por categoria/localidade, substituição só com evidência |

**Infraestrutura:** novo repositório e pasta dedicados, modelo habitual de deploy GitHub Actions → SSH/VPS apenas quando autorizado; sem instalações globais, sem novos coordenadores, sem serviços pagos impostos.

## 11. QA obrigatório antes de apresentar como concluído

- [ ] Página inicial e todas as rotas prioritárias funcionam no navegador, desktop e Android.
- [ ] Cinco categorias visíveis; quatro parceiros diferentes, Logitravel repetida em duas.
- [ ] Todas as páginas `en-GB`; metadados, canonical, sitemap/robots, OpenGraph consistentes.
- [ ] Sem links quebrados, textos temporários, conteúdo Filipino ou imagens sem licença.
- [ ] Imagens legíveis e otimizadas, textos acessíveis, funcionamento do teclado.
- [ ] Sem checkout, preços inventados, avaliações falsas ou promessas de comissão.
- [ ] CTAs desligados enquanto programas não aprovados; depois tracking validado.
- [ ] Provas de build, testes e URLs publicadas com commit identificado.
- [ ] Search Console confirmado; cliques separados de vendas aprovadas.
- [ ] README, BOOTSTRAP e este blueprint sincronizados com o estado **real**.

## 12. Decisões fechadas e propostas por confirmar

**FECHADO pelo proprietário:** Algarve-only, inglês britânico, cinco categorias, quatro parceiros, Logitravel nas categorias 2 e 3, cada categoria com um parceiro principal, substituição quando tracking/comissões não funcionarem, horizonte verão 2027, projeto independente.

**PROPOSTO tecnicamente:** Astro estático, base MasuRii simplificada sujeita a testes; Bookworm como fallback; paleta visual, menu, arquitetura de páginas e modelo de dados descritos acima.

**AINDA POR VALIDAR:** nome/domínio, imagens, base após build, taxas e candidaturas Awin, elegibilidade UK, SERPs/volume de procura, custos e deploy.

**A documentação de hoje reduz decisões futuras, não finge que o site já foi construído.**
