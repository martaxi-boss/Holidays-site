# Plano de execução e controlo — Holidays Site

**Data do planeamento:** 2026-11-19.  
**Status:** documentação; **nenhuma funcionalidade desenvolvida ou colocada online** por este trabalho.  
**Missão:** passar do planeamento para um portal Algarve-only, `en-GB`, medido, com 5 categorias / 4 parceiros Awin e preparado para verão 2027.

## 1. Contrato do produto (não desviar)

- [x] Foco geográfico definido: **todo o Algarve**, não um portal mundial.
- [x] Público definido: **Reino Unido**, site em inglês britânico.
- [x] Estrutura de monetização definida: **5 categorias, 4 parceiros**, **Logitravel nas categorias 2 e 3**.
- [x] Um parceiro principal por categoria; substituição futura por dados e elegibilidade.
- [x] Sem checkout próprio, pagamentos de clientes, reservas ou operações turísticas no nosso site.
- [x] Documentação inicial arquivada no GitHub.
- [ ] Nome comercial, domínio e identidade visual.
- [ ] Website funcional e publicado.
- [ ] Aprovação dos programas e tracking de produção.
- [ ] Indexação e dados reais de procura/SEO.
- [ ] Primeiras conversões/comissões reais.

Documentos vinculativos: [../BOOTSTRAP.md](../BOOTSTRAP.md), [PARTNERS_AWIN.md](PARTNERS_AWIN.md), [SEO_ALGARVE_2027.md](SEO_ALGARVE_2027.md).

## 2. Etapa A — Preparação sem complicar (primeiro sprint)

- [ ] Confirmar requisitos de conteúdo para UK e estudar SERPs concorrentes por Albufeira, Lagos, Portimão/Praia da Rocha, Tavira e Faro Airport.
- [ ] Criar lista de palavras-chave com procura/concorrência **reais e fontes datadas** (ainda não foi feita).
- [ ] Escolher marca e domínio, verificando disponibilidade antes de comprar.
- [ ] Selecionar stack simples e compatível com Google; evitar backend complexo antes de haver procura.
- [ ] Organizar conteúdo e configuração de parceiros separadamente para permitir troca de parceiro sem reescrever rotas.
- [ ] Preparar menu 5 categorias e menu localidade, com UX mobile/desktop e inglês britânico consistente.
- [ ] Preparar conteúdo editorial inicial, com dados locais verificados e imagens licenciadas.
- [ ] Criar páginas de privacidade, cookies se aplicável, transparência de links afiliados e contactos.
- [ ] Verificar enquadramento da atividade afiliação turística (sem checkout/intermediação própria).
- [ ] Documentar modelo de deploy e rollback; **não instalar ou alterar VPS/dns sem autorização operacional**.

**Aceitação Etapa A:** decisões implementáveis, conteúdo original pronto, arquitetura aprovada, sem dependências de parcerias ainda por aprovar.

## 3. Etapa B — MVP publicável

**Páginas mínimas:**
- [ ] Home `/` + cinco cartões de categorias
- [ ] `/villas-apartments/`
- [ ] `/hotels-resorts/`
- [ ] `/holidays-cruises/`
- [ ] `/tours-activities/`
- [ ] `/airport-transfers/`
- [ ] Albufeira, Lagos, Portimão/Praia da Rocha, Tavira
- [ ] Faro Airport transfers + 1 ou 2 rotas fortes
- [ ] Transparência publicitária, privacidade e contactos

**Qualidade mínima:**
- [ ] HTTPS e domínio final válidos.
- [ ] 200 nas páginas principais; 404 correta em rotas inexistentes; redirects previsíveis.
- [ ] Sitemap XML válido, robots.txt, canonical e metadata únicos.
- [ ] HTML `en-GB`, bom contraste, teclado, mobilidade e sem overflow mobile.
- [ ] Fotografias legais com `alt` descritivo e compressão.
- [ ] Links editoriais internos úteis, sem páginas duplicadas/geradas em massa.
- [ ] Botões para afiliados **só após adesão e validação de link**; alternativa editorial neutra até lá.
- [ ] Sem preço/disponibilidade fictícia, sem cópia não autorizada de inventário.
- [ ] Testes de navegação e cliques com provas em desktop e smartphone.
- [ ] Repositório consistente com deploy (commit e versão identificáveis).
- [ ] Documentar qualquer dependência, custo e necessidade de credenciais sem as publicar.

