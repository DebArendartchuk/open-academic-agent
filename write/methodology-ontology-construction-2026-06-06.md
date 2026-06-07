---
segment: methodology
research-source: research/tipologia-pesquisa-ciencia-informacao-2026-05-05.md
status: pending
date: 2026-06-06
note: Draft parcial — contém apenas a subseção 3.5 PROCEDIMENTOS DE CONSTRUÇÃO DO ARTEFATO ONTOLÓGICO (com 3.5.1 a 3.5.4). Deve ser anexado ao final do conteúdo já commitado em build/paper.md para a seção methodology (após 3.4 Procedimentos de Coleta de Dados).
---

## 3.5 PROCEDIMENTOS DE CONSTRUÇÃO DO ARTEFATO ONTOLÓGICO

<!-- Seção secundária: MAIÚSCULA, sem negrito. -->

Os procedimentos de construção da ontologia proposta neste trabalho adotam a metodologia **OntoForInfoScience**, desenvolvida por Mendonça (2015) especificamente para a construção de ontologias por cientistas da informação. A escolha desta metodologia decorre de três fatores articulados: (i) sua origem disciplinar coincide com o campo de inserção desta pesquisa — Gestão da Informação / Ciência da Informação; (ii) sua estrutura sintetiza e incorpora elementos da METHONTOLOGY (FERNÁNDEZ *et al.*, 1997), do Método 101 (NOY; McGUINNESS, 2001) e da NeOn Methodology (SUÁREZ-FIGUEROA, 2008), oferecendo um arcabouço metodológico ancorado nas principais escolas de engenharia ontológica; e (iii) seu nível de detalhamento sobre os artefatos intermediários (glossários, dicionários, modelos conceituais) é especialmente adequado à formação acadêmica em Ciência da Informação. A METHONTOLOGY é citada como influência teórica direta da OntoForInfoScience, sem constituir, neste trabalho, metodologia de aplicação independente.

A OntoForInfoScience é composta por **nove etapas sequenciais** (numeradas de 0 a 8), cada uma com passos e artefatos definidos. A síntese das etapas, com indicação dos passos previstos por Mendonça (2015) e da forma de aplicação adotada nesta pesquisa, é apresentada no Quadro 8.

<!-- Quadro: título acima, fonte 10, centralizado, espaçamento simples. -->

Quadro 8 – Mapeamento das etapas da metodologia *OntoForInfoScience* aplicadas a este trabalho

| Etapa | Denominação (Mendonça, 2015) | Aplicação adotada neste trabalho |
|---|---|---|
| 0 | Avaliação da necessidade da ontologia | Necessidade justificada na seção 3.3, em razão da heterogeneidade semântica e da exigência de inferência sobre o ciclo de pedidos LAI — um tesauro não atenderia a demanda. |
| 1 | Especificação da ontologia | Preenchimento do *template* de especificação (Quadro 9) e definição das nove questões de competência (Quadro 10). |
| 2 | Aquisição e extração de conhecimento | Combinação de três métodos: análise manual e informal dos materiais de referência, análise da estrutura dos campos do FalaBR e extração terminológica computacional em RStudio. |
| 3 | Conceitualização | Produção do dicionário de conceitos, das tabelas de conceitos e propriedades, do dicionário de verbos e dos modelos conceituais gráficos. |
| 4 | Fundamentação ontológica | **Etapa simplificada** — adoção de ontologia leve *standalone*, sem herança formal de ontologia de fundamentação (ex.: BFO), em razão do escopo factível de um trabalho de conclusão de curso. Ontologias de fundamentação são citadas como referência teórica, sem incorporação estrutural. |
| 5 | Formalização da ontologia | Implementação no editor Protégé, em OWL 2 DL, com definição de classes, taxonomia, propriedades de dados e de objetos, axiomas e instâncias representativas. |
| 6 | Avaliação da ontologia | Triangulação de três técnicas: verificação automática de consistência pelo *reasoner* HermiT; validação semântica pela tradução das questões de competência em consultas SPARQL; e revisão qualitativa pelo orientador como especialista de domínio. |
| 7 | Documentação da ontologia | Documentação formal incorporada ao próprio TCC, complementada por apêndice digital com a listagem da ontologia em formato OWL. |
| 8 | Disponibilização da ontologia | Publicação do arquivo OWL em repositório público no GitHub, com URL persistente referenciada no apêndice. |

FONTE: A autora (2026), com base em Mendonça (2015).

