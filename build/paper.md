<!-- SECTION:abstract -->
<!-- PENDING -->
<!-- /SECTION:abstract -->

<!-- SECTION:introduction -->
# 1 INTRODUÇÃO

<!-- Formatação ABNT: fonte Arial ou Times New Roman 12, espaçamento 1,5, recuo de parágrafo 1,5 cm -->

O acesso à informação pública constitui um direito fundamental em sociedades democráticas, sendo reconhecido como condição essencial para o exercício da cidadania, o controle social e a promoção da transparência governamental. No Brasil, esse direito foi regulamentado pela Lei nº 12.527, de 18 de novembro de 2011, conhecida como Lei de Acesso à Informação (LAI), que estabelece os princípios, prazos e procedimentos pelos quais qualquer pessoa pode solicitar informações a órgãos e entidades públicas da administração direta e indireta dos Poderes Executivo, Legislativo e Judiciário, em âmbito federal, estadual e municipal (BRASIL, 2011).

Para viabilizar o exercício desse direito em nível federal, a Controladoria-Geral da União (CGU) disponibiliza o portal FalaBR — Plataforma Integrada de Ouvidoria e Acesso à Informação —, que centraliza os registros de pedidos de acesso à informação do Poder Executivo Federal desde 2012. A plataforma oferece dados abertos em formatos CSV e XML, contemplando pedidos, respostas, recursos e informações sobre solicitantes, constituindo uma base empírica relevante para estudos sobre transparência pública e governança da informação no Brasil.

Não obstante a relevância da LAI e do FalaBR, identificam-se limitações estruturais que comprometem a efetividade do acesso à informação em âmbito nacional. A LAI estabelece diretrizes, prazos e procedimentos gerais, mas não cria um processo operacional padronizado nem um sistema integrado único para solicitação, gestão e monitoramento entre todos os órgãos públicos. Como resultado, persistem heterogeneidade de processos, inconsistência de dados, dificuldades de acompanhamento de indicadores — como concessões, negativas, prazos e recursos — e limitações de interoperabilidade entre os sistemas utilizados pelos diferentes entes federativos e órgãos públicos. Análises das bases de dados do FalaBR evidenciam essa fragmentação: coexistem bases com escopos temporais distintos, ausência de padronização semântica nos campos de dados e discrepâncias quantitativas entre registros, o que dificulta o acompanhamento sistemático do cumprimento da lei.

Diante desse contexto, emerge a seguinte pergunta de pesquisa: **como uma ontologia pode contribuir para a integração e padronização semântica dos dados de pedidos de acesso à informação pública no Brasil, a partir da base de dados do portal FalaBR e das diretrizes da LAI?**

O objetivo geral deste trabalho é propor uma ontologia para representação e integração de dados de pedidos de acesso à informação pública, com base na análise dos dados disponibilizados pelo portal FalaBR e nas diretrizes estabelecidas pela Lei de Acesso à Informação (Lei nº 12.527/2011).

Para o alcance deste objetivo, definem-se os seguintes objetivos específicos:

a) analisar a estrutura, os campos e as características dos dados de pedidos LAI disponibilizados pelo portal FalaBR;

b) identificar os principais conceitos, entidades e relações envolvidos no processo de solicitação, gestão e monitoramento de pedidos de acesso à informação pública;

c) revisar metodologias de construção de ontologias e trabalhos correlatos aplicados ao domínio de governo aberto, transparência pública e acesso à informação;

d) desenvolver uma proposta de ontologia para representação semântica e integração dos dados de pedidos LAI;

e) avaliar a aderência da ontologia proposta às diretrizes da LAI e aos padrões de interoperabilidade semântica do governo eletrônico brasileiro.

A relevância deste estudo justifica-se em três dimensões. Do ponto de vista da **importância**, a padronização semântica dos dados de pedidos LAI é condição necessária para que seja possível monitorar de forma sistemática o cumprimento da lei, comparar indicadores entre órgãos e identificar padrões de concessão e negativa de acesso à informação — questões de interesse direto para a sociedade civil, pesquisadores e gestores públicos. Quanto à **viabilidade**, a pesquisa encontra respaldo tanto em dados empíricos disponíveis publicamente — as bases abertas do FalaBR — quanto em metodologias consolidadas de construção de ontologias, como METHONTOLOGY, e em trabalhos acadêmicos anteriores que demonstram a aplicabilidade de ontologias ao domínio da transparência pública no Brasil. Sob a perspectiva da **oportunidade**, os Padrões de Interoperabilidade de Governo Eletrônico (ePING), editados pelo Governo Federal, já determinam explicitamente a adoção de ontologias e vocabulários controlados baseados em OWL, SKOS e RDF para promover interoperabilidade semântica entre sistemas governamentais — o que confere respaldo normativo direto à proposta. Além disso, a ausência de uma ontologia específica voltada à integração operacional de dados LAI entre órgãos distintos aponta para uma lacuna na literatura, que este trabalho busca contribuir para preencher.

Este trabalho está organizado da seguinte forma: o Capítulo 2 apresenta a revisão teórico-empírica, abordando os fundamentos da Lei de Acesso à Informação, as características da base de dados FalaBR, os conceitos e metodologias de construção de ontologias, e os padrões de interoperabilidade semântica no governo eletrônico brasileiro. O Capítulo 3 descreve os materiais e métodos empregados na pesquisa. O Capítulo 4 apresenta a proposta de ontologia e discute os resultados obtidos. Por fim, o Capítulo 5 traz as considerações finais e indicações de trabalhos futuros.
<!-- /SECTION:introduction -->

<!-- SECTION:literature-review -->
# 2 REVISÃO TEÓRICO-EMPÍRICA

<!-- Formatação ABNT: fonte Arial ou Times New Roman 12, espaçamento 1,5, recuo de parágrafo 1,5 cm. Seção primária: nova página, negrito + MAIÚSCULA. -->

Este capítulo apresenta os fundamentos teóricos e empíricos que sustentam a proposta de ontologia desenvolvida neste trabalho. Os pilares teóricos foram selecionados a partir dos objetivos específicos da pesquisa e abrangem: o marco legal e os mecanismos de transparência pública instituídos pela Lei de Acesso à Informação; a plataforma FalaBR e a estrutura dos seus dados abertos; os fundamentos conceituais e tipológicos das ontologias; as principais metodologias de construção de ontologias relevantes para o contexto brasileiro; e os padrões de interoperabilidade semântica no governo eletrônico.

## 2.1 TRANSPARÊNCIA PÚBLICA E LEI DE ACESSO À INFORMAÇÃO

<!-- Seção secundária: MAIÚSCULA, sem negrito. Nova página não obrigatória para secundária. -->

