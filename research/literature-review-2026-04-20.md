---
title: Revisão Teórico-Empírica — LAI, FalaBR, Ontologias, Interoperabilidade Semântica e Governo Aberto
date: 2026-04-20
sources:
  - type: web
    ref: https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2011/lei/l12527.htm
  - type: web
    ref: https://revista.cgu.gov.br/Cadernos_CGU/article/view/471
  - type: web
    ref: https://falabr.cgu.gov.br/web/dadosabertoslai
  - type: web
    ref: https://transparencia-brasil.github.io/negativas-acesso-informacao-Executivo-federal-2021-1/6-comparativo-entre-bases-do-falabr.html
  - type: web
    ref: https://pt.wikipedia.org/wiki/Ontologia_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o)
  - type: web
    ref: https://ceur-ws.org/Vol-1301/ontocomodise2014_2.pdf
  - type: web
    ref: https://ceur-ws.org/Vol-3905/paper1.pdf
  - type: web
    ref: https://oa.upm.es/5484/1/METHONTOLOGY_.pdf
  - type: web
    ref: https://www.scielo.br/j/pci/a/hHMgryMtL7c9RJGNmgHWRRf/
  - type: web
    ref: https://eping.governoeletronico.gov.br/
  - type: web
    ref: https://www.w3.org/2006/07/SWD/SKOS/skos-and-owl/master.html
  - type: web
    ref: https://publicacoes.bad.pt/revistas/index.php/cadernos/article/view/2047
---

## Research Results

### 1. Lei de Acesso à Informação (LAI): fundamentos e escopo

A Lei nº 12.527, sancionada em 18 de novembro de 2011 e vigente a partir de 16 de maio de 2012, regulamenta o direito constitucional de acesso à informação pública no Brasil. O princípio central da LAI é a **publicidade como regra** e o sigilo como exceção: toda informação produzida ou custodiada pelo poder público é, a priori, pública, salvo disposição legal em contrário. Seu escopo abrange os três poderes nos âmbitos federal, estadual e municipal, incluindo autarquias, fundações, empresas públicas e sociedades de economia mista (BRASIL, 2011).

A LAI estabelece direitos dos cidadãos — como o de acessar informações e intervir em políticas públicas — e obrigações das instituições públicas, que devem responder a pedidos de acesso dentro de prazos definidos, disponibilizar ferramentas de busca e publicar ativamente informações de interesse coletivo. A lei é caracterizada pela literatura como "uma ferramenta básica para a interação entre sociedade e Estado", funcionando como mecanismo de controle social e combate à corrupção (CADERNOS CGU, 2017). Estudos do Senado Federal indicam que a LAI representa um marco na consolidação do Estado Democrático de Direito, alinhando o Brasil a padrões internacionais de transparência.

### 2. Portal FalaBR: plataforma, histórico e estrutura dos dados

O FalaBR — Plataforma Integrada de Ouvidoria e Acesso à Informação — é o sistema desenvolvido pela Controladoria-Geral da União (CGU) que integrou, a partir de agosto de 2020, as funcionalidades do e-SIC (Sistema Eletrônico do Serviço de Informação ao Cidadão), desativado naquele ano. A plataforma centraliza manifestações de ouvidoria (denúncias, elogios, reclamações, sugestões) e pedidos de acesso à informação do Poder Executivo Federal, disponibilizando registros históricos desde 2012.

O FalaBR mantém **duas bases de dados distintas** com características complementares:
- **Painel CGU (2012–2021):** dados agregados com metadados, sem conteúdo textual completo.
- **Base de Consulta de Pedidos e Respostas (2015–2021):** contém "campos de texto dos pedidos, das respostas e dos recursos completos".

