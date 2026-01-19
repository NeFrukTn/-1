def factorial(n: int) -> int:
    if n < 0:
        raise ValueError("Факторіал не визначений для від’ємних чисел")

    result = 1
    for i in range(1, n + 1):
        result *= i
    return result
import unittest
from main import factorial


class TestFactorial(unittest.TestCase):

    def test_factorial_positive(self):
        self.assertEqual(factorial(0), 1)
        self.assertEqual(factorial(1), 1)
        self.assertEqual(factorial(5), 120)

    def test_factorial_negative(self):
        with self.assertRaises(ValueError):
            factorial(-3)


if __name__ == "__main__":
    unittest.main()

