# Zhalgas-Practice
#Three lines to make our compiler able to draw:
import sys
import matplotlib
matplotlib.use('Agg')

import pandas as pd
import matplotlib.pyplot as plt
from scipy import stats

# Предположим, что у вас есть столбцы "Cooking_Time" и "Calories" в вашем датасете
kitchen_data = {
    'Cooking_Time': [30, 45, 60, 20, 25, 40, 35, 50, 55, 15],
    'Calories': [300, 450, 600, 200, 250, 400, 350, 500, 550, 150]
}

full_kitchen_data = pd.DataFrame(data=kitchen_data)

x = full_kitchen_data["Cooking_Time"]
y = full_kitchen_data["Calories"]

slope, intercept, r, p, std_err = stats.linregress(x, y)

def myfunc(x):
    return slope * x + intercept

mymodel = list(map(myfunc, x))

plt.scatter(x, y)
plt.plot(x, mymodel)
plt.ylim(ymin=0, ymax=700)
plt.xlim(xmin=0, xmax=70)
plt.xlabel("Cooking_Time")
plt.ylabel("Calories")
plt.title("Линейная регрессия между временем приготовления и калориями на кухне")
plt.show()

#Two lines to make our compiler able to draw:
plt.savefig(sys.stdout.buffer)
sys.stdout.flush()


Array = [500, 100, 7530, 70, 1000, 202, 90, 555, 110, 155]
print(Array)


import pandas as pd
fruits_data = {
    'Фрукт': ['Яблоко', 'Груша', 'Банан', 'Апельсин', 'Киви'],
    'Цвет': ['Красный', 'Желтый', 'Желтый', 'Оранжевый', 'Зеленый'],
    'Вкус': ['Сладкий', 'Сладкий', 'Сладкий', 'Кислый', 'Сладкий'],
    'Количество': [5, 3, 6, 8, 12]
}
fruits_df = pd.DataFrame(data=fruits_data)
print(fruits_df)


weekly_temperatures_celsius = [22, 24, 25, 23, 20, 26, 28]
max_temperature = max(weekly_temperatures_celsius)
print("Максимальная температура за неделю:", max_temperature, "градусов Цельсия")
