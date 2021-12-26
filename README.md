## SpatialAwareStylisation

В данном ноутбуке реализована модификация [классической](https://github.com/leongatys/PytorchNeuralStyleTransfer)
модели переноса стиля, реализованной Леоном Гатисом. Суть модификации - перенос стиля по частям.

Принцип работы модификации:

- Style Image разбивается на гиперпиксели с помощью SLIC или Felzenwalb
- Content Image сегментируется с помощью сегментационной НС (был выбран Resnet)
- Для каждого сегмента Content выстраивается приоритет суперпикселей Style
- Каждый сегмент поочередно "присваивает" себе доли Style, ещё не принадлежащие другим

Примеры работы алгоритма.

![alt text](https://github.com/IlidanNaga/SpatialAwareStylisation/blob/master/Results/sample1.png?raw=true)

![alt text](https://github.com/IlidanNaga/SpatialAwareStylisation/blob/master/Results/sample2.png?raw=true)

Так же реализована возможность частично "сглаживать" произведенные изменения. Это достигается тем, что заранее заданный
перцентиль наиболее "близких" частей Style присваивается всем долям Content

![alt text](https://github.com/IlidanNaga/SpatialAwareStylisation/blob/master/Results/averaging.png?raw=true)