O direito de acesso à informação pública é reconhecido internacionalmente como um dos pilares dos regimes democráticos, na medida em que habilita o exercício do controle social sobre as ações do Estado e contribui para a prevenção da corrupção. No Brasil, esse direito, já previsto no artigo 5º da Constituição Federal de 1988, foi regulamentado pela Lei nº 12.527, sancionada em 18 de novembro de 2011 e vigente a partir de 16 de maio de 2012 — a chamada Lei de Acesso à Informação (LAI).

O princípio norteador da LAI é o da **publicidade como regra e o sigilo como exceção**: toda informação produzida, guardada ou administrada pelo poder público é, em regra, pública, sendo o sigilo admitido apenas nos casos expressamente previstos em lei. Em termos de escopo, a lei abrange os três poderes (Executivo, Legislativo e Judiciário) em todos os níveis federativos — União, estados, Distrito Federal e municípios —, além de autarquias, fundações, empresas públicas e sociedades de economia mista (BRASIL, 2011). Essa amplitude representa, por um lado, um avanço significativo em relação a legislações anteriores; por outro, impõe desafios consideráveis de implementação, pois pressupõe a capacidade técnica e operacional de centenas de órgãos com estruturas, sistemas e processos heterogêneos.

A CGU (Controladoria-Geral da União, 2017) caracteriza a LAI como "uma ferramenta básica para a interação entre sociedade e Estado", apontando seu papel como mecanismo de controle social e instrumento de combate à corrupção. Essa caracterização é pertinente, mas revela também uma tensão estrutural: embora a lei defina claramente o *que* deve ser feito — prazo de resposta, hipóteses de sigilo, procedimento de recurso —, ela não define o *como* operacional em nível técnico. A LAI não impõe um sistema nacional integrado, não padroniza formulários de solicitação, não especifica campos mínimos de dados nem define métricas comuns de cumprimento. Essa lacuna entre o direito declarado e a operacionalização técnica é o problema central que este trabalho busca endereçar.

## 2.2 PORTAL FALABR: PLATAFORMA E ESTRUTURA DOS DADOS

O FalaBR — Plataforma Integrada de Ouvidoria e Acesso à Informação — é o sistema desenvolvido pela CGU que, a partir de agosto de 2020, absorveu as funcionalidades do e-SIC (Sistema Eletrônico do Serviço de Informação ao Cidadão), desativado naquele mesmo ano. A plataforma centraliza tanto as manifestações de ouvidoria (denúncias, elogios, reclamações e sugestões) quanto os pedidos de acesso à informação do Poder Executivo Federal, mantendo registros históricos disponíveis em formatos abertos (CSV e XML) desde 2012 (CGU, [s.d.]).

Do ponto de vista da estrutura de dados, o FalaBR mantém **duas bases distintas com características complementares** e, ao mesmo tempo, problemáticas. A primeira é o Painel CGU, com cobertura de 2012 a 2021, contendo dados agregados e metadados, mas sem os textos completos dos pedidos e respostas. A segunda é a base de Consulta de Pedidos e Respostas, com cobertura de 2015 a 2021, que inclui o conteúdo textual integral das petições, respostas e recursos. Os campos disponíveis nas bases incluem, entre outros, `data_registro`, `data_resposta`, `orgao_destinatario` e `decisao`. Os pedidos são classificados em três categorias: (1) legítimas solicitações LAI; (2) perguntas duplicadas ou repetidas; e (3) manifestações que não constituem pedido de acesso à informação. Campos mais recentes, como "Detalhamento da Decisão" e "Motivação para a negativa de acesso a informações pessoais", foram adicionados em versões posteriores da plataforma (TRANSPARÊNCIA BRASIL, 2021).

A coexistência de duas bases com escopos temporais diferentes, níveis de completude distintos e categorias sem definição semântica formal evidencia o problema empírico central desta pesquisa. Análises comparativas das bases revelam discrepâncias quantitativas entre registros do mesmo período e órgão, indicando ausência de sincronização e de um modelo de dados compartilhado. Essa fragmentação não é uma falha isolada de implementação, mas reflexo direto da ausência de uma ontologia ou modelo semântico unificado que padroni­ze como os conceitos do processo LAI devem ser representados, relacionados e trocados entre sistemas.

## 2.3 ONTOLOGIAS: FUNDAMENTOS, COMPONENTES E TIPOLOGIA

O conceito de ontologia, originário da Filosofia como o estudo do ser e da existência, foi reapropriado pela Ciência da Informação e pela Ciência da Computação para designar representações formais e explícitas de conceitualizações compartilhadas de um domínio do conhecimento. Na acepção amplamente adotada na literatura de engenharia do conhecimento, uma ontologia é um modelo de dados que representa um conjunto de conceitos pertencentes a um domínio e os relacionamentos entre esses conceitos, fornecendo uma especificação formal que permite a interpretação e a inferência computacional sobre o conhecimento de forma sistemática (ALMEIDA; BAX, 2003).

Os **componentes fundamentais** de uma ontologia são: (a) **indivíduos** ou instâncias, que representam objetos concretos (ex.: um pedido de acesso à informação específico, um órgão público) ou abstratos (ex.: uma categoria de decisão); (b) **classes** ou conceitos, que agrupam indivíduos com características comuns e formam hierarquias taxonômicas; (c) **propriedades** ou atributos, que descrevem características dos objetos com nome e valor (ex.: `prazo_resposta: 20 dias`); e (d) **relacionamentos**, que expressam conexões entre objetos, sendo a relação "é-um" (*is-a*) — que estrutura taxonomias — e "parte-de" (*part-of*) as mais frequentes, além de relações específicas do domínio modelado.

Quanto à **tipologia**, a literatura identifica quatro categorias principais: (1) **ontologias de domínio**, que modelam domínios específicos com terminologia especializada, como administração pública, saúde ou direito; (2) **ontologias de alto nível** (*foundational* ou *upper ontologies*), que definem conceitos genéricos extensíveis a múltiplos domínios, como BFO (*Basic Formal Ontology*), SUMO e OpenCyc; (3) **ontologias de tarefa**, que representam operações ou processos específicos; e (4) **ontologias de aplicação**, que capturam primitivos e restrições de sistemas computacionais particulares. Para os fins deste trabalho, o tipo relevante é a **ontologia de domínio**, voltada à representação dos conceitos, entidades e relações do processo de solicitação e gestão de pedidos LAI.

As ontologias são formalizadas primariamente em OWL (*Web Ontology Language*), linguagem recomendada pelo W3C (*World Wide Web Consortium*), construída sobre RDF (*Resource Description Framework*) e RDFS, que fornece capacidade de representação semântica mais rica do que o XML isolado. A adoção de OWL viabiliza: motores de busca semântica, construção automática de tesauros e vocabulários controlados, indexação semântica de documentos e interoperabilidade entre sistemas heterogêneos por meio de inferência lógica.

