# Прогнозирование вероятности отчисления студентов
Работа посвящена проблеме высокого процента отчислений студентов. Основная цель исследования - разработка метода для прогнозирования вероятности отчисления студентов. В исследовании были рассмотрены различные алгоритмы рекуррентной нейронной сети, включая такие модификации, как GRU и LSTM. Оценка производительности моделей проводилась с помощью ROC-кривых, accuracy, recall, f1_score. 
  
Базовая модель, которую мы использовали в нашей работе, представляла собой рекуррентную нейронную сеть (RNN) с функцией активации гиперболического тангенса. Для предотврашения переобучения мы использовали слой дропаута с коэффициентом 0.1. Для получения вероятности класса мы использовали функцию активации сигмоиду. В качестве метрики для оценки модели мы применяли бинарную кросс-энтропию, а в качестве оптимизатора использовали Adam. Результаты базовой модели приведены в таблице 1.

| Модель      | Accuracy | Precision | Recall | F1-score | AUC-ROC |
|-------------|----------|-----------|--------|----------|---------|
| Basic RNN   | 78%      | 89%       | 70%    | 77%      | 81%     |
| GRU         | 80%      | 93%       | 68%    | 79%      | 83%     |
| LSTM        | **83%**      | **93%**       | **74%**    | **83%**      | **84%**     |

До третьего этапа тестирования наш подход к оценке успеха студентов ограничивался анализом их результатов только в последнем семестре. Однако в ходе третьего этапа тестирования мы внесли изменения, начав оценивать метрики по отдельным семестрам. Результаты представлены в Таблице 3.
| Модель          | Accuracy | Precision | Recall | F1-score | AUC-ROC |
|-----------------|----------|-----------|--------|----------|---------|
| **1 семестр**   |          |           |        |          |         |
| Basic RNN       | 76%      | 71%       | 79%    | 75%      | 76%     |
| GRU             | 73%      | 65%       | 86%    | 74%      | 76%     |
| LSTM            | 75%      | 73%       | 72%    | 72%      | 76%     |
| **2 семестр**   |          |           |        |          |         |
| Basic RNN       | 96%      | 76%       | 75%    | 76%      | 80%     |
| GRU             | 77%      | 69%       | 78%    | 73%      | 78%     |
| LSTM            | 79%      | 75%       | 73%    | 74%      | 80%     |
| **3 семестр**   |          |           |        |          |         |
| Basic RNN       | 84%      | 76%       | 68%    | 72%      | 79%     |
| GRU             | 82%      | 72%       | 69%    | 70%      | 78%     |
| LSTM            | 82%      | 72%       | 68%    | 70%      | 79%     |
| **4 семестр**   |          |           |        |          |         |
| Basic RNN       | 86%      | 71%       | 62%    | 66%      | 77%     |
| GRU             | 85%      | 69%       | 63%    | 66%      | 77%     |
| LSTM            | 85%      | 67%       | 64%    | 65%      | 79%     |
| **5 семестр**   |          |           |        |          |         |
| Basic RNN       | 90%      | 77%       | 63%    | 70%      | 81%     |
| GRU             | 89%      | 70%       | 63%    | 66%      | 79%     |
| LSTM            | 89%      | 70%       | 65%    | 68%      | 82%     |
| **6 семестр**   |          |           |        |          |         |
| Basic RNN       | 93%      | 76%       | 59%    | 66%      | 81%     |
| GRU             | 93%      | 71%       | 63%    | 67%      | 79%     |
| LSTM            | 92%      | 68%       | 54%    | 60%      | 79%     |
| **7 семестр**   |          |           |        |          |         |
| Basic RNN       | 95%      | 74%       | 65%    | 69%      | 84%     |
| GRU             | 95%      | 69%       | 63%    | 66%      | 83%     |
| LSTM            | 95%      | 69%       | 63%    | 66%      | 84%     |
| **8 семестр**   |          |           |        |          |         |
| Basic RNN       | 96%      | 67%       | 66%    | 67%      | 85%     |
| GRU             | 96%      | 69%       | 67%    | 68%      | 84%     |
| LSTM            | 96%      | 68%       | 68%    | 68%      | 85%     |



