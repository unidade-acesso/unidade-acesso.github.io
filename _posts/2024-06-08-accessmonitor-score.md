---
title: The score of AccessMonitor (II)
---

"Nota técnica AccessMonitor" publicada originalmente no sítio Web da Unidade ACESSO em Março de 2015.

Índice do documento

*   [_AccessMonitor_: o que é?](#n12)
*   [Funcionalidades](#n13)
*   [O relatório qualitativo](#n14)
*   [Os testes](#n15)
    *   [de tipo verdadeiro](#n151)
    *   [de tipo falso](#n152)
    *   [de tipo decrescente](#n153)
    *   [de tipo proporcional](#n154)
*   [O índice _AccessMonitor_](#n16)
*   [Bateria de testes](#Bateria_de testes_do_AccessMonitor)

## _AccessMonitor_: o que é?

O _AccessMonitor_ é um validador automático que verifica a aplicação das directrizes de acessibilidade nos conteúdos HTML de um sítio web. O _AccessMonitor_ usa como referência a versão 2.0 das **Directrizes de Acessibilidade para o Conteúdo da Web (WCAG 2.0)** do _World Wide Web Consortium (W3C)_.

O _AccessMonitor_ funciona integralmente na web e não requer quaisquer tipos de instalação, nem depende de um qualquer _browser_ ou sistema operativo e também não precisa de qualquer _plug-in_ adicional para funcionar. **Pode ser utilizado a partir de um qualquer dispositivo que corra um navegador web – o _AccessMonitor_ é integralmente universal**.

Ao contrário dos validadores para as WCAG 1.0, a existência de validadores para as WCAG 2.0 é ainda escassa. Dois dos validadores de referência são o [TAW (WCAG 2.0)](http://www.tawdis.net), ainda em versão beta, e o [_TotalValidator v2_](http://www.totalvalidator.com/). Da base de dados de ferramentas de validação do W3C, para a versão 2.0 das WCAG, apenas aparece o [_PEAT – Photosensitive Epilepsy Analysis Tool (version 0.2 (beta))_](http://trace.wisc.edu/peat/), do _Trace R & D Center_ da Universidade de _Wisconsin-Madison_.

O _AccessMonitor_ resulta da experiência de desenvolvimento e utilização do [validador eXaminator](/webax/examinator.php), ferramenta automática de validação que desde 2005 é usada pela equipa da [Unidade ACESSO da _FCT_](http://www.acesso.umic.pt/) na **Administração Pública Portuguesa**. O _AccessMonitor_ congrega todos os ensinamentos resultantes do eXaminator, aos quais se associam novas formas de recolha de informação e apresentação dos resultados.

## Funcionalidades do _AccessMonitor_

Assim, no _AccessMonitor_, é possível encontrar as seguintes funcionalidades:

*   **submissão de página web ao estilo dos validadores W3C:** à validação por introdução directa de URI, já existente no eXaminator, o _AccessMonitor_ disponibiliza ainda a validação por introdução directa do código fonte ou por _upload_ de ficheiro (x)HTML existente na máquina do utilizador;
*   **validação tripla:** o _AccessMonitor_ valida, num só passo, a aplicação das WCAG 2.0, a validação das folhas de estilo (CSS 3.0 e CSS 2.1) externas, das regras de estilo inseridas em linha ou no cabeçalho da página (x)HTML e, ainda, a validação do código (x)HTML;
*   **um relatório de acessibilidade imediato:** um relatório qualitativo, em língua portuguesa, que evita o uso de jargão técnico, em que as práticas de concepção encontradas na página se encontram organizadas pelos 3 níveis de prioridade com que os critérios de sucesso se apresentam nas WCAG 2.0.
*   **uma escala quantitativa (índice AccessMonitor):** que pontua as práticas de concepção encontradas na página e que, pela rápida e fácil leitura, notabilizou o seu predecessor eXaminator (“de 1 a 10, quanto valem as práticas que estou a usar na página?”);
*   **uma síntese de resultados de leitura imediata:** dos testes efectuados, quantos apresentam resultados positivos, quantos assinalam erros e quantos apontam a necessidade de uma validação manual. A síntese apresenta os resultados de forma a pôr em clara evidência os erros encontrados e a orientar os utilizadores para a sua correção;
*   **forte carácter pedagógico:** informação detalhada dos testes efectuados, dividos pelos 3 níveis de prioridade dos critérios de sucesso (prioridade ‘A’, prioridade ‘AA’ e prioridade ‘AAA’) de acordo com a nova definição de prioridades constante das WCAG 2.0;
*   **ajuda contextualizada:** apoiada nos 3 documentos essenciais, produzidos pelo W3C para a correcta implementação das directrizes, a ajuda contextualizada conduz o desenvolvedor dos conteúdos à correção dos problemas encontrados e fundamenta os testes efetuados pelo _AccessMonitor_:
    *   [Diretrizes de Acessibilidade para o Conteúdo da Web (WCAG) 2.0 – Recomendação W3C de 11 Dezembro de 2008](/w3/TR/WCAG20/);
    *   [Noções sobre as WCAG 2.0 – Um manual para compreender e implementar as Diretrizes de Acessibilidade para o Conteúdo da Web 2.0](/w3/TR/UNDERSTANDING-WCAG20/);
    *   [Técnicas para as WCAG 2.0 – Técnicas e Falhas para as Diretrizes de Acessibilidade para o Conteúdo da Web 2.0](/w3/TR/WCAG20-TECHS/).
*   **Verificações manuais mais fáceis:** o relatório disponibiliza 3 tipos de visualizações para análise manual das ocorrências:
    *   <img width="15" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/754e15db-1100-4c43-b86e-f1b7d26ae32b">
 uma visão por elemento;
    *   <img width="17" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/1cc8970a-10e8-427b-9f55-5b971ef55589">
 uma visão no código (organizado através do _Document Object Model_) e;
    *   <img width="19" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/2aba8c02-b182-4aa3-8f21-565132579336">
 uma visão das ocorrências sobrepostas na página original.

Tal como sucede atualmente com o eXaminator, também com o _AccessMonitor_ é possível criar diretórios de monitorização de múltiplas páginas de um sítio Web, diretórios de vários sítios de um setor de atividade, bem como proceder à afixação do selo dinâmico de certificação. Se pretende usar o selo dinâmico de certificação, entre em contato com a equipa da ACESSO.

## O relatório qualitativo _AccessMonitor_


O _AccessMonitor_ produz automaticamente um relatório qualitativo por cada página que lhe é submetida.

<img width="1272" alt="Relatório AccessMonitor" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/a55af292-c08c-4ae5-aae5-1cd66ae69ce8">
Figura 1: Recorte do relatório qualitativo _AccessMonitor_.

O relatório está organizado em duas partes:

*   uma breve descrição da amostra recolhida e;
*   uma apresentação exaustiva dos resultados compilados.




<img width="582" alt="Recorte exemplo de uma amostra recolhida pelo AccessMonitor" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/2a28491d-ebd0-43d9-9e96-bfecfd1a8ddf">

Figura 2: detalhe da amostra recolhida fornecida no relatório qualitativo do _AccessMonitor_.

Na primeira parte é possível observar o URI da página, um botão ![botão ver página](/accessmonitor/notatecnica/viewPage.png) “ver página” que liga à página que foi alvo da análise e um botão ![botão ver código](/acceessmonitor/notatecnica/viewCode.png) “ver código” que permite ver o seu código fonte. É ainda possível consultar o **título da página** (elemento `<title>` da página HTML), o **tamanho** em KB, o **número de elementos encontrados** e a **data e hora** a que se procedeu à análise. Relativamente ao número de elementos, deixamos aqui uma nota especial, resultante da nossa experiência com o validador eXaminator:

> “podemos inferir que quanto maior for o número de elementos observados na página, maior é o grau de confiança com que podemos aceitar as indicações fornecidas no relatório. Para um número de elementos inferior a 100 é necessário inspecionar com maior cuidado as afirmações proferidas, aconselhando-se a efectuar sempre uma verificação manual.”
> 
> — Jorge Fernandes / Unidade ACESSO da _FCT_.

Na segunda parte, os resultados encontram-se igualmente divididos em duas secções: uma primeira apresentando um **sumário dos resultados** e uma segunda apresentando um **detalhe exaustivo dos testes** efectuados.  

<img width="882" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/24358d66-7cdc-495f-9b7d-a3af5ecdcc79">

Figura 3: pormenor dos dados que compõem a síntese do relatório _AccessMonitor_.

Do sumário faz parte:

*   **o “índice _AccessMonitor_“**, o qual é uma unidade de valoração utilizada em todos os testes do validador e cujo resultado final sintetiza e quantifica as práticas com vista à acessibilidade expressa nas WCAG 2.0. O índice _AccessMonitor_ é uma herança do [índice _web@x_ do eXaminator](/webax/nota_tecnica_webax.html), o qual inaugurou o uso deste tipo de indicadores quantitativos em validadores de acessibilidade de conteúdos Web. Se em 2005, o eXaminator foi pioneiro no uso de indicadores quantitativos, hoje em dia este tipo de indicador tem sido alvo de discussão académica e é mesmo prática noutros validadores como o [_TAW_](http://www.tawdis.net). A escala de 1 a 10, representando o 10 uma boa prática observada automaticamente, acaba por ser uma escala de apreensão mais imediata e fácil do que a gradação usada pelo W3C com os seus 3 níveis de prioridade, pouco sensível a pequenas correções operadas nos conteúdos.
*   **um quadro que sintetiza os resultados dos testes efectuados**, em que se expressa o número de testes que estão **OK**, dos que contêm **erros**, dos que requerem uma validação manual adicional, assinalados como **avisos**. Os 3 tipos de resultados encontram-se estratificados pelos 3 níveis de prioridade dos critérios de sucesso das WCAG 2.0, ou seja, prioridade ‘A’, prioridade ‘AA’ e prioridade ‘AAA’.


<img width="925" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/6f4aee12-2e74-4e44-9cd5-91b518c2c6c3">

Figura 4: Informação detalhada por teste fornecida no relatório qualitativo _AccessMonitor_.

Os resultados detalhados apresentam todos os testes efectuados, organizados pelos 3 níveis de prioridade das WCAG 2.0. Para cada teste é apresentada a seguinte informação:

Um ícone assinalando se o teste deu <img width="27" alt="ícone OK" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/f1d23850-ce26-4daf-ae5a-0f8475e5f577">
(**OK**) ou <img width="26" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/afe018f6-11a7-4482-a6f0-fc82d76180ac">
(**Erro**), um **título do teste**, uma frase que sintetiza a ocorrência encontrada, uma ligação que permite observar a ocorrência em detalhe (com uma visão por elemento !<img width="20" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/b574a238-79ae-4217-93d0-e57714f85c7a">
, uma visão através do DOM <img width="17" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/ccc6c91a-b80e-4792-b199-bd39e1190d8a">
 e uma visão na página original <img width="15" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/f277e9d3-d293-4e10-b56b-6c112c8efca3">). Surge depois, um pequeno racional que explicita o porquê do teste e qual a orientação geral preconizada nas WCAG 2.0.

Dos 86 testes do _AccessMonitor_, 78 testes entram no cálculo do índice _AccessMonitor_. Os restantes 8 incorporam o relatório qualitativo mas funcionam como **avisos** para validar manualmente. Esses testes surgem identificados no relatório qualitativo pelo símbolo <img width="19" alt="Aviso" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/812fbde3-87b5-4bb8-b8eb-4fb70549ec49">.

<img width="456" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/70faad39-94f4-4dec-8008-170a942bd1f8">

Figura 5: Pormenor do relatório qualitativo – documentação WCAG 2.0 de referência.

Por último, é ainda fornecido um conjunto de documentação WCAG 2.0 de consulta contextualizada, do qual fazem parte a técnica ou falha WCAG 2.0 usada como referência principal pelo teste, a sua descrição, bem como os critérios, ou critério, de sucesso aplicáveis, assim como outras técnicas ou falhas relacionadas. Todas as referências mencionadas no relatório qualitativo do _AccessMonitor_ estão sustentadas, com ligações diretas aos documentos originais, em informação produzida pelo W3C para as WCAG 2.0 e cuja tradução para português esteve a cargo da Unidade ACESSO da _FCT._

Os testes _AccessMonitor_ resultam das WCAG 2.0 do W3C.
-------------------------------------------------------

Dos 61 critérios de sucesso das WCAG 2.0, o _AccessMonitor_ tem, pelo menos, um teste para 30 deles (ver tabela 1). No caso dos critérios de sucesso de prioridade ‘A’ chega mesmo a abranger 64% dos 25 critérios existentes para a conformidade ‘A’.

 <table style="width:100%">
<caption>Tabela 1: Nº de Critérios de Sucesso <abbr title="Web Content Accessibility Guidelines" lang="en">WCAG</abbr> 2.0 abrangidos pelos testes do <em lang="en">AccessMonitor</em> por níveis de prioridade</caption>
<tbody>
<tr>
<th style="width: 40%;" scope="col"></th>
<th style="width: 20%;" scope="col">(A) = Total CS abrangidos pelos Testes AccessMonitor</th>
<th style="width: 20%;" scope="col">(B) = Total CS das WCAG2.0</th>
<th style="width: 20%;" scope="col">(A) / (B)</th>
</tr>
<tr>
<th scope="row">Prioridade ‘A’</th>
<td>16</td>
<td>25</td>
<td>64%</td>
</tr>
<tr>
<th scope="row">Prioridade ‘AA’</th>
<td>5</td>
<td>13</td>
<td>38%</td>
</tr>
<tr>
<th scope="row">Prioridade ‘AAA’</th>
<td>9</td>
<td>23</td>
<td>39%</td>
</tr>
<tr>
<th scope="row">Total</th>
<td>30</td>
<td>61</td>
<td>50%</td>
</tr>
</tbody>
</table>

O _AccessMonitor_ infere o grau de conformidade para com as WCAG 2.0, sendo a sua análise transversal aos 3 níveis de prioridade. Os atuais 86 testes do _AccessMonitor_ não têm uma correspondência biunívoca para com os 61 critérios de sucesso das WCAG 2.0 (i.e. não existe uma relação de um para um). Existem critérios de sucesso para os quais se observa mais do que um teste e há testes que se aplicam a múltiplos critérios de sucesso (ver tabela 2). É importante ter em conta que existem critérios de sucesso para os quais é impossível uma análise automática.

<table style="width:100%">
<caption>Tabela 2: Nº de testes <em lang="en">AccessMonitor</em> por critérios de sucesso e níveis de prioridade</caption>
<tbody>
<tr>
<th style="width: 40%;" scope="col">Critérios de Sucesso WCAG2.0</th>
<th style="width: 10%;" scope="col">Testes ‘A’</th>
<th style="width: 10%;" scope="col">Testes ‘AA’</th>
<th style="width: 10%;" scope="col">Testes ‘AAA’</th>
<th style="width: 10%;" scope="col">Total</th>
</tr>
<tr>
<th scope="row">1.1.1</th>
<td>17</td>
<td></td>
<td></td>
<td>17</td>
</tr>
<tr>
<th scope="row">1.2.1</th>
<td>1</td>
<td></td>
<td></td>
<td>1</td>
</tr>
<tr>
<th scope="row">1.2.8</th>
<td></td>
<td></td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<th scope="row">1.3.1</th>
<td>18</td>
<td></td>
<td></td>
<td>18</td>
</tr>
<tr>
<th scope="row">1.3.2</th>
<td>2</td>
<td></td>
<td></td>
<td>2</td>
</tr>
<tr>
<th scope="row">1.4.3</th>
<td></td>
<td>2</td>
<td></td>
<td>2</td>
</tr>
<tr>
<th scope="row">1.4.4</th>
<td></td>
<td>5</td>
<td></td>
<td>5</td>
</tr>
<tr>
<th scope="row">1.4.5</th>
<td></td>
<td>3</td>
<td></td>
<td>3</td>
</tr>
<tr>
<th scope="row">1.4.6</th>
<td></td>
<td></td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<th scope="row">1.4.8</th>
<td></td>
<td></td>
<td>5</td>
<td>5</td>
</tr>
<tr>
<th scope="row">1.4.9</th>
<td></td>
<td></td>
<td>3</td>
<td>3</td>
</tr>
<tr>
<th scope="row">2.1.1</th>
<td>3</td>
<td></td>
<td></td>
<td>3</td>
</tr>
<tr>
<th scope="row">2.1.3</th>
<td></td>
<td></td>
<td>2</td>
<td>2</td>
</tr>
<tr>
<th scope="row">2.2.1</th>
<td>2</td>
<td></td>
<td></td>
<td>2</td>
</tr>
<tr>
<th scope="row">2.2.2</th>
<td>2</td>
<td></td>
<td></td>
<td>2</td>
</tr>
<tr>
<th scope="row">2.2.4</th>
<td></td>
<td></td>
<td>2</td>
<td>2</td>
</tr>
<tr>
<th scope="row">2.4.1</th>
<td>7</td>
<td></td>
<td></td>
<td>7</td>
</tr>
<tr>
<th scope="row">2.4.2</th>
<td>7</td>
<td></td>
<td></td>
<td>7</td>
</tr>
<tr>
<th scope="row">2.4.4</th>
<td>4</td>
<td></td>
<td></td>
<td>4</td>
</tr>
<tr>
<th scope="row">2.4.5</th>
<td></td>
<td>1</td>
<td></td>
<td>1</td>
</tr>
<tr>
<th scope="row">2.4.6</th>
<td></td>
<td>1</td>
<td></td>
<td>1</td>
</tr>
<tr>
<th scope="row">2.4.9</th>
<td></td>
<td></td>
<td>4</td>
<td>4</td>
</tr>
<tr>
<th scope="row">2.4.10</th>
<td></td>
<td></td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<th scope="row">3.1.1</th>
<td>4</td>
<td></td>
<td></td>
<td>4</td>
</tr>
<tr>
<th scope="row">3.2.1</th>
<td>1</td>
<td></td>
<td></td>
<td>1</td>
</tr>
<tr>
<th scope="row">3.2.2</th>
<td>2</td>
<td></td>
<td></td>
<td>2</td>
</tr>
<tr>
<th scope="row">3.2.5</th>
<td></td>
<td></td>
<td>1</td>
<td>1</td>
</tr>
<tr>
<th scope="row">3.3.2</th>
<td>5</td>
<td></td>
<td></td>
<td>5</td>
</tr>
<tr>
<th scope="row">4.1.1</th>
<td>8</td>
<td></td>
<td></td>
<td>8</td>
</tr>
<tr>
<th scope="row">4.1.2</th>
<td>10</td>
<td></td>
<td></td>
<td>10</td>
</tr>
<tr>
<th scope="row">Total (*)</th>
<td>93</td>
<td>12</td>
<td>20</td>
<td>125</td>
</tr>
</tbody>
</table>
(\*) O total de testes não é igual a 86 uma vez que existem testes que se aplicam a vários critérios de sucesso.

Se analisarmos a distribuição dos 30 testes _AccessMonitor_ (ver tabela 3) pelos 3 níveis de prioridade das WCAG verifica-se que 53% dos testes estão relacionados com verificações de prioridade A, 17% de prioridade AA e 30% de prioridade AAA. O _AccessMonitor_ segue os pesos relativos da distribuição existente nas WCAG 2.0 embora contenha um maior número de testes, em termos relativos, para os critérios de prioridade ‘A’.

<table style="width:100%">
<caption>Tabela 3: Distribuição dos critérios de sucesso <em lang="en">AccessMonitor</em> pelos 3 níveis de prioridade das <abbr title="Web Content Accessibility Guidelines" lang="en">WCAG</abbr> 2.0</caption>
<tbody>
<tr>
<th scope="col">Níveis de prioridade</th>
<th colspan="2" scope="col"><abbr title="Critério de Sucesso">CS</abbr> AccessMonitor</th>
<th colspan="2" scope="col"><abbr title="Critério de Sucesso">CS</abbr> WCAG2.0</th>
</tr>
<tr>
<th scope="row">Prioridade A</th>
<td>16</td>
<td>53%</td>
<td>25</td>
<td>41%</td>
</tr>
<tr>
<th scope="row">Prioridade AA</th>
<td>5</td>
<td>17%</td>
<td>13</td>
<td>21%</td>
</tr>
<tr>
<th scope="row">Prioridade AAA</th>
<td>9</td>
<td>30%</td>
<td>23</td>
<td>38%</td>
</tr>
<tr>
<th scope="row">Total</th>
<td>30</td>
<td></td>
<td>61</td>
<td></td>
</tr>
</tbody>
</table>

O índice _AccessMonitor_ e a fórmula de cálculo
-----------------------------------------------

O AcceMonitor dispõe de um índice numérico, numa escala de 1.0 a 10.0, que tem por objectivo sintetizar num só valor o grau de satisfação dos testes automáticos executados pelo validador. O valor 10.0 é indicativo de uma muito elevada satisfação dos testes executados pelo _AccessMonitor_ aos conteúdos submetidos. O índice sintetiza os resultados verificados numa página ou numa amostra de páginas de um sítio web.

O índice _AccessMonitor_ de uma página ou de um domínio na Internet é uma média ponderada do grau de satisfação dos diversos testes efectuados. No entanto, a ponderação, e mesmo a fórmula de cálculo, depende do tipo de teste.

A ponderação (P) resulta do produto do grau de confiança (U) e do Peso relativo do teste (W):

P=U\*W

O grau de confiança (U) no teste, resulta da experiência de utilização da equipa de desenvolvimento do _AccessMonitor_, nomeadamente pela utilização durante os últimos 5 anos do eXaminator. Assim, quando U=1 significa que o teste é 100% confiável. Quando ele é de 0.9 significa que o teste não é totalmente seguro.

O peso relativo do teste (W) pondera a importância do teste na estrutura organizativa das WCAG2.0 e nos 3 níveis de prioridade com que esta hierarquiza os critérios de sucesso, ou seja: critérios de sucesso de prioridade A, critérios de sucesso de prioridade AA e critérios de sucesso de prioridade AAA (veja tabela seguinte).

<table style="width:100%">
<caption>Tabela 4: Ponderação (W) dos testes consoante os CS das <abbr title="Web Content Accessibility Guidelines" lang="en">WCAG</abbr>2.0 a que pertencem</caption>
<tbody>
<tr>
<th scope="col">Critérios de Sucesso</th>
<th scope="col">Ponderação</th>
</tr>
<tr>
<td>de prioridade A</td>
<td>0.9</td>
</tr>
<tr>
<td>de prioridade AA</td>
<td>0.6</td>
</tr>
<tr>
<td>de prioridade AAA</td>
<td>0.2</td>
</tr>
</tbody>
</table>

A ponderação (W) pode ainda ser modificada caso o teste em presença esteja relacionado com mais do que uma técnica do tipo suficiente ou aconselhada, na definição das WCAG 2.0. Assim, no primeiro caso soma-se, à ponderação que se encontra na tabela anterior, 0.1, e no segundo caso subtrai-se 0.1, dando assim um maior peso às técnicas que o W3C considera suficientes em detrimento das técnicas “meramente” aconselhadas.

No _AccessMonitor_ existem 4 tipos de testes. Esta diversidade de tipos de testes deriva da própria natureza das técnicas e falhas que compõem os critérios de sucesso das WCAG 2.0.

### I) Testes de tipo verdadeiro

Os testes de tipo verdadeiro consistem na validação de uma determinada condição. Se a condição a verificar é verdadeira \[if (C == True)\] o valor do teste (R) resulta da fórmula:

R=S\*P

S é a pontuação “subjectiva” atribuída ao teste. A pontuação “subjectiva” resulta da experiência da equipa de desenvolvimento do _AccessMonitor_. A pontuação “subjectiva” é uma variável determinante, atribuída de acordo com a seguinte escala:

*   **Muito má prática:** 1
*   **Má prática:** 2 ou 3
*   **Prática regular:** 4 ou 5
*   **Boa prática:** 6 ou 7
*   **Muito boa prática:** 8 ou 9
*   **Excelente prática:** 10

**nota**: a conversão de uma apreciação qualitativa em quantitativa (numa escala de 1 a 10) serve de base ao cálculo do índice _AccessMonitor_. O valor (S) inicialmente atribuído é posteriormente ponderado tendo em conta vários factores: prioridade a que pertence o teste, confiança no teste, existência de uma determinada condição, dimensão do problema encontrado.

### II) Testes de tipo falso

Tal como nos testes de tipo verdadeiro também os de tipo falso procuram validar a existência de uma condição. Se a condição a verificar é falsa \[if (C == False)\] o valor do teste (R) resulta da fórmula:

R=S\*P

Ou seja, a fórmula de cálculo deste tipo de testes é exactamente igual à anterior. A única diferença está na verificação da condição (C). Neste caso, o teste é contabilizado quando a condição é falsa, ao passo que no teste anterior, ele é contabilizado quando a condição é verdadeira.

### III) Testes de tipo decrescente

Nos testes do tipo decrescente, entra-se em linha de conta com a ocorrência da condição mas quantifica-se a sua extensão. Quanto maior for a extensão do problema encontrado menor é o valor obtido no teste.

R=(S-(C-T)/Z)\*P

Retirando a variável P (ponderação) cuja fórmula de cálculo é comum aos 4 tipos de testes e cuja decomposição se encontra explicitada acima, ficamos com a seguinte parcela da fórmula:

S-(C-T)/Z

A origem da definição de teste do tipo decrescente reside nesta parcela da fórmula. Ao contrário dos testes I) e II) em que S (pontuação subjectiva) classifica um teste binário, do tipo verdadeiro ou falso, neste caso há necessidade de atribuir também uma pontuação que é variável de acordo com o número de erros encontrados. Neste caso, quando falamos em ocorrência da condição (C) estamos a falar de “número de erros”. Assim, se C > 0 (i.e. existem erros), isto implica, logo à partida, uma determinada pontuação (S), a qual vai decrescendo à medida que o número de erros aumenta. A variável ‘T’ é o nível de tolerância máximo ao erro, ou seja, valor a partir do qual é subtraída a primeira unidade à pontuação de partida ‘S’.

Por exemplo, no caso do teste que verifica quantos erros HTML existem numa página, se tivermos 1 erro, a fórmula tem o seguinte aspecto:

5 – (1 – 10)/10 = 5 + 9/10 = 5 + 0 = 5 (i.e. a pontuação seria a inicial ‘S’ de 5 pontos dado que a tolerância ao erro de 10 não foi ultrapassada.

Se, em vez de 1 erro, fossem localizados 33 erros, então teriamos:

5 – (33 -10)/10 = 5 – 2.2 = 2.8 (i.e., à pontuação inicial ‘S’ de 5 pontos iriamos retirar 2.2 pontos.

### IV) Testes de tipo proporcional

R=S\*(1-C/E)\*P

Retirando a variável P (ponderação) cuja fórmula de cálculo é comum aos 4 tipos de testes e cuja decomposição se encontra explicitada acima, ficamos com a seguinte fórmula:

S\*(1-C/E)

C = nº de elementos de um dado tipo semântico com erro

E = total de elementos de um dado tipo semântico

1-C/E = esta fracção é a que adjectiva o nome do teste, uma vez que ela representa a proporção a subtrair à pontuação subjectiva inicial (S).

Por exemplo, se na recolha forem encontradas 20 imagens das quais 10 não têm legenda, teremos 1-C/E = 1-10/20 = 1-1/2 = 1/2. Se S, pontuação inicial atribuída para a existência de erros deste tipo, for igual a 3, então teremos S\*(1-C/E) = 3\*(1-1/2) = 3/2 = 1.5, ou seja metade da pontuação inicial, o que tem lógica dado o erro estar presente em 50% das imagens encontradas.

<table style="width:100%">
<caption>Tabela 5: Tipo de testes AccessMonitor</caption>
<tbody>
<tr>
<th scope="row">Tipo de Teste</th>
<th>Nº de testes</th>
</tr>
<tr>
<td>Verdadeiro</td>
<td>25</td>
</tr>
<tr>
<td>Falso</td>
<td>14</td>
</tr>
<tr>
<td>Decrescente</td>
<td>24</td>
</tr>
<tr>
<td>Proporcional</td>
<td>23</td>
</tr>
<tr>
<td>Total</td>
<td>86</td>
</tr>
</tbody>
</table>

Por último, a fórmula de cálculo do índice _AccessMonitor_ resulta da divisão do somatório dos diversos resultados dos 4 tipos de testes pelo somatório das respectivas ponderações (ver fórmula síntese abaixo).

Em síntese, a fórmula de cálculo global do índice _AccessMonitor_ tem a seguinte notação:  

<img width="727" alt="image" src="https://github.com/unidade-acesso/unidade-acesso.github.io/assets/27364300/0e0395a9-d56c-4842-b80f-04ab74049b63">


Os índices das variáveis identificadas por t1, t2, t3 e t4 representam respectivamente os 4 tipos de testes do _AccessMonitor_, ou seja: testes do tipo verdadeiro, do tipo falso, do tipo decrescente e do tipo proporcional. A variável P (ponderação) encontra-se explicitada acima.

Bateria de testes
-----------------

[Bateria de testes](/accessmonitor/bateria.php) | Para uma análise detalhada dos 86 testes consulte a bateria de testes.