As subseções seguintes detalham os procedimentos previstos para cada etapa, agrupadas conforme sua função no ciclo de desenvolvimento: especificação (3.5.1), aquisição e conceitualização (3.5.2), formalização (3.5.3) e avaliação, documentação e disponibilização (3.5.4).

### 3.5.1 Especificação da ontologia (Etapas 0 e 1)

<!-- Seção terciária: misto, sem negrito. -->

A Etapa 0 da OntoForInfoScience exige resposta explícita à questão preliminar sobre a real necessidade de uma ontologia para o problema investigado (MENDONÇA, 2015). Conforme demonstrado na seção 3.3, o domínio dos pedidos de acesso à informação pública no portal FalaBR apresenta três características que justificam a construção de uma ontologia, em vez de instrumentos terminológicos mais simples como tesauros ou vocabulários controlados: (i) a necessidade de **representação de relações extensíveis** entre conceitos do processo de transparência passiva, e não apenas a padronização de termos isolados; (ii) a necessidade de **inferência semântica** sobre o ciclo pedido–resposta–recurso, que demanda formalismo lógico; e (iii) o objetivo de viabilizar **interoperabilidade entre sistemas heterogêneos**, propósito típico das ontologias e estranho aos tesauros (MENDONÇA, 2015).

A Etapa 1 corresponde à formalização da especificação da ontologia, segundo o *template* proposto por Mendonça (2015) com sete elementos: domínio e escopo, propósito geral, classes de usuários, uso pretendido, tipo da ontologia, grau de formalidade e delimitação do escopo de cobertura. O preenchimento desses elementos para a ontologia proposta é apresentado no Quadro 9.

Quadro 9 – Especificação da ontologia proposta (*template* OntoForInfoScience)

| Elemento | Especificação adotada |
|---|---|
| **Domínio e escopo geral** | Processo de pedido de acesso à informação pública na modalidade de transparência passiva, conforme regulado pela Lei nº 12.527/2011 (BRASIL, 2011), com recorte operacional no portal FalaBR. Detalhamento do escopo na seção 3.3 (Quadro 3). |
| **Propósito geral** | Representar formalmente as entidades, propriedades e relações do processo de pedido LAI, de modo a (i) responder às questões de competência definidas no Quadro 10 mediante inferência sobre instâncias do FalaBR e (ii) servir como referência semântica para a interoperabilidade entre sistemas heterogêneos de transparência passiva no setor público brasileiro. |
| **Classes de usuários** | (a) Desenvolvedora — a pesquisadora e potenciais sucessores acadêmicos; (b) Usuários colaboradores — orientador e especialistas em Ciência da Informação, governo aberto e LAI; (c) Usuários leitores — comunidade acadêmica de Ciência da Informação e Gestão da Informação; (d) Usuários de aplicações derivadas — desenvolvedores de sistemas de transparência pública que venham a adotar a ontologia como referência. |
| **Uso pretendido** | Cenário 1: consultas SPARQL sobre uma base populada com instâncias extraídas do FalaBR (recorte 2025), como prova de conceito da capacidade descritiva e inferencial da ontologia. Cenário 2: referência semântica para o desenho de sistemas de transparência futuros, sustentando o argumento de interoperabilidade. |
| **Tipo da ontologia** | (i) Estrutura/nível: **ontologia de domínio**; (ii) Grau de formalidade: **ontologia com médio rigor formal**; (iii) Propósito de criação: **ontologia para sistemas de informação**. |
| **Grau de formalidade** | OWL 2 DL, com axiomas básicos suficientes para sustentar inferência sobre as questões de competência, sem adoção de lógica de primeira ordem completa. |
| **Delimitação do escopo de cobertura** | Ponto de partida: classes-núcleo do ciclo pedido–resposta–recurso. Limite do domínio coberto: atributos formais e relações do processo de transparência passiva, excluídos os elementos listados como fora do escopo no Quadro 3 da seção 3.3. Questões de competência: nove questões consolidadas no Quadro 10. |

FONTE: A autora (2026), com base em Mendonça (2015, p. 189).

As questões de competência (CQs) constituem o requisito funcional central da ontologia. Cada CQ define, simultaneamente, um critério de design — orientando a inclusão de classes, propriedades e relações necessárias — e um critério de validação, posteriormente traduzido em consulta SPARQL executada sobre a ontologia povoada (MENDONÇA, 2015). Para a ontologia proposta foram definidas nove questões de competência, organizadas em dois grupos: sete CQs **descritivo-analíticas**, focadas na capacidade da ontologia de responder consultas sobre o ciclo operacional de pedidos LAI, e duas CQs **estruturais**, focadas na capacidade de sustentar o argumento de interoperabilidade semântica entre sistemas heterogêneos. O conjunto consolidado é apresentado no Quadro 10.

