# hse_hw1_meth

## Часть 1
### Per base sequence content

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Pbsc%2073_1.png)
![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Pbsc%2073_2.png)
![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Pbsc%20old.png)

Заметим, что графики выглядят по-разному: 
В  случае (SRR5836473_1) почти отсутствует Цитозин (C),  его гораздо меньше чем в РНК, в отличие от Тимина (T) – его содержание, наоборот, больше, чем в РНК, cодержание Гуанина (G) и Ацетозин (А) же примерно на равном уровне, по сравнению с РНК (SRR3414630_1).

### Per sequence GC content

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/PsGCc%2073_1.png)
![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/PsGCc%2073_2.png)
![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/PbGCc%20old.png)

Видно, что на первом графике наблюдается нормальное распределение, с элементами смещенния.

## Часть 2


## (a), (b) Таблица с числом ридов
### Которые закартированны на участках 11347700-11367700; 40185800-40195800 и процентом дуплицированных прочтений для каждого образца

# [Colab](https://colab.research.google.com/drive/1D5meH77a5aq3I9EfYKwNjglxfTfjAnye#scrollTo=RQAK_lggxsXi)


| BS-Seq | ch11: 11347700-11367700 | ch11: 40185800-40195800 | deduplication |
|:------:|:-----------------------:|:-----------------------:|:-------------:|
| SRR5836473 | 1090 | 464 | 81.69 |
| SRR3824222 | 2328 |	1062|	97.08 |
| SRR5836475 | 1456 | 630 | 90.92 |


## с (Bash)
```
!ls *pe.bam | xargs -P 4 -tI{} deduplicate_bismark  --bam  --paired  -o s_{} {}
```

## (d) M-bias plots
На графиках изображен уровень метилирования каждой возможной позиции в прочтении.  
На оси Y слева видно значение Methylation calls, справа -- пропорцию метилирования. Так как у нас парно-концевая запись, то для каждого запуска представлено 2 разных графика.

## SRR3824222

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Bismark_M-bias%20Read_1_22.png)
![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Bismark_M-bias%20Read_2_22.png)

## SRR5836473

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Bismark_M-bias%20Read_1_73.png)
![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Bismark_M-bias%20Read_2_73.png)

## SRR5836475

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Bismark_M-bias%20Read_1_75.png)
![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Bismark_M-bias%20Read_2_75.png)

## (e) Гистограмы распределения метелирования цитозинов по хромосоме
### SRR3824222 (Epiblast)

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/Epiblast.png)

### SRR5836473 (8 Cell)

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/8cell.png)

### SRR5836475 (ICM)

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/ICM.png)

### Вывод 
Для каждого образца частота и процент метилляции зависят по-разному. Для первого образца чаще всего метилируется 0%,  в 40 процентов случаев. 
Для второго образца чаще всего 100%, что является хорошим показателем, так как метилирование принимает участие в экспрессии гена. 
В третьем образце чаще всего (почти в 60% случаев) метилируется 0% цитозинов.

## (f) Визуализация уровеня метилирования и покрытия для каждого образца

### Уровень метилирования

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/plot_1.png)

### Уровень покрытия

![](https://github.com/NikitaGubanov0/hse_hw1_meth/blob/main/image/plot_2.png)
