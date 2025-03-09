# Домашнее задание весна №2

## Данные:
    * Гистоновая метка: H3K4me1
    * Клеточная линия: SK_N-SH
    * Реплика 1: ENCFF436WIU
    * Реплика 2: ENCFF005JXT

Ссылка на тетрадку: [https://colab.research.google.com/drive/1OT6iWlQWoBWUgF2p0lcDzlcx1gItRXm4?usp=sharing](https://colab.research.google.com/drive/1bbD2VRn9TTNNYic1PS8JsaNrwKo_iZ0c?usp=sharing)

## Анализ FastQC
подробнее можно посмтреть отчеты в репозитории
### ENCFF436WIU
![image](https://github.com/user-attachments/assets/fcbe3146-16c0-48ed-9096-ff844fff3133)


Подрезание не требуется

### ENCFF005JXT
![image](https://github.com/user-attachments/assets/e32c731e-4a04-4911-a71f-60a1af8ef77c)

Подрезание не требуется

### ENCFF615LEB
![image](https://github.com/user-attachments/assets/fa27e8de-fdeb-4f29-94c6-bcbfa9c91c9d)

Все также, подрезание не требуется
## Выравнивание на 7-ую хромосому: статистика

ChIP-seq	| Total number of reads |	Unique reads number |	Common reads number |	No Alignment
:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:|:-------------------------:
ENCFF436WIU	| 52770594 |	3826656 (7.25%)	 | 4727985 (8.96%) |	44215953 (83.79%)
ENCFF005JXT	| 41844503 |	3106338 (7.42%) |	4398565 (10.51%) |	34339600 (82.06%)
ENCFF615LEB	| 25897503 |	1987424 (7.67%) |	2773801 (10.71%) |	21136278 (81.62%)

Выравнили на одну хромосому, пересечений по больше части нет что ожидаемо. 

## Диаграммы Венна
X > Y             |  Y > X
:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/fc71fa30-08d6-4a88-9f4d-4d11bf4fdb92) | ![image](https://github.com/user-attachments/assets/f00ca87f-53ba-46a6-b043-8ce728aad003)
![image](https://github.com/user-attachments/assets/6a62a62b-060e-460f-b848-5185d6f5558d) | ![image](https://github.com/user-attachments/assets/fd79b405-1237-4d72-b443-71acb76f623c)

Алгоритм, на основе которого построены диаграммы, работает так, что пики первого чтения ищутся во втором. Если пики первого чтения меньше, алгоритм фиксирует совпадения при сравнении первого со вторым, но не наоборот (большие пики содержат маленькие, но не наоборот). Это приводит к различиям в цифрах и графиках. 

Также видно, что плотность пересечений меньше, если первыми берутся наши пики, а не экспериментальные. Это указывает на то, что часть наших пиков меньше экспериментальных. Количество пересечений остается ожидаемо небольшим, так как анализ проводился только на одной хромосоме.

## Бонусная часть:
### BAM полученный из ENCFF436WIU

Типичное             |  Эксперементальное
:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/dcdcc540-e591-49cf-859f-5c522c2772cf) | ![image](https://github.com/user-attachments/assets/41ba2b3a-4778-4d50-9fc7-1edaa1e14cbf)


### BAM полученный из ENCFF005JXT

Типичное             |  Эксперементальное
:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/dcdcc540-e591-49cf-859f-5c522c2772cf) | ![image](https://github.com/user-attachments/assets/3f6fa80a-7365-4120-8de0-37aba7812dde)


Выводы: Полученный график плохо кореллирует со статьей. возможной причиной может быть неправильная подготовка бам-> бигвиг  файлов в связи с чем получаем нетипичную картиинку с падением на TSS и TES
