# laba1

import math

# 1. Запрашиваем у пользователя угол альфа в градусах
alpha_deg = float(input("Введите значение угла альфа (в градусах): "))

# 2. Переводим градусы в радианы для функций модуля math
alpha = math.radians(alpha_deg)

# 3. Вычисление по первой формуле
# z1 = 2 * sin^2(3*pi - 2*alpha) * cos^2(5*pi + 2*alpha)
term1 = math.sin(3 * math.pi - 2 * alpha) ** 2
term2 = math.cos(5 * math.pi + 2 * alpha) ** 2
z1 = 2 * term1 * term2

# 4. Вычисление по второй формуле
# z2 = 1/4 - 1/4 * sin(5/2 * pi - 8*alpha)
z2 = 0.25 - 0.25 * math.sin((5 / 2) * math.pi - 8 * alpha)

# 5. Вывод результатов в консоль
print(f"Результат z1 = {z1:.6f}")
print(f"Результат z2 = {z2:.6f}")

# Проверка на совпадение с использованием math.isclose()
if math.isclose(z1, z2, rel_tol=1e-9, abs_tol=1e-9):
    print("Результаты совпадают!")
else:
    print("Результаты НЕ совпадают!")