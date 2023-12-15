# Resnet-V16
## Теоретическая база

Convolutional neural network (CNN) is a regularized type of feed-forward neural network that learns feature engineering by itself via filters (or kernel) optimization. Vanishing gradients and exploding gradients, seen during backpropagation in earlier neural networks, are prevented by using regularized weights over fewer connections.

A Residual Neural Network (a.k.a. Residual Network, ResNet) is a deep learning model in which the weight layers learn residual functions with reference to the layer inputs. A Residual Network is a network with skip connections that perform identity mappings, merged with the layer outputs by addition. It behaves like a Highway Network whose gates are opened through strongly positive bias weights. This enables deep learning models with tens or hundreds of layers to train easily and approach better accuracy when going deeper. The identity skip connections, often referred to as "residual connections", are also used in the 1997 LSTM networks, Transformer models (e.g., BERT, GPT models such as ChatGPT), the AlphaGo Zero system, the AlphaStar system, and the AlphaFold system.

Residual Networks were developed by Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun, which won the ImageNet 2015 competition.

## Описание разработанной системы

### Skip connection
![Skip connection](https://media.geeksforgeeks.org/wp-content/uploads/20200424011510/Residual-Block.PNG)
### Architecture
![Architecture](https://sun9-60.userapi.com/impg/c2jouT-6QqFheKeFJO9ikuhl66yDRaZgSSpWzA/hgsexk4KoOk.jpg?size=850x229&quality=96&sign=6fc3c3af80d5a2fd6ce34cffe4cc9c42&type=album)

### Adabound
AdaBound is a variant of the Adam stochastic optimizer which is designed to be more robust to extreme learning rates. Dynamic bounds are employed on learning rates, where the lower and upper bound are initialized as zero and infinity respectively, and they both smoothly converge to a constant final step size. AdaBound can be regarded as an adaptive method at the beginning of training, and thereafter it gradually and smoothly transforms to SGD (or with momentum) as the time step increases. 
![Adabound](https://sun9-2.userapi.com/impg/-WlZchD7hEjGdY12DZr6I24feFOvEMq6Kp2ScQ/GNdGPaR1X8A.jpg?size=912x326&quality=96&sign=66d2c28e17297af8cbc6f56df8cfff9e&type=album)

## Результаты работы и тестирования системы
### c Adabound
![loss](https://sun9-75.userapi.com/impf/uRFodPg6aC4jQofC3qcKH5k4MGIk2L97AXbshg/X3-qOqX4Hqs.jpg?size=547x413&quality=96&sign=594a4076018ef3672715e0ca9830ce25&type=album)
### с Adam
![loss](https://sun9-79.userapi.com/impf/Xo-rKFkToH3KS1nY03ePyBriSOAG7XC3Qck9Hg/zkW6-el8rO0.jpg?size=547x413&quality=96&sign=a4948b8bdc46fd62f67fe75ef369b1d2&type=album)
## Вывод по работе
В результате эксперимента с обучением ResNet v16 с использованием двух различных оптимизаторов, а именно Adam и Adabound, были получены следующие результаты.

Оптимизатор Adam продемонстрировал более успешные показатели в сравнении с Adabound. Обучение с использованием Adam достигло значительно более низкого значения функции потерь на тренировочном наборе данных (0.1277 по сравнению с 1.6878) и продемонстрировало более высокую точность на тестовом наборе данных (23.23% по сравнению с 15.18%).

Таким образом, можно сделать вывод, что Adam в данном случае эффективнее Adabound в обучении ResNet v16, обеспечивая более низкие значения потерь и более высокую точность на тестовом наборе данных.

## Источники
    https://www.geeksforgeeks.org/residual-networks-resnet-deep-learning/?ref=lbp
    https://en.wikipedia.org/wiki/Residual_neural_network
    https://paperswithcode.com/method/adabound
    https://pytorch.org/



