---
segment: methodology
research-source: research/tipologia-pesquisa-ciencia-informacao-2026-05-05.md
status: committed
date: 2026-06-05
note: Draft parcial — contém apenas a subseção 3.4 PROCEDIMENTOS DE COLETA DE DADOS (com 3.4.1 Levantamento Bibliográfico e 3.4.2 Extração e Tratamento dos Dados do FalaBR). Deve ser anexado ao final do conteúdo já commitado em build/paper.md para a seção methodology (após 3.3 Escopo do Domínio da Ontologia). Adicionalmente, requer pequena edição em 3.2 já commitada — Decisão 1 aprovada — substituir "aproximadamente 80.000 registros" por "84.109 pedidos e 9.554 recursos" no parágrafo sobre Camada 1, e atualizar a célula correspondente do Quadro 2.
---

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
