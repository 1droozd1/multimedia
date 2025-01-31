# Лабораторные работы по предмету "Методы, средства и технологии мультимедиа"
Работу выполнил\
Студент группы: М8О-407Б-21\
Дубровин Дмитрий Константинович

## Выбор датасета

Я выбрал датасет, содержащий данные о химическом составе различных вин. Этот датасет можно использовать как для классификации, так и для регрессии. Для классификации мы можем выделить несколько классов качества вина (например, 0 - низкое качество, 1 - среднее, 2 - высокое качество). Также этот датасет не содержит пропусков, что упрощает работу.

**Классификация**: задача классификации качества вина.
**Регрессия**: задача предсказания точного значения качества вина.

**Метрики для оценки**:
 - Для классификации: Accuracy, F1-Score.
 - Для регрессии: MSE, R², MAE.

**Для классификации**:
* ```Accuracy (Точность)```: Эта метрика показывает долю правильно классифицированных примеров. Применяется, если классы сбалансированы и важна общая точность классификации.
* ```F1-Score```: Этот показатель является средним гармоническим точности и полноты. Подходит, когда классы несбалансированы, и важно минимизировать как ложноположительные, так и ложносогласные ошибки.

**Для регрессии**:
* ```Mean Squared Error (MSE)```: Среднеквадратичная ошибка используется для измерения разницы между предсказанными и реальными значениями. Это хорошая метрика для оценки точности модели в задачах регрессии.
* ``R² (Коэффициент детерминации)``: Это метрика, которая оценивает, какая доля вариации целевой переменной объясняется моделью. R² близкий к 1 означает хорошую модель.
* ```Mean Absolute Error (MAE)```: Средняя абсолютная ошибка также используется для оценки отклонений между предсказанными и реальными значениями.

**Практическая значимость**: Прогнозирование качества вина является реальной задачей, используемой в виноделии, чтобы оценить, какие химические компоненты оказывают влияние на качество.

***Таблица 1 Метрика качества на тестовом наборе данных***

| Алгоритм | Задача | Бейзлайн | Улучшенный бейзлайн | Самостоятельная имплементация алгоритма |
| ---------| ------ | -------- | ------------------- | --------------------------------------- |
| ```KNN``` | Классификация | Accuracy: 0.8562, F1 Score: 0.30303 | Accuracy: 0.88125, F1 Score: 0.5128 | Accuracy: 0.88125, F1 Score: 0.5128|
| | Регрессия | MSE: 0.5320, MAE: 0.5788, R²: 0.1859 | MSE: 0.3689, MAE: 0.4901, R²: 0.4355 | MSE: 0.3689, MAE: 0.4901, R²: 0.4355
| ```Линейные модели``` | Классификация | Accuracy: 0.8656, F1-Score: 0.3768 | Accuracy: 0.8594, F1-Score: 0.3077 | Accuracy: 0.8625, F1-Score: 0.3125 |
| | Регрессия | MSE: 0.3900, MAE: 0.5035, R²: 0.4032 | MSE: 0.3900, MAE: 0.5036, R²: 0.4032 | MSE: 0.3899, MAE: 0.5035, R²: 0.4034 |
| ```Решающее дерево``` | Классификация | Accuracy: 0.8719, F1-Score: 0.8689 | Accuracy: 0.8594, F1-Score: 0.8344 | Accuracy: 0.8969, F1-Score: 0.5926 |
| | Регрессия | MSE: 0.6125, MAE: 0.4625, R²: 0.0627 | MSE: 0.4400, MAE: 0.5062, R²: 0.3267 | MSE: 0.4062, MAE: 0.4890, R²: 0.3784 |
| ```Случайный лес``` | Классификация | Accuracy: 0.9000, F1-Score: 0.6000 | Accuracy: 0.9031, F1-Score: 0.6076 | Accuracy: 0.8562, F1-Score: 0.3429 |
| | Регрессия | MSE: 0.3012, MAE: 0.4224, R²: 0.5390 | MSE: 0.3059, MAE: 0.4251, R²: 0.5319 | MSE: 0.3731, MAE: 0.4916, R²: 0.4291 |
| ```Градиентный бустинг``` | Классификация | Accuracy: 0.8812, F1-Score: 0.5250 | Accuracy: 0.8938, F1-Score: 0.6047 | Accuracy: 0.8750, F1-Score: 0.3548 |
| | Регрессия | MSE: 0.3623, MAE: 0.4849, R²: 0.4456 | MSE: 0.3454, MAE: 0.4554, R²: 0.4715 | MSE: 0.3630, MAE: 0.4858, R²: 0.4445 |

## Вывод

1. **Классификация**: Лучшие результаты показали ансамблевые методы — **Случайный лес** (Accuracy: 0.9031, F1-Score: 0.6076) и **Градиентный бустинг** (Accuracy: 0.8938, F1-Score: 0.6047). KNN значительно улучшился после настройки гиперпараметров.

2. **Регрессия**: Лидером стал **Случайный лес** (MSE: 0.3012, R²: 0.5390), близкие результаты у **Градиентного бустинга**. KNN и линейные модели уступают по качеству.

3. **Общее**: Ансамблевые методы эффективны в прогнозировании качества вина. Самостоятельные реализации моделей близки к готовым, но могут уступать в сложных задачах.