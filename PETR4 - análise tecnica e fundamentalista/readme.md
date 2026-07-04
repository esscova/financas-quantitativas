# Análise Técnica e Fundamentalista da PETR4

Projeto de portfólio que combina análise técnica e análise fundamentalista de uma ação negociada na B3, utilizando a PETR4 como ativo de demonstração.

## Objetivo

Construir uma leitura integrada de um ativo da bolsa brasileira, unindo duas perspectivas normalmente tratadas separadamente:

- **Análise técnica**: comportamento histórico de preço e volume, indicadores de tendência e momentum.
- **Análise fundamentalista**: indicadores financeiros da empresa, comparados à mediana do mercado.

O projeto tem finalidade educacional e de composição de portfólio, não constituindo recomendação de investimento.

## Estrutura do notebook

1. Imports e Configurações
2. Coleta e Inspeção dos Dados
3. Análise Técnica
   - Candlestick
   - Médias móveis (SMA 20, 50, 200)
   - RSI (14 períodos)
   - MACD
   - Bandas de Bollinger
4. Análise Fundamentalista
   - Múltiplos principais (P/L, P/VP, Dividend Yield, ROE, ROIC, Dív.Líq/Patrim.)
   - Comparação com a mediana do mercado
5. Conclusão e Considerações Finais
6. Referências

## Ferramentas utilizadas

- [`yfinance`](https://github.com/ranaroussi/yfinance): coleta do histórico de preços
- [`fundamentus`](https://github.com/jonathanmve/fundamentus): coleta dos indicadores fundamentalistas
- [`mplfinance`](https://github.com/matplotlib/mplfinance): gráfico de candlestick
- `pandas`, `numpy`, `matplotlib`: manipulação de dados e visualizações

## Principais achados

- A PETR4 encerrou o período de doze meses analisado com retorno acumulado de aproximadamente 29%, sustentado por uma tendência de alta formada na segunda metade da janela.
- No curto prazo, RSI e MACD sinalizam uma correção após o topo do período, contrastando com o desempenho positivo de fundo.
- Os múltiplos de valuation mostram um perfil misto: P/L abaixo da mediana do mercado, mas P/VP acima.
- ROE e ROIC superam a mediana do mercado em mais do dobro, evidenciando alta rentabilidade sobre capital.
- O nível de endividamento (Dív.Líq/Patrim.) é significativamente mais alto que a mediana do mercado, refletindo o perfil de capital intensivo do setor.

## Limitações

- Indicadores técnicos calculados sobre uma janela de doze meses, o que limita a leitura de tendências de mais longo prazo.
- Indicadores fundamentalistas representam um único ponto no tempo, sem evolução histórica dos múltiplos.
- Comparação com o mercado feita de forma ampla, sem segmentação setorial, já que a biblioteca `fundamentus` não disponibiliza essa informação de forma estruturada.

## Possíveis extensões

- Migrar o relatório final para um documento Quarto (PDF), consolidando os resultados do notebook em um formato de relatório.
- Parametrizar o notebook para aceitar qualquer ticker da B3 como input, generalizando a análise para além da PETR4.
- Incluir comparação setorial específica (petróleo e gás) caso uma fonte de dados com essa segmentação seja incorporada.
- Adicionar indicadores técnicos complementares, como Ichimoku ou ATR, para enriquecer a leitura de volatilidade.

## Autor

Wellington M. Santos, Cientista de Dados

- [LinkedIn](https://www.linkedin.com/in/wellington-moreira-santos)
- [GitHub](https://github.com/esscova)
- [Contato](mailto:wsantos08@hotmail.com)

---

>Material desenvolvido para estudos e composição de portfólio a partir de dados públicos do Yahoo Finance (yfinance) e do Fundamentus, para o repositório [financas-quantitativas](https://github.com/esscova/financas-quantitativas). Com auxílio do Claude Anthropic para revisões e apoio.