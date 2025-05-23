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

# Lesson 3 `Videos`
1) Read video
    *Для начала specify video path:*
    `video_path = os.path.join('.'.'data','video.mp4')`

    *Теперь сам reading*
    `video = cv2.VideoCapture(video_path)`

    **cv2.VideoCapture(путь к видосу)**

2) Visualize video
    *We have to create `variable` and set it to True
    `ret = True`

    `while ret:`
        `ret, frame = video.read()`
        `if ret:`
            `cv2.imshow('frame', frame)`
            `cv2.waitKey(40)`

    **название var где происходит чтение пикселей + .read**

    *ВАЖНО!!! Чтобы освободить память нужно прописать:*
        `video.release()`
        `cv2.destroyAllWindows()`

3) Explanation
    *p.s как это понял я*

    1) Для начала задаем путь к файлу (также как и в случае с images)
    2) Создаем переменную которая будет хранить набор пикселей,
    для этого используется:
        `перменная = cv2.VideoCapture(video_path)`
    3) Теперь о визуализации:

        *Видео это набор кадров (т.е frames)*
        *fps = frames per second (обычно 25)*

        Чтобы показать видос мы должны использовать цикл `while`
            а перед этим *желательно* создать точку входа т.е
            например перменная x
            `x = True`
            `while x`

        Теперь нужно:
            `x, frame = video.read()` 
            потому что функция `.read()` return два аргумента
        
        *Получается*
        `ret = True`
        `while ret:`
            `ret`,`frames` = `video.read()`

        Теперь пишем в цикле продолжение логики:
            `if ret:`
                `cv2.imshow('frame', frame)` - **второй аргумент всегда `frame`**
                `cv2.waitKey(40)`