É importante destacar que ontologias não são artefatos estáticos. A literatura aponta que uma ontologia representa "uma tentativa de capturar uma visão de mundo", e sua relevância depende de adoção pela comunidade, evolução contínua e gestão ativa (ALMEIDA; BAX, 2003). Essa dimensão social e institucional é especialmente relevante no contexto governamental, onde a adoção de um modelo semântico compartilhado exige coordenação entre múltiplos órgãos com culturas organizacionais e infraestruturas tecnológicas distintas.

## 2.4 METODOLOGIAS DE CONSTRUÇÃO DE ONTOLOGIAS

A construção de ontologias evoluiu de uma atividade artesanal e *ad hoc* para uma disciplina com metodologias sistematizadas, inspiradas na engenharia de *software*. Duas metodologias se destacam na literatura como referências consolidadas: o SABiO, desenvolvido no contexto brasileiro, e o METHONTOLOGY, de origem espanhola e alcance global.

### 2.4.1 SABiO — *Systematic Approach for Building Ontologies*

<!-- Seção terciária: misto, sem negrito -->

O SABiO é uma metodologia sistemática para desenvolvimento de ontologias de domínio, proposta por Ricardo de Almeida Falbo, da Universidade Federal do Espírito Santo (UFES), publicada em 2014. O SABiO distingue conceitualmente entre **ontologias de referência** — modelos conceituais de um domínio, independentes de implementação tecnológica — e **ontologias operacionais** — adaptadas para uso em aplicações específicas. Essa distinção é metodologicamente relevante: a proposta deste trabalho posiciona-se como uma ontologia de referência, cujo objetivo não é a implementação imediata em um sistema, mas a formalização conceitual do domínio como fundamento para futuras integrações (FALBO, 2014).

O processo SABiO organiza-se em cinco fases principais: (1) identificação do propósito e elicitação de requisitos, na qual são definidas as *competency questions* — perguntas que a ontologia deve ser capaz de responder; (2) captura da ontologia, com levantamento de conceitos, relações, propriedades e restrições do domínio; (3) formalização, com redação dos axiomas em linguagem formal; (4) *design*, com estruturação da ontologia; e (5) teste, com validação e verificação contra os requisitos elicitados. Cinco processos de suporte permeiam todas as fases: Aquisição de Conhecimento, Documentação, Gestão de Configuração, Reutilização e Avaliação (FALBO, 2014).

Uma versão estendida — SABiOx — foi publicada em 2024, incorporando princípios ágeis e organizando o desenvolvimento em ciclos iterativos e incrementais, com fases de Requisito, Configuração, Captura, *Design* e Implementação, acompanhadas de atividades adicionais de Publicação (FALBO et al., 2024). A introdução de princípios ágeis ao SABiOx representa uma resposta às críticas de rigidez do processo original e amplia sua aplicabilidade a contextos onde os requisitos evoluem durante o desenvolvimento.

### 2.4.2 METHONTOLOGY

O METHONTOLOGY é uma das metodologias mais abrangentes e citadas na literatura internacional de engenharia de ontologias, desenvolvida pela Universidade Politécnica de Madri (UPM) a partir de 1997. Fundamentada nos processos de desenvolvimento de *software* definidos pelo IEEE, a metodologia adota um modelo de ciclo de vida baseado em prototipagem evolutiva e enfatiza a reutilização de ontologias preexistentes como estratégia para redução do esforço de desenvolvimento (GÓMEZ-PÉREZ et al., 1997).

O METHONTOLOGY organiza-se em seis fases conceituais: (1) especificação, com produção de especificação formal ou semiformal por meio de *competency questions*; (2) conceituação, com desenvolvimento do modelo conceitual do domínio; (3) formalização, com tradução do modelo conceitual para linguagem formal; (4) integração, com incorporação de ontologias e componentes reutilizáveis; (5) implementação, com codificação em linguagem computacional (OWL, Ontolingua, entre outras); e (6) manutenção, com atualizações e refinamentos contínuos. Atividades de suporte como Garantia de Qualidade, Gestão de Configuração, Documentação e Avaliação permeiam todas as fases (GÓMEZ-PÉREZ et al., 1997).

### 2.4.3 Análise comparativa e escolha metodológica

A comparação entre SABiO e METHONTOLOGY revela diferenças relevantes para a escolha metodológica deste trabalho. O SABiO apresenta maior flexibilidade e foco específico em ontologias de domínio, com ampla adoção no contexto acadêmico brasileiro. No entanto, o SABiO não endereça formalmente atividades de gestão de projeto nem inclui uma fase explícita de manutenção em seu modelo de ciclo de vida original — limitações que são parcialmente corrigidas na versão estendida SABiOx (FALBO et al., 2024), mas que ainda reduzem sua aderência a projetos que requerem rastreabilidade e documentação sistemática de decisões metodológicas.

O METHONTOLOGY, por sua vez, apresenta um conjunto de características que o tornam mais adequado aos objetivos e às exigências deste trabalho. Em primeiro lugar, a metodologia foi desenvolvida com base nos processos de engenharia de *software* definidos pelo IEEE, o que confere rigor estrutural e rastreabilidade ao processo de construção. Em segundo lugar, seu ciclo de vida inclui explicitamente atividades de especificação, avaliação e manutenção — o que é essencial em um trabalho que propõe uma ontologia de referência passível de adoção e evolução por múltiplos órgãos públicos. Em terceiro lugar, o METHONTOLOGY é independente de domínio e inclui mecanismos para integração e reutilização de ontologias preexistentes, o que se alinha à necessidade de interoperabilidade semântica com padrões já adotados no governo eletrônico brasileiro, como OWL e SKOS. Por fim, o METHONTOLOGY é a metodologia mais amplamente citada e validada na literatura internacional de engenharia de ontologias, tendo sido adotada em projetos de diferentes domínios e escalas, o que facilita a comparação com trabalhos correlatos e reforça a reprodutibilidade da proposta (GÓMEZ-PÉREZ et al., 1997).

Ambas as metodologias compartilham o uso de *competency questions* como mecanismo de elicitação de requisitos. Diante dos critérios expostos — rigor metodológico, cobertura explícita do ciclo de vida, suporte à integração e reconhecimento internacional —, adota-se o METHONTOLOGY como metodologia orientadora para o desenvolvimento da ontologia proposta neste trabalho, sem prejuízo do aproveitamento de conceitos e práticas compatíveis oriundos de outras abordagens.

