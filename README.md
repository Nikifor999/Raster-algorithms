# Иллюстрация работы базовых растровых алгоритмов

## Описание задачи

Приложение визуализирует работу следующих базовых растровых алгоритмов:
1. Пошаговый алгоритм (Step-by-Step) — базовый метод рисования линии.
2. Цифровой дифференциальный анализатор (DDA) — алгоритм рисования линии с использованием интерполяции.
3. Алгоритм Брезенхема для линии — эффективный метод, использующий целочисленные вычисления.
4. Алгоритм Брезенхема для круга — для построения окружностей.

Приложение включает интерактивный интерфейс с возможностью масштабирования, ввода координат и выбора алгоритма, а также отображает координатную сетку с дискретными точками.

---

## Основные функции

### Визуализация алгоритмов

Алгоритмы построения работают следующим образом:
- Step-by-Step Line: Линия строится поэтапно, на каждом шаге изменяется одна координата.
- DDA Line: Использует линейную интерполяцию для вычисления промежуточных координат.
- Bresenham Line: Оптимизированный метод с использованием целочисленной арифметики.
- Bresenham Circle: Построение окружности с минимизацией вычислений за счет симметрии.

### Масштабирование

Пользователь может изменять масштаб отображения сетки с помощью клавиш + и -. Все элементы перерисовываются в соответствии с новым масштабом.

### Графический интерфейс

Интерфейс включает:
- Поля ввода координат (x0, y0, x1, y1) и радиуса для круга.
- Переключатель алгоритмов через выпадающий список.
- Кнопки для рисования и очистки холста.
- Интерактивную работу с масштабированием.

---

## Временные характеристики алгоритмов

Алгоритмы были протестированы на данных различной длины. Результаты:

| Алгоритм               | Время (в секундах)   | Зависимость от длины |
|------------------------|----------------------|----------------------|
| Step-by-Step Line  | ~0.02                | Линейная             |
| DDA Line           | ~0.015               | Линейная             |
| Bresenham Line     | ~0.01                | Линейная             |
| Bresenham Circle   | ~0.012               | Пропорциональная радиусу |

---

## Удобство интерфейса

1. Масштабирование:  
   Возможность увеличивать или уменьшать масштаб для детального изучения алгоритмов.
   
2. Привязка к координатам:  
   Сетка визуализирует дискретную координатную систему, облегчающую анализ.
   
3. Выбор алгоритмов:  
   Удобное переключение между методами через выпадающий список.

4. Валидация ввода:  
   Предупреждения выводятся при некорректных данных, предотвращая ошибки.

---

## Сравнительная характеристика алгоритмов

| **Характеристика**         | **Пошаговый алгоритм**                   | **Цифровой дифференциальный анализатор (ЦДА)** | **Алгоритм Брезенхема (прямая)**      | **Алгоритм Брезенхема (окружность)** |
|-----------------------------|------------------------------------------|-----------------------------------------------|---------------------------------------|---------------------------------------|
| **Принцип работы**         | Перебирает все точки по оси координат и вычисляет соответствующую вторую координату | Использует линейную интерполяцию по приращению одной из координат | Использует целочисленные вычисления и проверку ошибок для определения ближайшей точки | Аналогично алгоритму Брезенхема для прямой, но с учётом симметрии окружности |
| **Тип данных**             | Работает с числами с плавающей точкой    | Работает с числами с плавающей точкой         | Использует целые числа               | Использует целые числа               |
| **Скорость работы**        | Медленный из-за большого количества вычислений | Быстрее пошагового, но медленнее Брезенхема  | Очень быстрый за счёт целочисленных операций | Быстрый за счёт оптимизаций         |
| **Точность**               | Высокая                                  | Высокая                                       | Высокая                              | Высокая                              |
| **Сложность реализации**   | Простая                                  | Простая                                       | Сложнее ЦДА                          | Сложнее версии для прямой            |
| **Область применения**     | Простые задачи, где производительность не критична | Простейшие отрезки                           | Рисование отрезков с высокой скоростью и точностью | Рисование окружностей в компьютерной графике |
| **Основное преимущество**  | Лёгкость понимания и реализации          | Простота и улучшенная производительность по сравнению с пошаговым | Высокая производительность и отсутствие ошибок округления | Высокая производительность и симметрия |
| **Основной недостаток**    | Низкая производительность                | Может давать визуальные артефакты при больших значениях координат | Сложность понимания                  | Сложность расчётов из-за необходимости работы с криволинейными координатами |

### Выводы:
1. **Пошаговый алгоритм**: подходит для начального понимания работы с графикой, но практически не используется из-за низкой производительности.
2. **Алгоритм ЦДА**: лучше для рисования линий, так как работает быстрее, но использует операции с плавающей точкой.
3. **Алгоритм Брезенхема для прямых**: стандартное решение для отрисовки отрезков благодаря скорости и точности.
4. **Алгоритм Брезенхема для окружностей**: оптимизирован для работы с симметрией окружности, применяется для криволинейных объектов.



## Как запустить

1. Убедитесь, что установлен Python версии 3.7 или выше.
2. Установите зависимости, если необходимо (например, tkinter).
3. Запустите файл командой:  
   ```bash
   python application.py
