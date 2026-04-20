---
title: Proposta de ontologia para integração de dados de pedidos de acesso à informação pública baseada no portal FalaBR e na Lei de Acesso à Informação
date: 2026-04-19
sources:
  - type: web
    ref: https://isko.org.br/ojs/index.php/iskobrasil/article/view/72
  - type: web
    ref: https://sol.sbc.org.br/index.php/sbsi/article/view/5940
  - type: web
    ref: https://falabr.cgu.gov.br/web/dadosabertoslai
  - type: web
    ref: https://transparencia-brasil.github.io/negativas-acesso-informacao-Executivo-federal-2021-1/6-comparativo-entre-bases-do-falabr.html
  - type: web
    ref: https://eping.governoeletronico.gov.br/
  - type: web
    ref: https://ieeexplore.ieee.org/document/9050079/
  - type: web
    ref: https://www.al.sp.gov.br/alesp/biblioteca-digital/obra/?id=20783
  - type: web
    ref: https://periodicos.unesc.net/ojs/index.php/iniciacaocientifica/article/view/160
  - type: web
    ref: https://www.scielo.br/j/pci/a/hHMgryMtL7c9RJGNmgHWRRf/
  - type: web
    ref: https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2011/lei/l12527.htm
---

## Research Results

### 1. Ontologias existentes no domínio LAI e governo aberto

A pesquisa identificou a existência da **ONTOLAITP**, uma ontologia derivada da Basic Formal Ontology (BFO) e extensões OBI/IAO desenvolvida especificamente para representar entidades e processos na transparência passiva da Lei de Acesso à Informação brasileira. A ONTOLAITP organiza conceitos por meio de continuantes, realizáveis, papéis, processos e entidades de conteúdo informacional, e foi testada na Universidade Federal do Rio Grande do Sul (UFRGS), demonstrando viabilidade de estruturação semântica dos processos de PAINF (pedidos de acesso à informação). O trabalho habilita integração semântica na administração pública e intercâmbio de conhecimento via representação estruturada.

Adicionalmente, foi identificada uma ontologia de domínio para preservação de privacidade em dados publicados pelo governo brasileiro, que endereça o artigo 31 da LAI (proteção de dados pessoais). Essa ontologia cria terminologia padronizada entre métodos de anonimização, permitindo unificação semântica e interoperabilidade técnica entre ferramentas distintas de anonimização, cumprindo os princípios da LAI.

Para o contexto legislativo, destaca-se a ontologia do Processo Legislativo de São Paulo (Bortolato), desenvolvida com o framework NeOn, alinhada a dados abertos e padrões de web semântica para tornar informações legislativas legíveis por máquinas, enfatizando transparência e interoperabilidade semântica.

### 2. Características e limitações da base FalaBR

O **FalaBR** (Plataforma Integrada de Ouvidoria e Acesso à Informação) passou a receber pedidos LAI a partir de agosto de 2020, centralizando o que antes era distribuído no e-SIC. A plataforma disponibiliza dados abertos em CSV e XML incluindo o "Relatório de pedidos de acesso à informação e solicitantes" com cobertura a partir de 2012, contemplando pedidos, respostas e recursos do Poder Executivo Federal.

Análises comparativas revelam a existência de **duas bases distintas da CGU**: o Painel CGU (2012–2021, com metadados sem conteúdo textual completo) e a base de Consulta de Pedidos e Respostas (2015–2021, com textos completos de petições, respostas e recursos). Há lacunas temporais e discrepâncias de quantidade entre os sistemas, sugerindo sincronização incompleta — por exemplo, a Caixa Econômica Federal registrou 26.452 demandas entre 2019–2021 com categorizações divergentes entre as bases.

Pesquisa do IPEA identificou que quando a transparência ativa em finanças públicas é deficiente, as comunidades tendem a buscar informação via transparência passiva (e-SIC/FalaBR), aumentando o volume de pedidos — o que reforça a necessidade de padronização e monitoramento robusto.

### 3. Marco legal: LAI e lacunas operacionais

A **Lei nº 12.527/2011** regulamenta os procedimentos para garantir acesso à informação para União, Estados, DF e Municípios, abrangendo administração direta e indireta (autarquias, fundações, empresas estatais e sociedades de economia mista). A lei exige disponibilização de ferramentas de busca que permitam acesso objetivo, transparente, claro e inteligível à informação pública — mas não define um processo operacional único e padronizado em nível técnico, tampouco impõe um sistema nacional integrado de workflow, campos de dados, métricas e governança.

### 4. Interoperabilidade e padrões semânticos de governo eletrônico (ePING)

