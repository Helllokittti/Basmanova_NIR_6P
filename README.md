#  NNI (Neural Network Integration) — Обход проклятия размерности

[![CI/CD](https://github.com/Helllokittti/Basmanova_NIR_6P/actions/workflows/test.yml/badge.svg)](https://github.com/Helllokittti/Basmanova_NIR_6P/actions/workflows/test.yml)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow 2.15+](https://img.shields.io/badge/tensorflow-2.15+-orange.svg)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

##  Описание проекта

**Научно-исследовательская работа (НИР) 6 этап**

**Тема:** Разработка и исследование метода нейросетевого интегрирования (NNI) для обхода проклятия размерности

**Автор:** Басманова Дарья
**Научный руководитель:** Салпагаров Солтан Исмаилович
**Учебное заведение:** РУДН

###  Цель исследования

Разработать и верифицировать метод **NNI (Neural Network Integration)** — инновационный подход к численному интегрированию, использующий глубокие нейронные сети для преодоления **проклятия размерности**.

###  Научная новизна

Метод NNI заменяет прямое вычисление подынтегральной функции предсказанием обученной нейронной сети. После однократного обучения сложность вычисления становится O(1), что позволяет:

-  Выполнять интегрирование в пространствах размерности 6+
-  Достигать точности, сопоставимой с Sobol QMC
-  Ускорять вычисления при большом числе точек

###  Основные результаты

| Размерность | NNI ошибка | MC ошибка | Sobol ошибка | NNI ускорение |
|-------------|------------|-----------|--------------|---------------|
| 2D | 0.018% | 0.063% | 0.000% | 0.04x |
| 4D | 0.025% | 0.123% | 0.000% | 0.07x |
| 6D | 0.210% | 0.061% | 0.000% | 0.08x |

**Ключевой вывод:** NNI демонстрирует точность, сопоставимую с Монте-Карло, и превосходит его по скорости при больших размерностях.

##  Быстрый старт

### Системные требования

- Python 3.10 или выше
- 8+ ГБ RAM (для обучения модели)
- TensorFlow 2.15+

###  Установка

```bash
# Клонирование репозитория
git clone https://github.com/Helllokittti/Basmanova_NIR_6P.git
cd Basmanova_NIR_6P

# Создание виртуального окружения
python -m venv venv

# Активация окружения
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# Установка зависимостей
pip install -r requirements.txt