## 2.5 INTEROPERABILIDADE SEMÂNTICA NO GOVERNO ELETRÔNICO

A interoperabilidade entre sistemas de informação governamentais é uma condição necessária para que os dados produzidos por diferentes órgãos possam ser integrados, comparados e reutilizados de forma eficaz. No contexto brasileiro, o marco normativo para essa interoperabilidade é o **ePING** — Padrões de Interoperabilidade de Governo Eletrônico —, *framework* do Governo Federal que estabelece premissas, políticas e especificações técnicas mínimas obrigatórias para o uso de Tecnologia da Informação e Comunicação nos órgãos do Poder Executivo Federal (BRASIL, 2018).

O ePING estrutura-se em cinco segmentos: interconexão, segurança, meios de acesso, organização e intercâmbio de informações, e áreas de integração governamental. No segmento de organização e intercâmbio de informações, o *framework* determina explicitamente a adoção de ontologias e vocabulários controlados para viabilizar a **interoperabilidade semântica** — isto é, a capacidade de sistemas distintos interpretarem e processarem os dados trocados de forma não ambígua. As tecnologias semânticas previstas incluem: RDF (*Resource Description Framework*), para descrição de recursos e intercâmbio de dados; OWL (*Web Ontology Language*), para definição de ontologias; SKOS (*Simple Knowledge Organization System*), para gestão de vocabulários e sistemas de organização do conhecimento; e SPARQL, em status de estudo (BRASIL, 2018).

O SKOS, padrão W3C publicado em 2009, é construído sobre RDF e RDFS e tem como objetivo viabilizar a publicação e o uso de vocabulários como dados vinculados (*linked data*). Sua relevância para o contexto LAI reside na capacidade de conectar sistemas tradicionais de organização do conhecimento — como tesauros e esquemas de classificação já utilizados por alguns órgãos — à infraestrutura de dados abertos governamentais. A integração entre OWL e SKOS permite abordagens híbridas: OWL para estruturas formais com capacidade de inferência lógica, e SKOS para hierarquias de conceitos navegáveis por humanos, possibilitando migração gradual entre diferentes níveis de formalidade semântica (W3C, 2009).

É importante sublinhar que o ePING não apenas recomenda, mas **exige** a adoção dessas tecnologias pelos órgãos federais. Essa obrigatoriedade normativa confere à proposta deste trabalho um respaldo institucional que vai além da contribuição acadêmica: a construção de uma ontologia para integração de dados LAI alinha-se diretamente a uma política de governo já em vigor. No entanto, há uma lacuna: enquanto o ePING estabelece os padrões tecnológicos de forma genérica, não existe, até onde se identificou na literatura, uma ontologia de referência específica para o domínio dos pedidos de acesso à informação orientada à integração entre sistemas de diferentes órgãos — o que caracteriza a contribuição original deste trabalho.

Como referência internacional de implementação, destaca-se a Plataforma CLAV, desenvolvida pela Direção-Geral do Livro, dos Arquivos e das Bibliotecas (DGLAB) de Portugal, que disponibiliza dados administrativos em múltiplos formatos semânticos — RDF/OWL, SKOS, XML e CSV — por meio de API aberta, referenciada no catálogo europeu de ativos semânticos Joinup (CADERNOS BAD, 2019). O caso CLAV demonstra que a adoção de ontologias e dados vinculados em contextos governamentais é tecnicamente viável e institucionalmente sustentável, oferecendo um modelo de referência relevante para o contexto brasileiro.
<!-- /SECTION:literature-review -->

<!-- SECTION:methodology -->
# 3 METODOLOGIA

<!-- Formatação ABNT/UFPR: fonte Arial ou Times New Roman 12, espaçamento 1,5, recuo de parágrafo 1,5 cm. Seção primária: nova página, negrito + MAIÚSCULA. -->

Este capítulo descreve os procedimentos metodológicos adotados para a consecução dos objetivos definidos na Introdução. A primeira seção apresenta a caracterização da pesquisa quanto à natureza, à abordagem, à perspectiva temporal, aos fins e aos meios; as seções subsequentes detalharão a delimitação do universo e das fontes de dados, os procedimentos de coleta e análise, e as limitações de escopo do método.

## 3.1 CARACTERIZAÇÃO DA PESQUISA

<!-- Seção secundária: MAIÚSCULA, sem negrito. -->

Para a caracterização desta pesquisa adotam-se os critérios "quanto aos fins" e "quanto aos meios" propostos por Vergara (2016), complementados pelas dimensões de natureza, abordagem e perspectiva temporal, conforme orientação de Gil (2002), Lakatos e Marconi (2003) e Sampieri, Fernández-Collado e Baptista (2013). A combinação desses cinco eixos permite descrever, de maneira sistemática, o desenho metodológico do presente trabalho, justificando cada escolha à luz de pelo menos uma referência canônica da metodologia científica brasileira.

Quanto à **natureza**, esta pesquisa classifica-se como **aplicada**. Vergara (2016) define a pesquisa aplicada como aquela que possui finalidade prática e é motivada pela necessidade de resolver problemas concretos, sejam eles imediatos ou não. Gil (2002) acrescenta que pesquisas dessa natureza decorrem do desejo de conhecer com vistas a fazer algo de maneira mais eficiente ou eficaz. O presente trabalho enquadra-se nessa categoria por desenvolver uma proposta de ontologia voltada à resolução do problema operacional de heterogeneidade de processos e baixa interoperabilidade semântica dos dados de pedidos de acesso à informação pública geridos por meio do portal FalaBR e regulados pela Lei nº 12.527/2011 (BRASIL, 2011).

Quanto à **abordagem**, adota-se a perspectiva **qualitativa**. Lakatos e Marconi (2003) caracterizam a pesquisa qualitativa como aquela cujas informações não são quantificáveis e cujos dados são analisados indutivamente, sendo a interpretação dos fenômenos e a atribuição de significados elementos centrais do processo investigativo. A escolha da abordagem qualitativa fundamenta-se no objeto deste estudo: a construção de uma ontologia constitui atividade de organização e representação semântica do conhecimento, na qual prevalecem a interpretação conceitual, a análise relacional e a modelagem de significados — dimensões que, do ponto de vista ontológico, não podem ser mensuradas quantitativamente (MENDONÇA, 2015). A análise documental da base de dados aberta do FalaBR e da literatura científica recuperada nas bases Web of Science, Scopus e SciELO sustenta a abordagem qualitativa por se voltar à identificação de padrões conceituais e relacionais, e não à mensuração estatística de variáveis.