O **ePING** (Padrões de Interoperabilidade de Governo Eletrônico) define premissas, políticas e especificações técnicas mínimas obrigatórias para uso de TIC nos serviços governamentais, abrangendo cinco segmentos: interconexão, segurança, métodos de acesso, organização e intercâmbio de informações, e áreas de integração. O ePING **determina explicitamente a adoção de ontologias e vocabulários controlados** para interoperabilidade semântica, utilizando SKOS (Simple Knowledge Organization System), OWL (Web Ontology Language) e RDF (Resource Description Framework). Governos devem desenvolver vocabulários colaborativos compartilhados por repositórios gerenciados por especialistas de domínio.

Estudos internacionais (IEEE/Emerald) propõem arquitetura sistemática baseada em ontologias para gerenciar cadeias de valor completas de dados abertos governamentais em múltiplos domínios. A abordagem enfatiza que "modelar e projetar o modelo de dados, bem como explorar uma abordagem baseada em ontologia, são pilares críticos" para criar conjuntos de dados OGD ricos e bem descritos.

### 5. Metodologias de construção de ontologias

**METHONTOLOGY** é uma das metodologias mais abrangentes para desenvolvimento de ontologias, desenvolvida pela Universidade Politécnica de Madrid, com raízes nos processos IEEE de desenvolvimento de software. Segue um modelo de prototipagem evolutiva, permitindo refinamento contínuo durante a modelagem. É independente de domínio, comparável às metodologias 101 e UPON, e foi proposta pela FIPA para promover interoperabilidade entre aplicações baseadas em agentes.

Na prática, o desenvolvimento de ontologias combina múltiplas metodologias (101, METHONTOLOGY, On-To-Knowledge). Componentes essenciais incluem: classes (conceitos de domínio), instâncias (materializações), relacionamentos entre conceitos, restrições e propriedades. **Questões de competência** guiam o design. Insight essencial: ontologias representam "uma tentativa de capturar uma visão de mundo", mas requerem adoção da comunidade, evolução contínua e gestão para se manterem relevantes.

---

## Conclusion

A pesquisa confirma que o tema da proposta está bem fundamentado: há lacunas técnicas e semânticas concretas no ecossistema LAI/FalaBR, reconhecidas tanto na literatura acadêmica quanto nos dados abertos disponíveis. A existência da ONTOLAITP demonstra que trabalhos anteriores reconhecem a necessidade de representação semântica no domínio, mas nenhum trabalho encontrado propõe especificamente uma ontologia voltada à **integração de dados entre sistemas de diferentes órgãos** com foco em interoperabilidade operacional. O ePING fornece respaldo normativo direto para a proposta, pois já exige adoção de ontologias e vocabulários controlados no governo eletrônico brasileiro. As bases FalaBR apresentam inconsistências e fragmentação que reforçam empiricamente o problema de pesquisa. Para a construção da ontologia, METHONTOLOGY se apresenta como metodologia consolidada e amplamente referenciada na literatura brasileira, sendo uma escolha justificável para a prova de conceito.

---

## Cited Sources

- ISKO Brasil (2023). *Uso de ontologia BFO na Transparência Passiva da Lei de Acesso à Informação Brasileira: ONTOLAITP*. <https://isko.org.br/ojs/index.php/iskobrasil/article/view/72>
- SBC/SBSI. *Uma Ontologia de Domínio para Preservação de Privacidade em Dados Publicados pelo Governo Brasileiro*. <https://sol.sbc.org.br/index.php/sbsi/article/view/5940>
- CGU. *Dados Abertos LAI — Fala.BR*. <https://falabr.cgu.gov.br/web/dadosabertoslai>
- Transparência Brasil (2021). *Comparativo entre bases de dados do FalaBR*. <https://transparencia-brasil.github.io/negativas-acesso-informacao-Executivo-federal-2021-1/6-comparativo-entre-bases-do-falabr.html>
- Governo Federal do Brasil. *ePING — Padrões de Interoperabilidade de Governo Eletrônico*. <https://eping.governoeletronico.gov.br/>
- IEEE (2020). *An Ontology-based Open Data Interoperability Approach for Cross-Domain Government Data Services*. <https://ieeexplore.ieee.org/document/9050079/>
- BORTOLATO, Frederico. *Uma ontologia do Processo Legislativo de São Paulo*. Assembleia Legislativa do Estado de São Paulo. <https://www.al.sp.gov.br/alesp/biblioteca-digital/obra/?id=20783>
- Revista de Iniciação Científica UNESC. *A Metodologia METHONTOLOGY na Construção de Ontologias*. <https://periodicos.unesc.net/ojs/index.php/iniciacaocientifica/article/view/160>
- SciELO. *Desenvolvimento de uma ontologia sobre componentes de ontologias*. <https://www.scielo.br/j/pci/a/hHMgryMtL7c9RJGNmgHWRRf/>
- BRASIL. *Lei nº 12.527, de 18 de novembro de 2011 — Lei de Acesso à Informação*. <https://www.planalto.gov.br/ccivil_03/_ato2011-2014/2011/lei/l12527.htm>