Quadro 10 – Questões de competência da ontologia proposta

| # | Questão de competência | Grupo |
|---|---|---|
| QC1 | Quais órgãos receberam pedidos LAI no período investigado e em que volume? | Descritivo-analítica |
| QC2 | Qual a distribuição dos tipos de decisão (acesso concedido, negado, parcial, com sigilo) por órgão? | Descritivo-analítica |
| QC3 | Quais pedidos resultaram em recurso e em qual instância recursal? | Descritivo-analítica |
| QC4 | Qual o tempo médio entre o registro do pedido e a resposta por órgão e por categoria institucional? | Descritivo-analítica |
| QC5 | Quais pedidos extrapolaram o prazo legal de atendimento previsto no art. 11 da Lei nº 12.527/2011? | Descritivo-analítica |
| QC6 | Quais categorias temáticas (assunto e subassunto) concentram maior número de decisões de negativa? | Descritivo-analítica |
| QC7 | Qual a relação entre o tipo de decisão do pedido original e o tipo de resposta ao recurso correspondente? | Descritivo-analítica |
| QC8 | Quais classes, propriedades e relações mínimas qualquer sistema de registro de pedidos LAI deve implementar para ser interoperável com a ontologia proposta? | Estrutural — interoperabilidade |
| QC9 | Como mapear vocabulários divergentes de decisão (ex.: "acesso concedido" / "acesso integral" / "informação fornecida") presentes em diferentes sistemas para uma terminologia unificada sob a ontologia? | Estrutural — interoperabilidade |

FONTE: A autora (2026).

### 3.5.2 Aquisição de conhecimento e conceitualização (Etapas 2 e 3)

<!-- Seção terciária: misto, sem negrito. -->

A Etapa 2 da OntoForInfoScience compreende a aquisição e extração de conhecimento do domínio a partir de fontes de referência, com vistas à produção de três glossários — de conceitos, de verbos e de relações — que servem de insumo à conceitualização (MENDONÇA, 2015). Esta pesquisa combina, conforme orientação metodológica de Mendonça (2015, p. 192), três dos seis métodos previstos:

(i) **Análise manual e informal de textos** dos materiais de referência selecionados na seção 3.4.1, com foco em normas legais (Lei nº 12.527/2011 e Decreto nº 7.724/2012), padrões de interoperabilidade (ePING), ontologia preexistente (ONTOLAITP) e literatura científica recuperada no levantamento bibliográfico;

(ii) **Análise da estrutura dos campos do FalaBR**, descritos nos Quadros 5 e 6 da seção 3.4.2, considerando que os próprios campos da base operacional carregam terminologia consolidada do domínio (ex.: `Decisao`, `EspecificacaoDecisao`, `Instancia`, `TipoRecurso`), o que constitui fonte primária privilegiada de extração conceitual;

(iii) **Extração terminológica computacional** sobre os textos livres dos pedidos (`ResumoSolicitacao`, `DetalhamentoSolicitacao`, `Resposta`) e dos recursos (`DescRecurso`, `RespostaRecurso`), por meio dos pacotes `tidytext` e `quanteda` em ambiente RStudio, para identificação de termos recorrentes, *colocações* e *n-gramas* relevantes ao domínio.

A combinação dos três métodos produz três conjuntos de candidatos a termos da ontologia — análogos ao Pré-Glossário, ao Conjunto Manual e ao Conjunto Automático descritos por Mendonça (2015, p. 195, Figura 34). A unificação e separação desses conjuntos resulta nos três glossários (de conceitos, de verbos e de relações) que constituem o artefato final da Etapa 2.

A Etapa 3, de conceitualização, opera sobre os três glossários produzidos na Etapa 2 e produz quatro artefatos centrais (MENDONÇA, 2015): (a) **dicionário de conceitos**, que define cada conceito candidato a classe da ontologia; (b) **tabela de conceitos e propriedades**, que associa atributos a cada conceito; (c) **dicionário de verbos**, que define os verbos extraídos como relações ontológicas candidatas; e (d) **modelos conceituais gráficos**, que representam visualmente a estrutura proposta antes da formalização em OWL. Esses artefatos materializam o modelo conceitual do domínio e funcionam como ponte entre a extração terminológica e a formalização lógica, sendo apresentados na seção 4 (Resultados e Discussão) como produto da execução desta etapa.