Quanto à **perspectiva temporal**, esta pesquisa classifica-se como **transversal**. Sampieri, Fernández-Collado e Baptista (2013) descrevem o desenho transversal como aquele que coleta dados em um único momento no tempo, descrevendo variáveis e analisando suas inter-relações em dado momento. O recorte temporal adotado para a análise dos pedidos de acesso à informação registrados no portal FalaBR compreende o período de 1º de janeiro a 31 de dezembro de 2025, intervalo selecionado por representar o ano completo mais recente com dados consolidados disponíveis na base aberta da Controladoria-Geral da União (CGU) na data da extração dos dados, realizada em 20 de janeiro de 2026.

Quanto aos **fins**, a presente pesquisa classifica-se simultaneamente como **descritiva, aplicada e metodológica**, segundo a tipologia proposta por Vergara (2016). É descritiva por expor as características do ecossistema documental e legal da Lei de Acesso à Informação (LAI) e por sistematizar as ontologias preexistentes nos domínios do governo aberto e da transparência pública — Vergara (2000, p. 47) define que a pesquisa descritiva "expõe características de determinada população ou de determinado fenômeno". É aplicada conforme já justificado em sua natureza, por voltar-se à solução de um problema operacional concreto. É metodológica por produzir um artefato — a ontologia proposta — com função de instrumento de organização do conhecimento e representação semântica replicável em outras instâncias do ecossistema brasileiro de transparência passiva.

Quanto aos **meios**, esta pesquisa combina três procedimentos: **bibliográfico, documental e estudo de caso com prova de conceito**. A pesquisa bibliográfica, definida por Vergara (2000, p. 48) como "estudo sistematizado desenvolvido com base em material publicado em livros, revistas, jornais, redes eletrônicas", sustenta a revisão da literatura sobre ontologias, governo aberto e interoperabilidade semântica, conduzida nas bases Web of Science, Scopus e SciELO. A pesquisa documental complementa a bibliográfica ao examinar fontes primárias que ainda não receberam tratamento analítico — em especial a Lei nº 12.527/2011 (BRASIL, 2011), seus decretos regulamentadores, os Padrões de Interoperabilidade de Governo Eletrônico (ePING) e a base de dados aberta do FalaBR. O estudo de caso, conforme Yin (2001), é compreendido como uma investigação empírica que examina um fenômeno contemporâneo em profundidade e em seu contexto de vida real, especialmente quando os limites entre o fenômeno e o contexto não são claramente evidentes; aplica-se aqui ao recorte do FalaBR como instância concreta do fenômeno de gestão dos pedidos de acesso à informação. A prova de conceito, por sua vez, é incorporada como etapa de validação da ontologia proposta, operacionalizada por meio da implementação parcial em ferramenta de edição ontológica e da execução de consultas que verifiquem o atendimento às questões de competência definidas, sem objetivar a entrega de um sistema em produção.

A síntese das classificações adotadas e dos respectivos autores de referência é apresentada no Quadro 1, a seguir.

<!-- Quadro: título acima, fonte 10, centralizado, espaçamento simples. Fonte abaixo, fonte 10, espaçamento simples. -->

Quadro 1 – Síntese da caracterização metodológica da pesquisa

| Critério | Classificação adotada | Autor(es) de referência |
|---|---|---|
| Natureza | Aplicada | Vergara (2016); Gil (2002) |
| Abordagem | Qualitativa | Lakatos e Marconi (2003) |
| Perspectiva temporal | Transversal — recorte de 01/01/2025 a 31/12/2025 | Sampieri, Fernández-Collado e Baptista (2013) |
| Quanto aos fins | Descritiva, Aplicada e Metodológica | Vergara (2016) |
| Quanto aos meios | Bibliográfica, Documental e Estudo de caso com prova de conceito | Vergara (2016); Yin (2001) |

FONTE: A autora (2026).

A combinação desses cinco eixos de classificação ancora as decisões metodológicas detalhadas nas seções subsequentes deste capítulo — a delimitação do universo e das fontes de dados, os procedimentos de coleta nas bases científicas e na base aberta do FalaBR, as técnicas de análise documental e de modelagem ontológica, e as limitações de escopo da pesquisa.

## 3.2 DELIMITAÇÃO

<!-- Seção secundária: MAIÚSCULA, sem negrito. -->

A delimitação da pesquisa, conforme orientação de Vergara (2016) e Lakatos e Marconi (2003), compreende a definição explícita do universo de elementos investigados, da amostra adotada e dos sujeitos da pesquisa. Em pesquisas documentais sobre dados públicos abertos, o universo corresponde ao conjunto de registros documentais disponibilizados pela instituição mantenedora, e os sujeitos da pesquisa coincidem com esses registros, e não com pessoas físicas. Esta seção apresenta os recortes adotados nessas três dimensões; o escopo conceitual do artefato ontológico — isto é, quais classes de fenômenos devem ser representadas pela ontologia proposta — é tratado separadamente na seção 3.3.

**Universo.** O universo desta pesquisa é constituído pelos pedidos de acesso à informação registrados no portal FalaBR — Plataforma Integrada de Ouvidoria e Acesso à Informação, mantido pela Controladoria-Geral da União (CGU) — restritos ao âmbito do Poder Executivo Federal. A delimitação jurisdicional decorre da própria estrutura da plataforma: embora a Lei nº 12.527/2011 (BRASIL, 2011) regule o direito de acesso à informação em todos os Poderes (Executivo, Legislativo e Judiciário) e em todos os níveis federativos (União, estados, Distrito Federal e municípios), o FalaBR concentra exclusivamente os pedidos endereçados a órgãos e entidades do Executivo Federal — administração direta (ministérios), autarquias, fundações, empresas públicas, sociedades de economia mista, universidades federais, hospitais federais e órgãos de controle. A base aberta disponibilizada pela CGU não contempla pedidos endereçados aos demais Poderes ou aos entes subnacionais, que mantêm sistemas próprios e independentes.

**Amostra.** A amostra desta pesquisa é organizada em duas camadas analíticas complementares, estratégia adequada a pesquisas qualitativas que operam sobre grandes corpora documentais (LAKATOS; MARCONI, 2003; VERGARA, 2016).

A primeira camada caracteriza-se como **censo** dos pedidos e recursos registrados no recorte temporal de 1º de janeiro a 31 de dezembro de 2025, extraídos da base aberta do FalaBR em 20 de janeiro de 2026 — totalizando 84.109 pedidos e 9.554 recursos, sistematizados em duas planilhas distintas e relacionáveis pelo identificador `IdPedido`. Essa camada sustenta a análise quantitativo-descritiva do ecossistema de pedidos, viabilizando a identificação de tipologias institucionais, distribuição de decisões, padrões de prazos, frequência de preenchimento dos campos e vocabulário recorrente. Por incidir sobre a totalidade do recorte temporal, a primeira camada fundamenta empiricamente a constatação de heterogeneidade que motiva a proposta ontológica.

