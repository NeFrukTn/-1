# Робота 2
# Основи програмування на Python
# Місто: Львів
# Імʼя: Назар

# Основні типи даних
text = "Привіт, Python"
num = 5
lst = [1, "a", 2.5]
dct = {"імʼя": "Назар", "місто": "Львів"}

print(text, num, lst, dct)

# Вбудовані константи та функції
print(True)
print("abs(-10) =", abs(-10))

# Цикл
for i in range(3):
    print("Ітерація:", i)

# Розгалуження
if num > 0:
    print("Число додатне")
else:
    print("Число відʼємне")

# Обробка помилок
try:
    print(10 / 0)
except Exception as e:
    print("Помилка:", e)
finally:
    print("Кінець блоку try")

# Контекст-менеджер
with open(__file__, "r", encoding="utf-8") as f:
    print("Файл успішно відкрито")

# Lambda
hello = lambda name: f"Привіт, {name}!"
print(hello("Назар"))