### 3.5.3 Formalização da ontologia (Etapa 5)

<!-- Seção terciária: misto, sem negrito. -->

Conforme decisão metodológica registrada no Quadro 8, a Etapa 4 da OntoForInfoScience — fundamentação ontológica por adoção de ontologia de alto nível — é simplificada nesta pesquisa, em razão do escopo factível de um trabalho de conclusão de curso. A ontologia proposta classifica-se como *ontologia leve standalone*, sem herança estrutural formal de ontologias de fundamentação como a Basic Formal Ontology (BFO), utilizada pela ONTOLAITP (ISKO BRASIL, 2023). A literatura sobre ontologias de fundamentação é citada como referencial teórico na revisão (seção 2), mas não é incorporada como camada superior do modelo. Essa simplificação preserva a capacidade da ontologia de atender às questões de competência definidas, mantendo o rigor formal compatível com OWL 2 DL.

A Etapa 5, de formalização, é executada no editor **Protégé**, em sua versão *desktop* mais recente disponível ao tempo da pesquisa, que oferece interface gráfica para edição de ontologias OWL e integração nativa com *reasoners*. A linguagem de representação adotada é **OWL 2 DL** (*Description Logic*), perfil consolidado da família OWL 2 que combina expressividade lógica suficiente para axiomas de classe e propriedade com decidibilidade computacional — característica essencial para a execução de *reasoners* na Etapa 6.

Os passos previstos na Etapa 5, conforme Mendonça (2015, p. 187, Tabela 24), são executados na seguinte ordem na ontologia proposta: (i) construção da **taxonomia geral** a partir dos conceitos consolidados na Etapa 3; (ii) definição das **propriedades descritivas** das classes (rótulos, comentários, anotações); (iii) criação das **definições formais** das classes, com restrições lógicas quando aplicáveis; (iv) definição das **propriedades de dados** (*data properties*) das classes, com domínios e contradomínios tipados; (v) criação de **instâncias representativas** das classes, populadas com registros do FalaBR; (vi) especificação das **relações ontológicas** (*object properties*) entre classes; e (vii) definição das **propriedades das relações** (transitividade, simetria, inverso, quando aplicável).

### 3.5.4 Avaliação, documentação e disponibilização (Etapas 6, 7 e 8)

<!-- Seção terciária: misto, sem negrito. -->

A Etapa 6 corresponde à avaliação da ontologia construída. Adota-se uma estratégia de **triangulação de três técnicas** complementares de avaliação:

(i) **Verificação automática de consistência lógica**, executada pelo *reasoner* **HermiT**, integrado ao Protégé, com o objetivo de identificar inconsistências formais — classes insatisfazíveis, contradições entre axiomas e violações de restrições. A ontologia é considerada formalmente correta quando o *reasoner* retorna sem inconsistências.

(ii) **Validação semântica pelas questões de competência**, mediante tradução de cada uma das nove CQs do Quadro 10 em consultas SPARQL executadas sobre a ontologia povoada com instâncias do FalaBR. Considera-se a ontologia validada para uma CQ quando a consulta correspondente retorna a resposta esperada para o domínio. Os resultados das nove consultas são reportados na seção 4 (Resultados e Discussão).

(iii) **Revisão qualitativa por especialista de domínio**, conduzida com o orientador da pesquisa, com foco em três aspectos: adequação semântica da nomenclatura das classes e relações ao vocabulário consagrado do domínio LAI; suficiência da estrutura representacional para o propósito declarado; e clareza para usuários leitores de Ciência da Informação.

A Etapa 7, de documentação, é parcialmente incorporada ao próprio corpo do presente TCC: a descrição das classes, das relações principais e das decisões de modelagem é apresentada na seção 4 (Resultados e Discussão), enquanto a listagem completa em formato OWL, incluindo todos os elementos da ontologia formalizada, é disponibilizada como apêndice digital. A documentação produzida ao longo das Etapas 1 a 6 — especificação, glossários, dicionários, modelos conceituais e relatórios de avaliação — integra o anexo documental do TCC.

A Etapa 8, de disponibilização, opera pela publicação do arquivo OWL da ontologia em repositório público no **GitHub**, plataforma escolhida pela gratuidade, persistência da URL, versionamento automático e ampla adoção na comunidade acadêmica internacional para publicação de artefatos de pesquisa. A URL de acesso é referenciada no apêndice digital e nas Considerações Finais, viabilizando a continuidade da ontologia para futuras pesquisas e para potenciais adoções por sistemas de transparência pública.
