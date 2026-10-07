в этом репозитории будет находиться анализ анализ статьи https://doi.org/10.1007/s00253-023-12863-z
влияния D-лактата на дрожжи Saccharomyces cerevisiae 

скачиваем файлы 
```
SRR24466389
SRR24466390
SRR24466391
SRR24466377
SRR24466378
SRR24466379
```
команда 
```
nano accessions.txt
for acc in $(cat accessions.txt); do fasterq-dump -A --threads 2 --progress "$acc"; done
```
# RR2026
чтение данных из статьи и проверка их качества производится с помощью следующих скриптов:
read.xlsx("Rt4.xlsx", sheet = 2) — загрузка данных из второго листа Excel-файла Rt4.xlsx в объект test_table.
<img width="1920" height="1080" alt="Снимок экрана (62)" src="https://github.com/user-attachments/assets/bab524b9-a527-45b7-bd0b-175e6abd53dd" />

str(test_table) — вывод структуры таблицы: типы столбцов, количество наблюдений и переменных.
<img width="1481" height="1015" alt="Снимок экрана (64)" src="https://github.com/user-attachments/assets/b273ed13-2dfc-4ae5-a30f-46fba8fca213" />

hist(test_table$OD600_final) — построение гистограммы распределения значений переменной OD600_final.
<img width="1920" height="1080" alt="Снимок экрана 65" src="https://github.com/user-attachments/assets/a0a5f01a-edb6-460c-8fb2-b81d97f0805b" />

shapiro.test(test_table$OD600_final) — проверка нормальности распределения OD600_final с помощью теста Шапиро–Уилка (H₀: данные распределены нормально).
```
	Shapiro-Wilk normality test

data:  test_table$OD600_final
W = 0.98397, p-value = 0.7048
```
