# ExpressNet-Advanced-Facial-Emotion-Recognition
ExpressNet is an innovative facial emotion recognition platform developed using deep learning models and Python. The project aims to accurately identify and classify seven basic emotions - anger, disgust, fear, happiness, neutral, sadness, and surprise - from facial images.

  1 | {
  2 |   "nbformat": 4,
  3 |   "nbformat_minor": 0,
  4 |   "metadata": {
  5 |     "colab": {
  6 |       "name": "Copy of FER AB",
  7 |       "provenance": [],
  8 |       "collapsed_sections": []
  9 |     },
 10 |     "kernelspec": {
 11 |       "name": "python3",
 12 |       "display_name": "Python 3"
 13 |     },
 14 |     "accelerator": "TPU"
 15 |   },
 16 |   "cells": [
 17 |     {
 18 |       "cell_type": "code",
 19 |       "metadata": {
 20 |         "id": "YqMM73DWZ98U"
 21 |       },
 22 |       "source": [
 23 |         ""
 24 |       ],
 25 |       "execution_count": null,
 26 |       "outputs": []
 27 |     },
 28 |     {
 29 |       "cell_type": "code",
 30 |       "metadata": {
 31 |         "id": "Law8UGxTZ5OA",
 32 |         "colab": {
 33 |           "base_uri": "https://localhost:8080/"
 34 |         },
 35 |         "outputId": "c3852593-9f4d-4692-a3bd-926d6560de7c"
 36 |       },
 37 |       "source": [
 38 |         "from zipfile import ZipFile\n",
 39 |         "file_name = \"CK+48.zip\"\n",
 40 |         "\n",
 41 |         "with ZipFile(file_name,'r') as zip:\n",
 42 |         "  zip.extractall()\n",
 43 |         "  print('done')\n"
 44 |       ],
 45 |       "execution_count": 2,
 46 |       "outputs": [
 47 |         {
 48 |           "output_type": "stream",
 49 |           "text": [
 50 |             "done\n"
 51 |           ],
 52 |           "name": "stdout"
 53 |         }
 54 |       ]
 55 |     },
 56 |     {
 57 |       "cell_type": "code",
 58 |       "metadata": {
 59 |         "id": "Uzp5TDJWO2Qh"
 60 |       },
 61 |       "source": [
 62 |         "from __future__ import print_function\n",
 63 |         "import keras\n",
 64 |         "from keras.preprocessing.image import ImageDataGenerator\n",
 65 |         "from keras.models import Sequential\n",
 66 |         "from keras.layers import Dense, Dropout, Activation, Flatten, BatchNormalization\n",
 67 |         "from keras.layers import Conv2D, MaxPooling2D\n",
 68 |         "from keras.preprocessing.image import ImageDataGenerator\n",
 69 |         "import os\n",
 70 |         "\n"
 71 |       ],
 72 |       "execution_count": 3,
 73 |       "outputs": []
 74 |     },
 75 |     {
 76 |       "cell_type": "code",
 77 |       "metadata": {
 78 |         "colab": {
 79 |           "base_uri": "https://localhost:8080/",
 80 |           "height": 284
 81 |         },
 82 |         "id": "x2Nu09LDoQEN",
 83 |         "outputId": "f7680a5a-0b5a-4f5d-b363-6a06fceb255c"
 84 |       },
 85 |       "source": [
 86 |         "import cv2\n",
 87 |         "import matplotlib.pyplot as plt\n",
 88 |         "import sklearn\n",
 89 |         "img1 = cv2.imread('/content/CK+48/validation/angry/S133_003_00000045.png')\n",
 90 |         "\n",
 91 |         "plt.imshow(img1)\n"
 92 |       ],
 93 |       "execution_count": 10,
 94 |       "outputs": [
 95 |         {
 96 |           "output_type": "execute_result",
 97 |           "data": {
 98 |             "text/plain": [
 99 |               "<matplotlib.image.AxesImage at 0x7f83d9e82f90>"
100 |             ]
101 |           },
102 |           "metadata": {
103 |             "tags": []
104 |           },
105 |           "execution_count": 10
106 |         },
107 |         {
108 |           "output_type": "display_data",
109 |           "data": {
110 |             "image/png": 
