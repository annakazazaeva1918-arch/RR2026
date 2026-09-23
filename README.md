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
