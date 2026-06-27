# Pipeline de Analytics do Instagram: Da API da Meta a Insights de Negócios

Projeto desenvolvido para a ONG **Espaço Logos de Cidadania Consciente**, organização que promove projetos educativos, culturais e esportivos para crianças e jovens.
O objetivo deste projeto foi responder uma pergunta simples: **Quais conteúdos geram mais engajamento no Instagram da ONG e quando vale a pena publicá-los?**

Para isso, foi desenvolvido um pipeline de dados que coleta métricas do Instagram via **Instagram Graph API (Meta)**, organiza os dados em uma camada analítica e alimenta dashboards no **Looker Studio**, permitindo que a gestora acompanhe o desempenho das publicações e tome decisões baseadas em dados.

---

## Sobre o Espaço Logos

O Espaço Logos de Cidadania Consciente atua na região da Tijuca (Rio de Janeiro) oferecendo oficinas de educação, cultura e esporte para crianças e jovens em situação de vulnerabilidade, com o objetivo de promover cidadania, cultura e protagonismo juvenil. [Clique aqui](https://espacologos.org.br/) para mais informações.

---

## Arquitetura do Projeto

1. **Coleta de Dados**  
   - Extração das publicações via Instagram Graph API.
   - Coleta de curtidas, comentários, tipo de mídia, data de publicação e permalink.

2. **Enriquecimento**  
   - Consulta em lote (batch) dos indicadores de salvamentos e compartilhamentos.

3. **Camada Raw**  
   - Armazenamento dos dados brutos em Google Sheets via API.

4. **Automação**  
   - Atualização automática semanal utilizando GitHub Actions.

5. **Camada Analítica**  
   - Organização dos dados para consumo pelo Looker Studio.

5. **Visualização**
   - Construção de dashboards orientados à tomada de decisão.
---

## Visualização de Dados com o Looker Studio 

O dashboard foi construído para responder duas perguntas principais:

- O que engaja o público da ONG?
- Quando vale a pena publicar para aumentar esse engajamento?

Todas as visualizações foram escolhidas para responder uma dessas perguntas e transformar dados em recomendações acionáveis para uma usuária sem conhecimento técnico.

![Página 1](dashboard/Espaço_Logos_page-0001.jpg)

## Página 1 – O que engaja nosso público?

A primeira página identifica quais conteúdos geram maior engajamento. As análises respondem perguntas como:
- Qual formato performa melhor?
- O volume de publicações acompanha o desempenho?
- Quais tipos de conteúdo recebem mais curtidas, comentários, salvamentos e compartilhamentos?

Além dos indicadores, cada seção apresenta um insight interpretando os resultados.

### Cards

Os cards apresentam uma visão executiva do cenário geral. Além de indicadores descritivos, destacam rapidamente os dois principais achados da análise:
- o formato com maior engajamento médio
- a principal oportunidade identificada na estratégia atual de conteúdo

A ideia é permitir que a gestora compreenda o panorama do perfil em poucos segundos antes de aprofundar a análise.

### Gráfico de dispersão

O gráfico relaciona duas variáveis importantes:
- quantidade de publicações por formato
- engajamento médio obtido por publicação

Os quadrantes ajudam a identificar oportunidades. Nesse caso, ficou evidente que imagens representam a maior parte do calendário editorial, mas possuem o menor engajamento médio, enquanto vídeos apresentam desempenho superior mesmo sendo publicados com pouca frequência. Essa visualização permite responder rapidamente se a estratégia atual de publicação está alinhada com o comportamento do público.

### Evidências da análise

As tabelas complementam o diagnóstico detalhando como cada formato performa em diferentes tipos de interação. Foram analisadas quatro métricas:
- curtidas
- comentários
- salvamentos
- compartilhamentos

Nesse ponto, a análise utiliza médias por publicação, permitindo comparações mais justas entre formatos com volumes diferentes de postagens. Cada visualização é acompanhada por um insight interpretando os resultados e relacionando-os ao contexto da ONG.

![Página 1](dashboard/Espaço_Logos_page-0002.jpg)

## Página 2 – Quando vale a pena publicar?

A segunda página transforma os resultados em recomendações práticas. Ela apresenta:
- melhores dias para publicação
- melhores horários
- recomendações priorizadas
- hipóteses para validação em ciclos futuros

### Gráficos de barras

Os gráficos mostram como o engajamento médio varia de acordo com:
- dia da semana
- horário de publicação

Como a análise utiliza médias, evita o viés causado pela concentração de publicações em determinados períodos e ajuda a identificar momentos com maior potencial de alcance orgânico.

### Recomendações

A seção de recomendações traduz os resultados em ações práticas. Em vez de apenas apresentar métricas, o dashboard sugere mudanças concretas na estratégia editorial, como:
- diversificar formatos
- aumentar a frequência de vídeos
- priorizar determinados dias e horários de publicação

### Hipóteses para validar

Toda análise gera novas perguntas. Por isso, o dashboard termina propondo hipóteses que podem ser testadas em ciclos futuros de publicação. 

As hipóteses funcionam como ponto de partida para experimentos simples, permitindo validar se mudanças na estratégia realmente aumentam o engajamento do perfil ao longo do tempo visando evolução contínua da estratégia de conteúdo.

## Principais Insights

+ Vídeos apresentam o maior engajamento médio, apesar de representarem uma pequena parcela das publicações.
+ Imagens concentram quase 80% do calendário editorial, mas possuem o menor engajamento médio.
+ Carrosséis apresentam maior média de salvamentos, indicando potencial para conteúdos educativos.
+ Terças, quartas e quintas concentram os maiores níveis médios de engajamento.
+ O período noturno apresentou melhor desempenho médio nas publicações analisadas.


---

## Ferramentas Utilizadas

| Python | Google Sheets | Looker Studio | GitHub Actions |
| :----: | :-----------: | :-----------: | :------------: |
| <a href="https://www.python.org/" target="_blank"><img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" width="100"></a> | <a href="https://www.google.com/sheets/about/" target="_blank"><img src="https://upload.wikimedia.org/wikipedia/commons/3/30/Google_Sheets_logo_%282014-2020%29.svg" width="50"></a> | <a href="https://looker.com/" target="_blank"><img src="https://www.svgrepo.com/show/354012/looker-icon.svg" width="80"></a> | <a href="https://github.com/features/actions" target="_blank"><img src="https://icon.icepanel.io/Technology/svg/GitHub-Actions.svg" width="80"></a> |