**Aceitação Etapa B:** um visitante pode entender o portal, explorar localidades/categorias e obter informação útil sem checkout nosso; funcionalidade real verificada em browser. Não chamar "lançado" a um build que só compila.

## 4. Etapa C — Awin e parceiros

**Conta de referência:** Awin Publisher Lowcost. Não abrir conta alternativa por cada categoria.

Para **cada um** de Holidu UK, Logitravel PT, Viator UK, SunTransfers:
- [ ] Registar o domínio como espaço promocional na conta Awin.
- [ ] Confirmar no programa Awin a geografia do público e dos serviços: UK → Portugal/Algarve.
- [ ] Confirmar linguagem `en-GB`, categoria elegível, taxa real, base de cálculo, cookie e prazo de pagamento.
- [ ] Ler termos específicos de publicidade (PPC/brand, criativos, newsletters, feeds).
- [ ] Apresentar candidatura no painel (guardar data, estado e respostas).
- [ ] Esperar aprovação **antes de apresentar links como monetizados**.
- [ ] Criar links Awin por categoria e, quando permitidos, *deep links* para a pesquisa/localidade.
- [ ] Testar redirects e link tracking em desktop/mobile.
- [ ] Registar cliques por categoria/localidade com `clickref` autorizado e evitar recolha de dados pessoais em IDs.
- [ ] Verificar eventual troca de domínio, redirecionamento externo e páginas não comissionáveis.
- [ ] Verificar na Awin a conversão/validação apenas quando houver reserva real elegível.

**Bloqueio principal:** Logitravel PT. Garantir adequação a tráfego britânico, idioma e serviços. Confirmado que voos isolados estão excluídos das comissões nos termos consultados, sujeitos a revisão atual.

**Aceitação Etapa C:** cada CTA ativo aponta para destino correto, o clique é registado e as condições são conhecidas. Atribuição de uma venda só se comprova por transação real atribuída e validada.

## 5. Etapa D — SEO e medição

- [ ] Verificar domínio correto no Search Console; sitemap aceite e acessível.
- [ ] URL Inspection nas URLs principais; acompanhar indexação sem confundir sitemap aceite com página indexada.
- [ ] Configurar métricas de `clicks_out` por `category`, `destination`, `partner`, data e campanha.
- [ ] Adicionar filtragem por país no Search Console para UK, sem ignorar visitantes britânicos fisicamente no Algarve.
- [ ] Analisar queries e páginas com impressões e melhorar conteúdos, títulos e ligações internas.
- [ ] Rever semanalmente erros técnicos e mensalmente SEO/performance.
- [ ] Acompanhar Awin: clicks, pending, approved, declined, payable e pagos.
- [ ] Separar analítica orgânica Google, tráfego social e publicidade.
- [ ] Medir resultados por categoria para comparações com futuros parceiros.

**Aceitação Etapa D:** relatório verificável com dados reais, sem números ou visitas inventadas.

## 6. Monitorização e troca de parceiro

**Regra do proprietário:** não ficamos presos a uma marca. Se a categoria recebe visitantes e envia cliques, mas o parceiro não atribui comissões ou oferece experiência inadequada, devemos **avaliar um substituto para aquela categoria apenas**.

### Ficha de saúde por categoria

| Campo | Definição |
|---|---|
| Categoria | uma das cinco categorias fixas |
| Partner ativo | nome e Awin ID |
| Estado de aprovação | notjoined / pending / joined / rejected / suspended |
| URLs testadas | home/category/deep link + dispositivo/localidade |
| Clicks_out | cliques registados no portal |
| Awin clicks | cliques atribuídos no programa |
| Pending sales | conversões ainda em validação |
| Approved / declined | vendas aprovadas / recusadas |
| Payable amount | comissões disponíveis para pagamento |
| EPC real do nosso portal | comissões atribuídas / cliques Awin, com moeda e período |
| Risco | cancelamentos, bloqueios, demora de validação, geografia, idioma |
| Próxima revisão | data + responsável |

### Critério de substituição proposto (não limiar absoluto)

