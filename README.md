# Análise de Previsão de Notas de Alunos

<img align="center" alt="html5" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />

![kaggle estudantes](https://github.com/user-attachments/assets/148c4f51-6e1d-4c68-91b6-2b2832c2513b)

### 1. Entendimento do Negócio

[Base de dados do Kaggle]('https://www.kaggle.com/datasets/haseebindata/student-performance-predictions/data')

_Análise Desenvolvida por: Ramon Mendes_

O **Conjunto de Dados de Desempenho Estudantil** foi criado para avaliar e prever os resultados dos alunos com base em diversos fatores que podem influenciar o sucesso acadêmico. Esse conjunto de dados sintético inclui características que são comumente consideradas em pesquisas educacionais e cenários do mundo real, como frequência, hábitos de estudo, desempenho acadêmico anterior e participação em atividades extracurriculares. O objetivo é entender como esses fatores se correlacionam com as notas finais dos alunos e construir um modelo preditivo que possa prever o desempenho dos estudantes.

**Características do Conjunto de Dados:**
- **StudentID**: Um identificador único para cada aluno.
- **Nome**: O nome do aluno.
- **Gênero**: O gênero do aluno (Masculino/Feminino).
- **Taxa de Frequência**: A porcentagem de aulas frequentadas pelo aluno.
- **Horas de Estudo por Semana**: O número de horas que o aluno passa estudando a cada semana.
- **Nota Anterior**: A nota que o aluno alcançou no semestre anterior (de 0 a 100).
- **Atividades Extracurriculares**: O número de atividades extracurriculares em que o aluno está envolvido.
- **Apoio dos Pais**: Uma avaliação qualitativa do nível de apoio fornecido pelos pais do aluno (Alto/Médio/Baixo).
- **Nota Final**: A nota final do aluno (de 0 a 100), que serve como a variável-alvo para a previsão.

**Casos de Uso:**
- **Previsão de Desempenho Estudantil**: O conjunto de dados pode ser usado para construir modelos de aprendizado de máquina que preveem a nota final dos alunos com base nas outras características. Isso pode ajudar educadores a identificar alunos que podem precisar de apoio adicional para melhorar seus resultados.

# Conclusão:

O **Conjunto de Dados de Desempenho Estudantil** é uma ferramenta versátil para educadores, cientistas de dados e pesquisadores interessados em entender e prever o sucesso dos alunos. Ao analisar esses dados, os envolvidos podem obter valiosos insights sobre os fatores que contribuem para o desempenho acadêmico e desenvolver estratégias para melhorar os resultados educacionais.

Foram Treinados de um mesmo conjunto de dados dois modelo partindo da **Regressão Linear Múltipla** para prever através do comportamento do aluno qual é a possível nota em um semestre/prova/ano que pode alcançar.

Após a **Análise Exploratória dos Dados** não foi encontrado _out liers_ nas notas dos alunos, porém, foi visto uma distribuição alta de notas entre 85 - 90 e uma correlação entre _'AttendanceRate'_ e _'FinalGrade'_.

**[1]** O treinamento do **Modelo 1** obtivemos:

    R²: 0.6574610769258501
    MAE: 3.842068530775805
    MSE: 21.237413230597294
    RMSE: 4.608406799599759

**[2]** Enquanto no treinamento do **Modelo 2** obtivemos:

    R2: 0.9900207610042044
    MAE: 0.764857881136957
    MSE: 0.6187128177393232
    RMSE: 0.786583001176178

  **[3]** Coeficientes antes da exclusão das colunas  _'AttendanceRate' [ 0.24510334], 'StudyHoursPerWeek'_ [-0.53621842]:
  
  **Coeficientes:** [ 0.24510334, -0.53621842, 1.02232203, 1.68929826, 1.27426381, 2.0141159, 1.36902269]

Podemos observar um melhor desenpenho no **Modelo 2** com o **R²** alto e **RMSE** baixo após retirada das colunas  _'AttendanceRate', 'StudyHoursPerWeek'_ no _dataset [3], visto que, os **coeficientes** das duas colunas estavam baixos e o **R²** apresentou uma taxa baixa no *Modelo 1**, conforme observamos acima [1].

Apesar dos dados serem fictícios (extraídos do site da Kaggle), podemos observar como a escolha de manter ou não colunas no modelo de dados interfere positiva ou negativamente no desenpenho modelo. Cabe também ressaltar a importância no entendimento do _business_ que auxilia na tomada da decisão de manter ou não, caso tivessemos que manter a escolha por outro _modelo de machine learning_ poderia ser uma melhor escolha.
