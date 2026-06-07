---
segment: methodology
research-source: research/tipologia-pesquisa-ciencia-informacao-2026-05-05.md
status: committed
date: 2026-05-05
note: Draft parcial — contém apenas as subseções 3.2 DELIMITAÇÃO e 3.3 ESCOPO DO DOMÍNIO DA ONTOLOGIA. Deve ser anexado ao final do conteúdo já commitado em build/paper.md para a seção methodology (após 3.1 Caracterização da Pesquisa).
---

## 3.2 DELIMITAÇÃO

<!-- Seção secundária: MAIÚSCULA, sem negrito. -->

A delimitação da pesquisa, conforme orientação de Vergara (2016) e Lakatos e Marconi (2003), compreende a definição explícita do universo de elementos investigados, da amostra adotada e dos sujeitos da pesquisa. Em pesquisas documentais sobre dados públicos abertos, o universo corresponde ao conjunto de registros documentais disponibilizados pela instituição mantenedora, e os sujeitos da pesquisa coincidem com esses registros, e não com pessoas físicas. Esta seção apresenta os recortes adotados nessas três dimensões; o escopo conceitual do artefato ontológico — isto é, quais classes de fenômenos devem ser representadas pela ontologia proposta — é tratado separadamente na seção 3.3.

**Universo.** O universo desta pesquisa é constituído pelos pedidos de acesso à informação registrados no portal FalaBR — Plataforma Integrada de Ouvidoria e Acesso à Informação, mantido pela Controladoria-Geral da União (CGU) — restritos ao âmbito do Poder Executivo Federal. A delimitação jurisdicional decorre da própria estrutura da plataforma: embora a Lei nº 12.527/2011 (BRASIL, 2011) regule o direito de acesso à informação em todos os Poderes (Executivo, Legislativo e Judiciário) e em todos os níveis federativos (União, estados, Distrito Federal e municípios), o FalaBR concentra exclusivamente os pedidos endereçados a órgãos e entidades do Executivo Federal — administração direta (ministérios), autarquias, fundações, empresas públicas, sociedades de economia mista, universidades federais, hospitais federais e órgãos de controle. A base aberta disponibilizada pela CGU não contempla pedidos endereçados aos demais Poderes ou aos entes subnacionais, que mantêm sistemas próprios e independentes.

**Amostra.** A amostra desta pesquisa é organizada em duas camadas analíticas complementares, estratégia adequada a pesquisas qualitativas que operam sobre grandes corpora documentais (LAKATOS; MARCONI, 2003; VERGARA, 2016).

A primeira camada caracteriza-se como **censo** dos pedidos registrados no recorte temporal de 1º de janeiro a 31 de dezembro de 2025, extraídos da base aberta do FalaBR em 20 de janeiro de 2026 — totalizando aproximadamente 80.000 registros. Essa camada sustenta a análise quantitativo-descritiva do ecossistema de pedidos, viabilizando a identificação de tipologias institucionais, distribuição de decisões, padrões de prazos, frequência de preenchimento dos campos e vocabulário recorrente. Por incidir sobre a totalidade do recorte temporal, a primeira camada fundamenta empiricamente a constatação de heterogeneidade que motiva a proposta ontológica.

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
| 3 — Recorte temporal | Período de 01/01/2025 a 31/12/2025 (extração em 20/01/2026) | Aproximadamente 80.000 registros — **Camada 1 analítica: censo** |
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
