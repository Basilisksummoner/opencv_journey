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

# Lesson 2 `Input/Output`
    Начинаем с:
`import os`
`import cv2`

1) Read image
    *Предположим что image находится в той же директории что и проект*
    *в папке data*
    
    `define image path`
    `image_path = os.path.join('.','data','image.jpg')`
    т.е указываем в () директорию, папку и название файла
    
    *Теперь создаем переменную в которой будем считывать image*

    **cv2.imread(путь к image)** - Супер важная функция, основа основ
    
2) Saving image 

    `img = cv2.imread(image_path)` - Сохраняем набор пискелей в img

    *Как сохранять на комп отредаченое изображение*
    `cv2.imwrite(os.path.join('.','data','new_image.jpg'),img)`

    **cv2.imwrite(куда сохраняем, что сохраняем)**

3) Visualize image

    `cv2.imshow('frame', img)`
    `cv2.waitKey(0)` - Откроется окно с картинкой, будет стоять 0 мс

    **cv2.imshow('название окна', что показываем)**
    **cv2.waitKey(кол-во милисекунд)**