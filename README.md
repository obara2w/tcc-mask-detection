# Visão Computacional para detecção do uso de máscara de proteção facial

Este Repositório contem os scripts e conjunto de dados para o treinamento do modelo de detecção do uso de máscas de proteção facial usados no trabalho de conclusão de curso para obtenção do título de especialista em Data Science e Analytics do MBA USP ESALQ.

* Aluno: Wagner Takeshi Obara
* Orientador: Francisco Lledo dos Santos 

**Índice**

- [Visão Computacional para detecção do uso de máscara de proteção facial](#vis-o-computacional-para-detec--o-do-uso-de-m-scara-de-prote--o-facial)
  * [Conjunto de dados](#conjunto-de-dados)
  * [Script de treinamento](#script-de-treinamento)
  * [Executar o modelo utilizando uma Webcam](#executar-o-modelo-utilizando-uma-webcam)

## Conjunto de dados

O Conjunto de dados está disponível no diretório `dataset` deste repositório e está disponível em dois formatos, [PASCAL VOC](dataset/Face-Mask-Detection.v2i.voc.zip) e [YOLO v5 PyTorch](dataset/Face-Mask-Detection-2.yolo5.zip)

## Script de treinamento

Foi criado o Notebook [Mask-Train-YOLOv5.ipynb](Mask-Train-YOLOv5.ipynb) com os passos para treinar o modelo e para melhor desempenho é recomendado o uso de recursos de GPU, como o [Google Colab](https://colab.research.google.com/).

O mesmo notebook pode ser acessado com o Google Colab por [aqui](https://colab.research.google.com/drive/1PjF2eslicdO3Kyod7wkwojUwB2At6Bsy?usp=sharing).

Os resultados do treinamento podem ser encontrados no diretório [yolov5s_results](yolov5/runs/train/yolov5s_results) e os pesos obtidos no treinamento no diretório [weights](yolov5/runs/train/yolov5s_results/weights).

## Executar o modelo utilizando uma Webcam

Execute o comando abaixo para utilizar o modelo atraves de uma webcam fazer inferências em tempo real:

```bash
python yolov5/detect.py --weights yolov5/runs/train/yolov5s_results/weights/best.pt --conf 0.4 --source 0
```
