# Projeto Final - Diagnóstico de Distúrbio da Tireoide

Este pacote contém a entrega do projeto final de Ciência de Dados com base no arquivo `Base_M43_Pratique_Hypothyroid.csv`.

## Arquivos

- `Projeto_Final_Diagnostico_Tireoide_executado.ipynb`  
  Notebook completo, com análise exploratória, pré-processamento, modelagem e conclusão.

- `Relatorio_Projeto_Final_Diagnostico_Tireoide.pdf`  
  Relatório final em PDF, pronto para leitura e apresentação.

- `model_comparison.csv`  
  Tabela comparativa das métricas dos modelos testados.

- `threshold_analysis_rf.csv`  
  Avaliação de diferentes thresholds para o modelo Random Forest.

- `data_dictionary_summary.csv`  
  Resumo das colunas, tipos e faltantes.

## Resumo do projeto

- Problema tratado como classificação binária, pois a base entregue possui alvo `binaryClass` com classes `P` e `N`.
- Principais etapas:
  - limpeza da base;
  - tratamento de valores ausentes;
  - análise exploratória visual;
  - pipeline com imputação, padronização e One-Hot Encoding;
  - comparação entre Regressão Logística, Árvore de Decisão e Random Forest;
  - seleção do melhor modelo com foco em recall da classe positiva.

## Modelo final

O melhor resultado foi obtido com **Random Forest**.

## Observação importante

O briefing em vídeo menciona um problema multiclasse com cerca de 9.172 observações e 31 atributos.  
A base efetivamente entregue contém 3.772 registros, 30 colunas e variável-alvo binária.  
Por isso, o projeto foi desenvolvido com base nos dados realmente disponibilizados.