1. Verificar se há tráfego qualificado suficiente para avaliar.
2. Se cliques de saída > 0 mas Awin clicks ~ 0: **corrigir link/tracking primeiro**.
3. Se ambos contam mas há poucas conversões: rever intenção, preços, destino, produto e sazonalidade.
4. Se as conversões estão pendentes de estadia/check-in: aguardar validação razoável antes de concluir que não há ganhos.
5. Se existe recusa sistemática, serviço excluído, mercado não aceite ou falha persistente: pesquisar parceiro alternativo daquela categoria.
6. Trocar apenas a configuração de parceiro e seus links; preservar conteúdos, URLs, SEO e métricas históricas.
7. Fazer novo QA completo das ligações, legal e analytics após a troca.

**Cadência inicial proposta:** revisão rápida aos 30 dias após ativação, revisão comparativa aos 60–90 dias ou quando houver amostra útil; aferir eventos de validação que podem exceder esse prazo. Não atribuir culpa ao parceiro sem evidência.

## 7. Logística e infraestrutura

O proprietário já utiliza GitHub e infraestrutura VPS com entrega por GitHub Actions → SSH. **Este projeto deve ser independente**, tanto no repositório como na pasta do servidor.

- [ ] Definir a forma de deploy deste novo repo; CI separado e sem afetar repositórios existentes.
- [ ] Nunca instalar dependências globais na VPS por iniciativa própria.
- [ ] Segredos em GitHub Actions secrets / configuração segura, nunca em Markdown, logs ou repo público.
- [ ] Ter rollback simples por versão/commit em caso de falha.
- [ ] Não ativar scraping recorrente nem armazenar catálogos/feeds sem permissão do parceiro.
- [ ] Avaliar manutenção periódica de links e conteúdos **apenas quando houver fluxo/infraestrutura reais**.
- [ ] QA automatizado para links quebrados, sitemap, HTML, sitemap e rotas; inspeção humana para conteúdo e relevância.

## 8. Calendário de trabalho

| Período | Produto esperado | Métrica de controlo |
|---|---|---|
| **19 Nov–Dez 2026** | documentação, escolha domínio, MVP e parceiros em candidatura | páginas publicadas, sitemap, GSC, testes de cliques |
| **Jan 2027** | ampliar destinos, validar links aprovados | primeiros dados de impressões/cliques UK |
| **Fev–Mar 2027** | otimizar conteúdo e conversão após meses de dados | SEO por página, click-through, Awin pending/approved |
| **Abr–Jun 2027** | fortalecer páginas para época alta e cobrir novas localidades | tráfego qualificado, reservas atribuídas, qualidade de links |
| **Verão 2027** | acompanhar e substituir parceiros quando justificado | comissões aprovadas/pagáveis, crescimento por categoria |

**Não há garantia de ranqueamento em três meses.** O compromisso é lançar cedo, instrumentar e melhorar com provas reais.

## 9. Notas de continuidade para o próximo ChatGPT/Codex/Work/Ferrari

1. Abrir [../BOOTSTRAP.md](../BOOTSTRAP.md) primeiro; respeitar a decisão **5 categorias / 4 parceiros / Logitravel em 2**.
2. Não confundir **documentado** com **implementado**. Neste arquivo ainda não há site, deploy ou candidaturas feitas.
3. Não construir novos projetos dentro do Low Cost Europa ou de outro repositório.
4. Antes de pedir nova decisão ao proprietário, consultar os documentos e verificar a conta Awin e GitHub reais.
5. Trabalhar progressivamente, com checklists verificadas, testes de browser reais e documentação de commits.
6. Não criar instalações globais nem mexer na VPS de outros projetos.
7. Alterações de decisões comerciais (categorias, parceiro principal, idioma, mercado, posicionamento) exigem pedido explícito.
8. Em caso de divergência, registrar mudança no histórico e atualizar os quatro documentos; não apagar a razão da decisão.
9. Se o projeto começar a funcionar com tráfego mas sem comissões, executar primeiro uma **auditoria de atribuição e elegibilidade**, depois comparar substitutos.

## 10. Histórico de alterações

| Data | Alteração | Estado |
|---|---|---|
| 2026-11-19 | Decidido Algarve-only, mercado UK, `en-GB` e cinco categorias | planeamento |
| 2026-11-19 | Selecionados Holidu UK, Logitravel (2 categorias), Viator UK e SunTransfers | candidatos; não aderidos |
| 2026-11-19 | Aprovada estratégia de um parceiro principal por categoria e substituição individual | planeamento |
| 2026-11-19 | Bootstrap inicial arquivado no repositório Holidays-site | documentação |

**Próxima atualização:** preencher o histórico com decisões comprovadas de domínio, site publicado, aprovação Awin, links e resultados — não adivinhar.