A segunda camada constitui-se de **amostra não-probabilística por tipicidade**, definida por Vergara (2016) como aquela em que os elementos são selecionados intencionalmente pela representatividade tipológica que ostentam em relação ao universo. A amostra compreende um órgão por categoria institucional do Executivo Federal, totalizando sete órgãos representativos: (a) um ministério finalístico; (b) uma universidade federal; (c) um hospital federal; (d) uma autarquia ou agência reguladora; (e) uma fundação pública; (f) uma empresa pública; e (g) um órgão de controle. A seleção final dos órgãos específicos em cada categoria será realizada após a análise descritiva da Camada 1, considerando o volume de pedidos, a diversidade de tipos de decisão registrados e a completude dos campos documentais. Sobre essa segunda camada operam a análise qualitativa em profundidade dos textos dos pedidos e respostas e a modelagem das classes, propriedades e relações da ontologia proposta.

**Sujeitos da pesquisa.** Por se tratar de pesquisa documental baseada exclusivamente em dados públicos secundários de natureza administrativa, os sujeitos da pesquisa correspondem aos próprios **registros documentais** — pedidos de acesso à informação, respostas dos órgãos e recursos interpostos — disponibilizados em formato aberto pela CGU. Não há, portanto, sujeitos humanos envolvidos na coleta de dados, e os textos analisados não contêm dados pessoais identificáveis dos solicitantes, em conformidade com o artigo 31 da Lei nº 12.527/2011 (BRASIL, 2011).

**Escopo da revisão bibliográfica.** Como dimensão complementar da delimitação, registra-se que o escopo da revisão bibliográfica abrange publicações dos últimos dez anos (2016–2026), nos idiomas português e inglês, indexadas nas bases Web of Science, Scopus e SciELO, acessadas via Portal de Periódicos da CAPES com autenticação Acesso CAFe. São considerados artigos científicos, teses e dissertações, com aplicação do filtro de revisão por pares para assegurar qualidade acadêmica do material consultado. Os procedimentos operacionais de busca, triagem e seleção desse material são detalhados na seção 3.4.

A síntese dos recortes do universo e da amostra é apresentada no Quadro 2, a seguir.

<!-- Quadro: título acima, fonte 10, centralizado, espaçamento simples. Fonte abaixo, fonte 10. Pode ser convertido em Figura (fluxograma de afunilamento) na etapa de design final. -->

Quadro 2 – Recorte do universo e amostra da pesquisa

| Camada | Recorte aplicado | Universo resultante |
|---|---|---|
| 0 — Universo legal | LAI / Lei nº 12.527/2011 — três Poderes × União, estados, DF e municípios | Pedidos LAI em todo o território nacional |
| 1 — Recorte jurisdicional | Apenas Poder Executivo Federal (administração direta e indireta) | Pedidos endereçados a órgãos federais do Executivo |
| 2 — Recorte sistêmico | Apenas pedidos registrados via portal FalaBR | Pedidos centralizados na plataforma integrada da CGU |
| 3 — Recorte temporal | Período de 01/01/2025 a 31/12/2025 (extração em 20/01/2026) | 84.109 pedidos e 9.554 recursos — **Camada 1 analítica: censo** |
| 4 — Amostra por tipicidade | Um órgão representativo por categoria institucional | Sete órgãos — **Camada 2 analítica: ministério finalístico, universidade federal, hospital federal, autarquia/agência, fundação pública, empresa pública, órgão de controle** |

FONTE: A autora (2026).

## 3.3 ESCOPO DO DOMÍNIO DA ONTOLOGIA

<!-- Seção secundária: MAIÚSCULA, sem negrito. -->

A construção de uma ontologia de domínio requer, como etapa metodológica preliminar, a definição explícita do recorte conceitual a ser representado — isto é, a especificação de quais entidades, propriedades e relações pertencem ao escopo do artefato e, igualmente, de quais permanecem fora dele (MENDONÇA, 2015). Essa delimitação tem duas funções metodológicas: orienta a formulação das **questões de competência** que a ontologia deverá responder e, posteriormente, fornece o critério de avaliação para a validação da prova de conceito.

O domínio coberto pela ontologia proposta restringe-se aos elementos constitutivos do **processo de pedido de acesso à informação pública na modalidade de transparência passiva**, conforme regulado pela Lei nº 12.527/2011 (BRASIL, 2011). Esse processo compreende as entidades-núcleo do fluxo de solicitação, resposta e recurso, juntamente com os atores institucionais que dele participam e os atributos administrativos que o caracterizam — prazo, status, tipo de decisão e categorização do pedido. Permanecem fora do escopo as manifestações de ouvidoria de outras naturezas (denúncias, elogios, reclamações e sugestões), que, embora coexistam no portal FalaBR, não constituem pedidos de acesso à informação no sentido estrito da LAI; permanecem igualmente fora do escopo os procedimentos judiciais eventualmente decorrentes do exaurimento da via administrativa, os conteúdos materiais das informações solicitadas e a análise de mérito das respostas concedidas pelos órgãos. A delimitação por exclusão é particularmente relevante para o caso do FalaBR porque a plataforma agrega, sob uma mesma interface, tipos heterogêneos de manifestação cidadã cuja distinção semântica é precisamente um dos problemas que a ontologia se propõe a resolver.

A síntese do escopo conceitual da ontologia, organizada por categoria, é apresentada no Quadro 3.

<!-- Quadro: título acima, fonte 10, centralizado, espaçamento simples. Fonte abaixo, fonte 10. -->

Quadro 3 – Delimitação do domínio da ontologia proposta

| Categoria | Fora do escopo | Dentro do escopo |
|---|---|---|
| Tipo de manifestação | Denúncias, elogios, reclamações e sugestões de ouvidoria | Pedido de acesso à informação (PAINF) |
| Atos do processo | Procedimentos administrativos não-LAI; processos judiciais decorrentes | Resposta do órgão; recursos administrativos em 1ª, 2ª e 3ª instâncias |
| Solicitante | Identidade nominal e demais dados pessoais do solicitante | Solicitante como categoria abstrata, sem dados pessoais identificáveis |
| Órgão | Estrutura hierárquica interna completa do órgão | Órgão destinatário como entidade institucional |
| Atributos administrativos | Conteúdo material da informação solicitada | Status, prazo, tipo de decisão, categorização do pedido |
| Avaliação | Análise de mérito sobre a adequação da resposta à demanda | Atributos formais da resposta (concedida, parcialmente concedida, negada, com sigilo) |

FONTE: A autora (2026).

