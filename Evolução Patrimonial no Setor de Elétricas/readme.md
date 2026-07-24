# Evolução Patrimonial no Setor Elétrico Brasileiro

Análise da evolução do Patrimônio Líquido Consolidado de cinco empresas do setor elétrico brasileiro entre 2020 e 2025, a partir de dados abertos da CVM.

## Objetivo

Este projeto busca responder a uma pergunta simples, mas pouco explorada em exercícios introdutórios: como o Patrimônio Líquido de diferentes empresas de um mesmo setor evolui ao longo do tempo, e em que ritmo. Em vez de olhar para um único balanço isolado, o projeto constrói um painel histórico de seis anos para cinco companhias com perfis distintos dentro do setor elétrico, geração e distribuição, com Cemig, Copel e CPFL, e transmissão, com Taesa e ISA Energia Brasil. Essa comparação horizontal permite identificar não apenas quem é maior em determinado ano, mas quem está crescendo mais rápido, o que um recorte de um único período não revela.

## Sobre o Dataset

[Dados Abertos da CVM, conjunto DFP](https://dados.cvm.gov.br/dataset/cia_aberta-doc-dfp), Comissão de Valores Mobiliários. O projeto utiliza o Balanço Patrimonial Passivo Consolidado de todas as companhias abertas entre 2020 e 2025, totalizando 630.845 registros brutos. Após o filtro do exercício mais recente de cada ano e a seleção das cinco empresas de interesse, a base final para a conta de Patrimônio Líquido Consolidado reúne 30 registros, cinco empresas ao longo de seis anos.

## Metodologia

1. **Coleta**: download automatizado, via `wget`, dos arquivos de DFP de 2020 a 2025 no portal de dados abertos da CVM, com extração via `zipfile`.
2. **Consolidação**: leitura do Balanço Patrimonial Passivo Consolidado de cada ano e concatenação em um único dataframe, com marcação do ano de referência.
3. **Limpeza e Tratamento**: conversão de tipos, datas e valores numéricos, e filtro dos registros do exercício mais recente de cada ano.
4. **Filtragem das empresas**: identificação e seleção das cinco holdings de interesse por nome e código CVM, descartando subsidiárias e segmentos operacionais reportados separadamente.
5. **Isolamento da conta de Patrimônio Líquido**: filtragem da conta 2.03, Patrimônio Líquido Consolidado, para as cinco empresas ao longo dos seis anos.
6. **Construção do painel e cálculo da variação**: reorganização dos dados em painel empresas por anos e cálculo da variação percentual acumulada com 2020 como ano base.

## Principais Resultados

| Métrica | Valor |
|---|---|
| Período analisado | 2020 a 2025 |
| Empresas comparadas | Cemig, Copel, CPFL, Taesa e ISA Energia Brasil |
| Maior variação acumulada até 2025 | CPFL Energia, 65,1% |
| Menor variação acumulada até 2025 | Copel, 14,0% |

### Variação percentual acumulada por empresa, 2020 a 2025

| Empresa | Variação acumulada |
|---|---|
| CPFL Energia | 65,1% |
| Cemig | 63,5% |
| ISA Energia Brasil | 51,8% |
| Taesa | 26,3% |
| Copel | 14,0% |

A Copel se destaca por ser a única empresa com trajetória não monótona no período, registrando queda de Patrimônio Líquido tanto em 2022 quanto em 2025, mesmo tendo iniciado 2020 como a maior das cinco em valor absoluto.

## Tecnologias Utilizadas

- Python
- pandas (`concat`, `pivot`, `to_numeric`)
- wget
- zipfile
- matplotlib

## Referências

* Videoaula [Coletando e Analisando Dados do Balanço Patrimonial em Python](https://youtu.be/YnsQ6fo10sM?si=SbNQaNvdJ97Dmibo), Análise Macro, Luiz Henrique Barbosa Filho.
* Dataset [Dados Abertos da CVM, conjunto DFP](https://dados.cvm.gov.br/dataset/cia_aberta-doc-dfp), CVM.
* Documentação [pandas](https://pandas.pydata.org/docs/).
* Documentação [matplotlib](https://matplotlib.org/stable/).

## Autor

**Wellington M. Santos**, Cientista de Dados

[LinkedIn](https://www.linkedin.com/in/wellington-moreira-santos) · [GitHub](https://github.com/esscova) · [Contato](mailto:wsantos08@hotmail.com)

---

> Material desenvolvido para estudos e composição de portfólio a partir da videoaula
> [Coletando e Analisando Dados do Balanço Patrimonial em Python](https://youtu.be/YnsQ6fo10sM?si=SbNQaNvdJ97Dmibo),
> de Análise Macro, para o repositório
> [financas-quantitativas](https://github.com/esscova/financas-quantitativas);
> com auxílio do Claude Anthropic para revisões e estruturação.