Os campos disponíveis incluem, entre outros: `data_registro`, `data_resposta`, `orgao_destinatario` e `decisao`. Os pedidos são classificados em três categorias: (1) legítimas solicitações LAI; (2) perguntas duplicadas ou repetidas; e (3) manifestações que não constituem pedido de acesso à informação. Novos campos foram adicionados recentemente à plataforma, como "Detalhamento da Decisão", "Motivação para a negativa de acesso a informações pessoais" e "Prazo estimado de restrição (anos)" (TRANSPARÊNCIA BRASIL, 2021).

Análises comparativas das bases evidenciam discrepâncias temporais, de quantidade e de completude entre os registros, o que reforça a necessidade de padronização semântica dos dados para viabilizar análises integradas e monitoramento sistemático da lei.

### 3. Ontologias: definição, componentes e tipos

No contexto da Ciência da Informação e da Ciência da Computação, uma **ontologia** é um modelo de dados que representa um conjunto de conceitos pertencentes a um domínio e os relacionamentos entre esses conceitos. Ontologias fornecem especificações explícitas e formais de conceitualizações compartilhadas, permitindo que sistemas computacionais interpretem e realizem inferências sobre o conhecimento de forma sistemática. Sua aplicação permite transitar de sistemas de recuperação da informação baseados em correspondência de palavras-chave para sistemas de busca verdadeiramente semântica.

Os **componentes fundamentais** de uma ontologia são:
- **Indivíduos/Instâncias:** objetos básicos, concretos (pessoas, documentos, órgãos) ou abstratos (categorias, classificações).
- **Classes (Conceitos):** agrupamentos ou coleções de objetos que formam hierarquias.
- **Atributos/Propriedades:** características dos objetos, com nome e valor (ex.: `prazo_resposta: 20 dias`).
- **Relacionamentos:** conexões entre objetos; a relação "é-um" (hierarquia taxonômica) e "parte-de" são as mais comuns, além de relações específicas do domínio.

Quanto à **tipologia**, as ontologias classificam-se em: (a) **ontologias de domínio**, que modelam domínios específicos com terminologia especializada (ex.: administração pública, saúde); (b) **ontologias de alto nível (foundational/upper ontologies)**, que definem conceitos básicos extensíveis a múltiplos domínios (ex.: BFO, SUMO, OpenCyc); (c) **ontologias de tarefa**, que representam operações ou tarefas específicas; e (d) **ontologias de aplicação**, que capturam primitivos e restrições de sistemas particulares.

As ontologias são formalizadas em OWL (Web Ontology Language), linguagem recomendada pelo W3C construída sobre RDF e RDFS, que fornece representação semântica mais rica do que XML isolado. Entre as aplicações práticas estão: motores de busca semântica, construção automática de tesauros e vocabulários controlados, indexação automática de documentos e gestão do conhecimento organizacional.

### 4. Metodologias de construção de ontologias: SABiO e METHONTOLOGY

#### 4.1 SABiO — Systematic Approach for Building Ontologies

SABiO é uma metodologia sistemática para desenvolvimento de ontologias, proposta por Ricardo de Almeida Falbo (Universidade Federal do Espírito Santo — UFES) em 2014. A metodologia distingue entre **ontologias de referência** (modelos conceituais de um domínio, independentes de implementação) e **ontologias operacionais** (adaptadas para aplicações específicas). SABiO enfatiza a aquisição de conhecimento a partir de múltiplas fontes: especialistas do domínio, livros, normas internacionais e modelos de referência.

O processo SABiO organiza-se em **5 fases principais**:
1. **Identificação do propósito e elicitação de requisitos** — define as perguntas de competência (competency questions) que a ontologia deve responder.
2. **Captura da ontologia** — levantamento de conceitos, relações, propriedades e restrições do domínio.
3. **Formalização** — redação dos axiomas da ontologia em linguagem formal.
4. **Design** — estruturação e formalização da ontologia.
5. **Teste** — validação e verificação da ontologia contra os requisitos.

O SABiO conta ainda com **5 processos de suporte**: Aquisição de Conhecimento, Documentação, Gestão de Configuração, Reutilização e Avaliação.