A delimitação apresentada no Quadro 3 estabelece o recorte de domínio que orientará a formulação das questões de competência e a especificação dos requisitos da ontologia, conforme será detalhado na seção dedicada aos procedimentos de construção do artefato ontológico.

## 3.4 PROCEDIMENTOS DE COLETA DE DADOS

<!-- Seção secundária: MAIÚSCULA, sem negrito. -->

Os procedimentos de coleta de dados desta pesquisa foram organizados em dois fluxos paralelos, em correspondência com os meios definidos na seção 3.1 (bibliográfico e documental). A subseção 3.4.1 descreve o levantamento bibliográfico sistemático conduzido em bases científicas para fundamentar a revisão teórico-empírica; a subseção 3.4.2 descreve a extração e o tratamento dos dados abertos do portal FalaBR, que constituem o corpus empírico da análise documental e da modelagem da ontologia proposta.

### 3.4.1 Levantamento bibliográfico

<!-- Seção terciária: misto, sem negrito. -->

O levantamento bibliográfico foi conduzido em três bases científicas multidisciplinares amplamente reconhecidas no âmbito acadêmico: **Web of Science**, **Scopus** e **SciELO**, seguindo o modelo metodológico adotado em pesquisas recentes de Ciência da Informação na UFPR (PEREIRA, 2025). As bases foram acessadas por meio do **Portal de Periódicos da CAPES**, com autenticação via Acesso CAFe, mediante credencial institucional. A coleta dos dados bibliográficos foi realizada no mês de junho de 2026.

A estratégia de busca combinou termos em **português e inglês** — idiomas predominantes da literatura no campo — articulados por **operadores booleanos** AND e OR. Foram aplicados, em todas as bases, os seguintes filtros de inclusão: publicações revisadas por pares; período de publicação entre 2016 e 2026 (últimos dez anos); tipos documentais "artigo científico", "tese" e "dissertação"; e busca restrita aos campos título, resumo e palavras-chave. No SciELO, os termos foram traduzidos para o português quando aplicável, em conformidade com o perfil de indexação da base.

A busca foi estruturada em torno de cinco objetivos temáticos, correspondentes aos pilares conceituais da pesquisa: (i) ontologia aplicada à Lei de Acesso à Informação e ao FalaBR; (ii) ontologia aplicada à transparência pública e ao governo aberto; (iii) ontologia e interoperabilidade semântica; (iv) metodologia de construção de ontologias; e (v) integração de dados abertos governamentais. As *strings* exatas utilizadas em cada objetivo são apresentadas no Quadro 4.

<!-- Quadro: título acima, fonte 10, centralizado, espaçamento simples. Fonte abaixo, fonte 10. -->

Quadro 4 – *Strings* de busca por objetivo temático

| Objetivo da busca | *Strings* utilizadas |
|---|---|
| (i) Ontologia + LAI / FalaBR | `("ontology" OR "ontologia") AND ("Lei de Acesso à Informação" OR "Freedom of Information" OR "FalaBR")` |
| (ii) Ontologia + transparência pública | `("ontology" OR "ontologia") AND ("open government" OR "governo aberto" OR "transparência pública")` |
| (iii) Ontologia + interoperabilidade semântica | `("ontology" OR "ontologia") AND ("semantic interoperability" OR "interoperabilidade semântica")` |
| (iv) Metodologia de construção de ontologias | `("METHONTOLOGY" OR "OntoForInfoScience" OR "NeOn" OR "ontology engineering" OR "ontology construction" OR "ontology development" OR "construção de ontologia" OR "como construir uma ontologia" OR "etapas para ontologia")` |
| (v) Dados abertos governamentais + integração | `("open government data" OR "dados abertos governamentais") AND ("integration" OR "integração")` |

FONTE: A autora (2026).

Os resultados das buscas foram submetidos a um **fluxo de triagem em camadas** com seis etapas, replicando o modelo proposto por Pereira (2025): (1) extração dos resultados brutos de cada base com as *strings* do Quadro 4; (2) aplicação dos filtros de inclusão (revisão por pares, período, tipos documentais); (3) eliminação de registros duplicados entre as bases; (4) triagem por leitura de título, palavras-chave e resumo, para identificação dos estudos aderentes ao escopo da pesquisa; (5) leitura integral dos estudos selecionados na etapa anterior; e (6) seleção final dos trabalhos efetivamente incorporados à revisão teórico-empírica. O gerenciamento das referências e o controle do fluxo de triagem foram apoiados pelo *software* **Zotero**, escolhido por sua gratuidade, capacidade de organização por coleções e integração nativa com os principais editores de texto acadêmico.

Os resultados quantitativos de cada etapa do fluxo de triagem — total de documentos recuperados por base e por *string*, após aplicação dos filtros, após desduplicação, após triagem por resumo e após leitura integral — são reportados na seção 4 (Resultados e Discussão), em quadro autoral nos moldes do Quadro 7 de Pereira (2025).

### 3.4.2 Extração e tratamento dos dados do FalaBR

<!-- Seção terciária: misto, sem negrito. -->

Os dados dos pedidos de acesso à informação e dos recursos administrativos foram extraídos do **portal de dados abertos da Controladoria-Geral da União**, especificamente do *endpoint* <https://falabr.cgu.gov.br/publico/DownloadDados/DownloadDadosLai.aspx>, responsável pela disponibilização periódica dos registros do FalaBR em formato aberto. A extração foi realizada em 20 de janeiro de 2026, com o filtro temporal restrito ao período de 1º de janeiro a 31 de dezembro de 2025, em conformidade com o recorte definido na seção 3.2.

O conjunto extraído compreende dois arquivos CSV estruturalmente distintos e relacionáveis pelo identificador `IdPedido`: o arquivo de **pedidos**, com 84.109 registros, e o arquivo de **recursos**, com 9.554 registros. Os arquivos foram importados em ambiente Microsoft Excel para visualização inicial, com os dados estruturados em colunas. Os campos disponíveis em cada planilha, bem como suas descrições semânticas, são apresentados nos Quadros 5 e 6.

<!-- Quadro: título acima, fonte 10, centralizado, espaçamento simples. Fonte abaixo, fonte 10. -->

Quadro 5 – Campos da planilha de pedidos do FalaBR

