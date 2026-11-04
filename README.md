# Tireoide — estudo acadêmico de classificação
**João Vitor Marinho · Formação em Ciência de Dados — EBAC**

Estudo de classificação binária com preparação de dados, comparação de modelos e análise de limiar. O objetivo desta versão é documentar o experimento e os pontos que precisam de validação.

## Dados e escopo

A base fornecida no curso contém **3.772 registros**, 30 colunas e o alvo `binaryClass`: 3.481 registros `P` e 291 `N`. O código mapeia `P → 1` e `N → 0`; o significado clínico desses códigos precisa ser confirmado na documentação da fonte.

O briefing descrevia um problema multiclasse com cerca de 9.172 observações e 31 atributos. O notebook trabalha com a base binária efetivamente recebida. O CSV não está publicado neste repositório.

## Método e resultados históricos

Imputação e codificação são ajustadas em pipelines com os dados de treino. O experimento usa divisão estratificada de 80%/20%, com `random_state=42`.

| Modelo | Acurácia | Precisão (classe 1) | Recall (classe 1) | F1 | ROC-AUC |
| --- | ---: | ---: | ---: | ---: | ---: |
| Regressão Logística | 0,9775 | 0,9971 | 0,9785 | 0,9877 | 0,9928 |
| Árvore de Decisão | 0,9974 | 1,0000 | 0,9971 | 0,9986 | 0,9986 |
| Random Forest | 1,0000 | 1,0000 | 1,0000 | 1,0000 | 1,0000 |

São saídas salvas da execução original, sem nova execução nesta revisão. O teste contém 755 registros: 697 da classe 1 e 58 da classe 0.

**O resultado perfeito precisa ser auditado.** Ele não comprova generalização nem utilidade clínica. A comparação dos modelos, a seleção do melhor e a exploração dos limiares usam o mesmo conjunto de teste, que deixa de funcionar como avaliação final independente.

## Validação pendente

- Confirmar a origem dos dados e a semântica das classes.
- Verificar duplicatas, registros do mesmo paciente em partições diferentes e atributos que revelem o desfecho.
- Separar treino, validação para seleção de modelo/limiar e teste final intocado.
- Comparar com um classificador de referência e avaliar ambas as classes, calibração e incerteza.

O estudo não foi validado para diagnóstico ou decisão clínica.

## Arquivos

- [Notebook](./Projeto%20tireoide.ipynb): análise, pipelines e resultados históricos.
- [Relatório original](./Relatorio%20Projeto%20tireoide.pdf): documento da entrega acadêmica; deve ser lido com as ressalvas desta revisão.

## Como preparar a execução

```bash
git clone https://github.com/jvickz/Projeto-Tireoide-.git
cd Projeto-Tireoide-
python -m pip install -r requirements.txt
python -m jupyter notebook
```

Obtenha o arquivo original disponibilizado no curso, respeitando seus termos de uso, e coloque-o em `data/Base_M43_Pratique_Hypothyroid.csv`. Alternativamente, defina a variável de ambiente `THYROID_DATA_PATH` com o caminho do arquivo.

Abra o notebook a partir da raiz do repositório. A célula de leitura informa claramente quando o arquivo está ausente. O ambiente ainda não possui versões de dependências fixadas; resultados podem variar entre versões.