Uma versão estendida — **SABiOx** — incorpora princípios ágeis, organizando o desenvolvimento em ciclos iterativos e incrementais com fases de Requisito, Configuração, Captura, Design e Implementação.

#### 4.2 METHONTOLOGY

METHONTOLOGY é uma das metodologias mais abrangentes para construção de ontologias, desenvolvida pela Universidade Politécnica de Madri (UPM), com raízes nos processos de engenharia de software IEEE. Adota um modelo de ciclo de vida baseado em prototipagem evolutiva e enfatiza a reutilização de ontologias existentes. É considerada independente de domínio e estruturada, sendo composta por atividades de gestão, desenvolvimento e suporte.

As **6 fases conceituais** do METHONTOLOGY são:
1. **Especificação** — produção de especificação formal ou semiformal usando perguntas de competência.
2. **Conceituação** — desenvolvimento do modelo conceitual do domínio.
3. **Formalização** — formalização do modelo conceitual.
4. **Integração** — incorporação de ontologias e componentes reutilizáveis.
5. **Implementação** — codificação em linguagem formal (OWL, Ontolingua, etc.).
6. **Manutenção** — atualizações e refinamentos contínuos.

As atividades de suporte paralelas incluem: Garantia de Qualidade, Gestão de Configuração, Documentação, Avaliação, Manutenção e Integração.

#### 4.3 Comparativo SABiO × METHONTOLOGY

| Aspecto | SABiO | METHONTOLOGY |
|---|---|---|
| Planejamento | Não explicitamente endereçado | Inclui atividades de gestão |
| Manutenção | Não abordada formalmente | Integrada ao ciclo de vida |
| Flexibilidade | Alta; adaptável a projetos ágeis | Estruturada e rigorosa |
| Foco | Ontologias de domínio (referência e operacional) | Independente de domínio |
| Contexto brasileiro | Amplamente citada na academia brasileira | Referência global; frequentemente adaptada |

SABiO é particularmente reconhecida no contexto acadêmico brasileiro; METHONTOLOGY é a referência global mais citada e adotada em projetos de maior escala.

### 5. Interoperabilidade semântica no governo eletrônico: ePING, OWL, SKOS e RDF

O **ePING** (Padrões de Interoperabilidade de Governo Eletrônico), framework do Governo Federal Brasileiro, estabelece premissas, políticas e especificações técnicas mínimas obrigatórias para o uso de TIC nos órgãos do Poder Executivo Federal. Estruturado em cinco segmentos — interconexão, segurança, meios de acesso, organização e intercâmbio de informações, e áreas de integração governamental —, o ePING determina explicitamente a adoção de ontologias e vocabulários controlados para promover interoperabilidade semântica entre sistemas governamentais.

As tecnologias semânticas previstas no ePING incluem:
- **RDF (Resource Description Framework):** para descrição de recursos e intercâmbio semântico de dados.
- **OWL (Web Ontology Language):** designado para definição de ontologias e representação rica de conhecimento.
- **SKOS (Simple Knowledge Organization System):** recomendado para gestão de vocabulários e sistemas de organização do conhecimento.
- **SPARQL:** em status "em estudo" para capacidades de consulta semântica.

O **SKOS** é um padrão W3C (publicado em 18 de agosto de 2009) construído sobre RDF e RDFS, com objetivo de viabilizar a publicação e uso de vocabulários como dados vinculados (linked data). SKOS conecta sistemas tradicionais de organização do conhecimento (tesauros, esquemas de classificação) à comunidade de dados abertos. A integração entre OWL e SKOS permite abordagens híbridas: OWL para estruturas formais e SKOS para hierarquias de conceitos navegáveis por humanos, possibilitando migração bidirecional entre diferentes níveis de formalidade.

A política da **Dimensão Semântica** do ePING alinha-se diretamente com a LAI ao determinar a adoção de "conceitos de Dados Abertos para orientar os processos de disponibilização de dados públicos" e priorizar transparência e disseminação de dados para viabilizar a interação efetiva entre governo e sociedade.

