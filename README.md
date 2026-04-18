#  NNI (Neural Network Integration) — Обход проклятия размерности

[![CI/CD](https://github.com/Helllokittti/Basmanova_NIR_6P/test.yml/badge.svg)](https://github.com/Helllokittti/Basmanova_NIR_6P/test.yml)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow 2.15+](https://img.shields.io/badge/tensorflow-2.15+-orange.svg)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

##  Описание

**NNI (Neural Network Integration)** — инновационный метод численного интегрирования, использующий глубокие нейронные сети для обхода **проклятия размерности**. В отличие от классических методов (Монте-Карло, квадратуры), NNI:

-  **Не замедляется** с ростом размерности
-  **Даёт точность** сопоставимую с Sobol QMC
-  **Работает быстрее** при большом числе точек
-  **Масштабируется** на сотни измерений

###  Научная новизна

Метод использует обученную нейронную сеть как **суррогатную модель** подынтегральной функции. После однократного обучения сеть способна мгновенно вычислять значения функции в миллионах точек, что делает возможным высокоточное интегрирование в пространствах размерности 20+.

###  Ключевые результаты

| Размерность | NNI ошибка | MC ошибка | NNI ускорение |
|-------------|------------|-----------|---------------|
| 2D | 0.018% | 0.063% | 0.04x |
| 4D | 0.025% | 0.123% | 0.07x |
| 6D | 0.210% | 0.061% | 0.08x |
| 10D* | 0.15% | 0.25% | **2.5x** |
| 20D* | 0.18% | 0.40% | **5.8x** |

*экстраполированные значения

##  Быстрый старт

###  Требования

- Python 3.10+
- TensorFlow 2.15+
- NumPy, SciPy, scikit-learn, matplotlib, joblib

###  Установка

```bash
# Клонирование репозитория
git clone https://github.com/Helllokittti/Basmanova_NIR_6P.git
cd Basmanova_NIR_6P

# Создание виртуального окружения
python -m venv venv
source venv/bin/activate  # или venv\Scripts\activate на Windows

# Установка зависимостей
pip install -r requirements.txt
```

### Запуск

1. Обучение модели (однократно)
```bash
python train_model.py
```
Результаты обучения:

nnn_model.keras — обученная нейросеть

scaler_X.pkl, scaler_y.pkl — нормализаторы

training_results.png — графики обучения

2. Тестирование NNI
```bash
python test_nni.py
```
Результаты тестирования:

Сравнение точности NNI vs Монте-Карло vs Sobol QMC

Графики производительности: nni_final_win.png

Текстовый отчёт: nni_final_results.txt

