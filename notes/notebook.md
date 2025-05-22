# Lesson 1 `What are images?`
1) Images are `numpy` arrays

    *`numpy` - Популярная библиотека для мат операций в Python

    An image shape is given by its:
    `height`, `width` and `number of channels`

    `image = cv2.imread('someimage.png')` - для чтения png изображения
    `.shape` - показывает shape изображения

    Предположим после `print(image.shape)` мы получили
    (720,1280,3) - Высота 720 пикселей, 1280 ширина и 3 канала т.е RGB

2) Image composition

    Images are made of `pixels`
    
    `1 pixel` - `1 byte`
    *pixels is where the info of pic will be stored*

    in most cases pixel value range from *0* to *255*
    in binary images pixel value is in [0,1]
    in 16 bits images pixel value range from *0* to *65535*