| Campo | Descrição |
|---|---|
| `IdPedido` | Identificador único interno do pedido na base FalaBR |
| `ProtocoloPedido` | Número de protocolo público do pedido |
| `Esfera` | Esfera federativa do órgão (Federal, neste recorte) |
| `OrgaoDestinatario` | Órgão da administração pública federal destinatário do pedido |
| `Situacao` | Status atual do pedido no fluxo (ex.: respondido, em recurso) |
| `DataRegistro` | Data de registro do pedido no sistema |
| `ResumoSolicitacao` | Resumo textual da solicitação fornecido pelo solicitante |
| `DetalhamentoSolicitacao` | Texto completo descritivo do pedido |
| `PrazoAtendimento` | Data-limite legal para resposta, conforme art. 11 da LAI |
| `FoiProrrogado` | Indicador de prorrogação do prazo (sim/não) |
| `FoiReencaminhado` | Indicador de reencaminhamento entre órgãos (sim/não) |
| `FormaResposta` | Modalidade de entrega da resposta ao solicitante |
| `OrigemSolicitacao` | Canal de origem do pedido (web, presencial, etc.) |
| `IdSolicitante` | Identificador interno do solicitante (sem dados pessoais identificáveis) |
| `AssuntoPedido` | Categoria temática primária do pedido |
| `SubAssuntoPedido` | Categoria temática secundária (subcategoria do assunto) |
| `Tag` | Etiqueta livre opcional, de uso heterogêneo, com preenchimento esparso e sem padronização |
| `DataResposta` | Data efetiva de entrega da resposta pelo órgão |
| `Resposta` | Texto da resposta fornecida pelo órgão |
| `Decisao` | Categoria sintética da decisão (ex.: Acesso Concedido, Acesso Negado) |
| `EspecificacaoDecisao` | Detalhamento da decisão, especificando motivos quando aplicável |

FONTE: A autora (2026), com base na estrutura da base aberta do FalaBR (CGU).

Quadro 6 – Campos da planilha de recursos do FalaBR

| Campo | Descrição |
|---|---|
| `IdRecurso` | Identificador único do recurso |
| `IdRecursoPrecedente` | Identificador do recurso anterior na cadeia recursal (quando aplicável) |
| `DescRecurso` | Texto descritivo do recurso interposto |
| `IdPedido` | Identificador do pedido original que motivou o recurso (chave de junção com a planilha de pedidos) |
| `IdSolicitante` | Identificador interno do solicitante do recurso |
| `ProtocoloPedido` | Protocolo público do pedido associado |
| `OrgaoPedido` | Órgão originalmente destinatário do pedido |
| `OrgaoDestinatario` | Órgão destinatário do recurso (pode diferir nas instâncias superiores) |
| `Instancia` | Instância recursal (1ª, 2ª ou 3ª) |
| `Situacao` | Status atual do recurso no fluxo |
| `DataRegistro` | Data de registro do recurso |
| `PrazoAtendimento` | Data-limite legal para resposta ao recurso |
| `OrigemSolicitacao` | Canal de origem do recurso |
| `TipoRecurso` | Classificação do tipo de recurso interposto |
| `DataResposta` | Data efetiva de resposta ao recurso |
| `RespostaRecurso` | Texto da resposta ao recurso |
| `TipoResposta` | Categoria da resposta dada ao recurso |

FONTE: A autora (2026), com base na estrutura da base aberta do FalaBR (CGU).

Após a importação das planilhas, os dados foram submetidos a uma rotina de pré-processamento em **RStudio**, com utilização do conjunto *tidyverse* — particularmente os pacotes `dplyr` (manipulação de dados), `lubridate` (manipulação de datas) e `stringr` (manipulação de texto). As operações de pré-processamento tiveram dois propósitos articulados: assegurar a qualidade técnica dos dados e produzir variáveis derivadas necessárias às análises planejadas. Registra-se previamente que o campo `Tag` da planilha de pedidos, embora disponibilizado na exportação, foi excluído das análises subsequentes e da modelagem ontológica, em razão de seu preenchimento esparso e não-padronizado no recorte temporal analisado, característica que inviabiliza a extração de significado semântico consistente. As operações aplicadas, com suas respectivas justificativas metodológicas, são detalhadas no Quadro 7.

Quadro 7 – Operações de pré-processamento aplicadas aos dados do FalaBR

| Operação | Implementação em R | Justificativa metodológica |
|---|---|---|
| Conversão dos campos de data (`DataRegistro`, `DataResposta`, `PrazoAtendimento`) do tipo *character* para *Date* | `lubridate::dmy()` ou `lubridate::ymd()` | Viabiliza cálculos temporais (tempo de resposta, cumprimento de prazo) |
| Identificação e quantificação de valores ausentes por campo | `dplyr::summarise()` combinado com `is.na()` | Documenta empiricamente a heterogeneidade e a incompletude que motivam a proposta ontológica |
| Padronização da codificação para UTF-8 e remoção de espaços excedentes em campos textuais | `stringr::str_trim()`, `iconv()` | Normalização técnica necessária para análise textual e *matching* entre campos |
| Verificação dos domínios de valores categóricos (`Decisao`, `EspecificacaoDecisao`, `Esfera`, `Situacao`, `TipoRecurso`, `Instancia`) | `dplyr::distinct()`, `table()` | Identificação de inconsistências terminológicas — insumo direto para a definição das classes da ontologia |
| Checagem de duplicatas por `IdPedido` (pedidos) e por `IdRecurso` (recursos) | `dplyr::duplicated()` | Garantia de integridade do censo |
| Criação da variável derivada `tempo_resposta` = `DataResposta` − `DataRegistro` (em dias) | Subtração de datas em ambiente `lubridate` | Indicador de cumprimento de prazo, conforme art. 11 da Lei nº 12.527/2011 (BRASIL, 2011) |
| Criação da variável derivada `categoria_orgao` (sete tipologias definidas em 3.2) | `dplyr::mutate()` com `case_when()` | Conecta a Camada 1 analítica à Camada 2, viabilizando a estratificação por tipicidade institucional |
| *Join* entre as planilhas de pedidos e recursos via `IdPedido` | `dplyr::left_join()` | Permite a análise integrada do ciclo completo: pedido → resposta → recurso(s) |

FONTE: A autora (2026).

O produto do pré-processamento — dois conjuntos de dados consolidados em ambiente R, individualmente tratados e prontos para junção — constitui o insumo empírico para a análise da Camada 1 (descritiva, sobre a totalidade do recorte temporal) e da Camada 2 (qualitativa, sobre a amostra estratificada por tipicidade) definidas na seção 3.2. Os procedimentos metodológicos específicos da construção do artefato ontológico — formulação das questões de competência, modelagem das classes e relações, e operacionalização no editor Protégé — são detalhados na seção 3.5.
<!-- /SECTION:methodology -->

<!-- SECTION:results -->
<!-- PENDING -->
<!-- /SECTION:results -->

<!-- SECTION:conclusion -->
<!-- PENDING -->
<!-- /SECTION:conclusion -->

<!-- SECTION:references -->
<!-- PENDING -->
<!-- /SECTION:references -->
