# Робота 3 — Тестування в Python

**Студент:** Назар  
**Місто:** Львів  

## Мета роботи
Ознайомитися з основами тестування програм на Python, використанням
`assert`, бібліотеки `unittest`, `pytest` та перевіркою покриття коду.

## Хід роботи
У межах роботи було виконано:
# robota_3.py

class Figure:
    FIGURES = ["квадрат", "прямокутник", "трикутник"]

    def __init__(self, figure_type, length):
        assert length > 0, "Довжина має бути більшою за 0"
        assert figure_type in self.FIGURES, "Недозволений тип фігури"
        self.figure_type = figure_type
        self.length = length

    @property
    def get_figure_type(self):
        return self.figure_type

    @property
    def get_figure_length(self):
        return self.length

    @property
    def get_angles(self):
        if self.figure_type in ["квадрат", "прямокутник"]:
            return 4
        return 3


# ====== UNIT TESTS ======

import unittest


class TestFigure(unittest.TestCase):

    def test_type(self):
        fig = Figure("квадрат", 5)
        self.assertEqual(fig.get_figure_type, "квадрат")

    def test_length(self):
        fig = Figure("трикутник", 3)
        self.assertEqual(fig.get_figure_length, 3)

    def test_angles_triangle(self):
        fig = Figure("трикутник", 4)
        self.assertEqual(fig.get_angles, 3)

    def test_angles_square(self):
        fig = Figure("квадрат", 2)
        self.assertEqual(fig.get_angles, 4)

    def test_invalid_type(self):
        with self.assertRaises(AssertionError):
            Figure("коло", 5)

    def test_invalid_length(self):
        with self.assertRaises(AssertionError):
            Figure("квадрат", 0)


if __name__ == "__main__":
    unittest.main()

## Результати
Реалізований код проходить базові тести, некоректні дані викликають помилки,
а результати тестування можуть бути перевірені через звіти покриття коду.

## Висновок
Тестування є важливим етапом розробки програмного забезпечення, оскільки
дозволяє виявляти помилки, перевіряти коректність логіки програми та
підвищувати надійність коду.