No contexto europeu, Portugal oferece um caso de referência com a **Plataforma CLAV** (desenvolvida pela Direção-Geral do Livro, dos Arquivos e das Bibliotecas — DGLAB), que disponibiliza dados em múltiplos formatos semânticos (RDF/OWL, SKOS, XML, CSV) por meio de API aberta, referenciada no catálogo europeu de ativos semânticos Joinup (CADERNOS BAD, 2019).

---

## Conclusion

A revisão teórico-empírica confirma que os cinco pilares da proposta — LAI, FalaBR, ontologias, metodologias de construção e interoperabilidade semântica — possuem literatura acadêmica e normativa suficiente para fundamentar o TCC. A LAI fornece o marco legal e o problema empírico (ausência de padronização operacional); o FalaBR fornece a base de dados com duas bases heterogêneas que evidenciam a fragmentação identificada no problema de pesquisa. Ontologias de domínio, construídas com SABiO ou METHONTOLOGY, são o instrumento conceitual adequado para formalizar os conceitos do processo LAI e habilitar integração semântica. O ePING fornece respaldo normativo direto à proposta, tornando a adoção de ontologias não apenas uma contribuição acadêmica, mas uma recomendação governamental já em vigor. A lacuna identificada — ausência de ontologia específica para integração operacional entre órgãos distintos — é confirmada pela pesquisa e posiciona este trabalho como contribuição original ao domínio.

---

## Cited Sources

- BRASIL. *Lei nº 12.527, de 18 de novembro de 2011 — Lei de Acesso à Informação*. <https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2011/lei/l12527.htm>
- CGU — Controladoria-Geral da União. *Cadernos Técnicos da CGU — Lei de Acesso à Informação como Mecanismo de Controle Social*. <https://revista.cgu.gov.br/Cadernos_CGU/article/view/471>
- CGU. *Dados Abertos LAI — Fala.BR*. <https://falabr.cgu.gov.br/web/dadosabertoslai>
- Transparência Brasil (2021). *Comparativo entre bases de dados do FalaBR*. <https://transparencia-brasil.github.io/negativas-acesso-informacao-Executivo-federal-2021-1/6-comparativo-entre-bases-do-falabr.html>
- Wikimedia Foundation. *Ontologia (Ciência da Computação)*. Wikipédia. <https://pt.wikipedia.org/wiki/Ontologia_(ci%C3%AAncia_da_computa%C3%A7%C3%A3o)>
- FALBO, Ricardo de Almeida (2014). *SABiO: Systematic Approach for Building Ontologies*. CEUR-WS, Vol. 1301. <https://ceur-ws.org/Vol-1301/ontocomodise2014_2.pdf>
- FALBO, Ricardo de Almeida et al. (2024). *SABiOx: The Extended Systematic Approach for Building Ontologies*. CEUR-WS, Vol. 3905. <https://ceur-ws.org/Vol-3905/paper1.pdf>
- GÓMEZ-PÉREZ, Asunción et al. *METHONTOLOGY: From Ontological Art Towards Ontological Engineering*. Universidade Politécnica de Madri. <https://oa.upm.es/5484/1/METHONTOLOGY_.pdf>
- SciELO Brasil. *Desenvolvimento de uma ontologia sobre componentes de ontologias*. Perspectivas em Ciência da Informação. <https://www.scielo.br/j/pci/a/hHMgryMtL7c9RJGNmgHWRRf/>
- Governo Federal do Brasil. *ePING — Padrões de Interoperabilidade de Governo Eletrônico*. <https://eping.governoeletronico.gov.br/>
- W3C (2009). *Using OWL and SKOS*. W3C Interest Group Note. <https://www.w3.org/2006/07/SWD/SKOS/skos-and-owl/master.html>
- CADERNOS BAD (2019). *Plataforma CLAV: Contributo para a Disponibilização de Dados Abertos da Administração Pública em Portugal*. <https://publicacoes.bad.pt/revistas/index.php/cadernos/article/view/2047>
