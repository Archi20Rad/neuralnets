# Нейронные сети
Практика для курса по нейронным сетям.   
Адрес почты для вопросов по курсу `ailabintsev@fa.ru`  
Слайды к лекциям можно найти [здесь](https://drive.google.com/drive/folders/114QaNFTlvY3oXLmzqiGzE48MfpozMTCh?usp=drive_link).  
Рекомендованый учебник по [гиту](https://git-scm.com/book/ru/v2).  
Нерекомендованный учебник по [гиту](https://dangitgit.com/ru).  
Учебник по машинному обучению от [ШАД](https://academy.yandex.ru/handbook/ml) раздел 5 и далее.  
Ссылка на результаты [промежуточной аттестации](grads/scores1-4.csv), все остальные файлы остались на своих местах.  
Вопросы к экзамену: [теория](doc/theory.md),  [практика](doc/practice.md).  

## Начало работы
В первую очередь необходимо завести на github собственный аккаунт и сделать себе форк репозитория.  
Ссылку на свой репозиторий присылайте мне на почту, чтобы я мог оценить Вашу работу.  
Затем клонируйте **свой** репозиторий на локальную машину.  

```shell
git clone https://github.com/yourname/neuralnets.git
cd neuralnets
```

Далее нужно настроить виртуальное окружение, если Ваша IDE не сделает это автоматически.   

Ubuntu, Mac:
```shell
python -m venv venv
source venv/bin/activate
```

Windows:
```commandline
python -m venv venv
venv/Scripts/activate.bat
```

Установка зависимостей:
```shell
pip install -r requirements.txt
```

Решение задач заключается в реализации функций в файлах `seminar*.py`  
В файлах `test*.py` находятся тесты, редактировать эти файлы НЕЛЬЗЯ. 

За каждый пройденный TestCase начисляется один балл. 
На каждую задачу приходится несколько тестов. 
Количество тестов больше, чем количество задач, поэтому будьте внимательны. 
Правильность решения проверяется тестированием unittest

```shell
python -m unittest discover -v -s src
```

Срок сдачи каждого задания - до начала следующего занятия.
На каждом следующем занятии будем разбирать решение предыдущего. 
Для каждого файла `seminar*.py` срок выполнения определяется по Вашему последнему коммиту в этот файл. 
Если Вы модифицируете файл после разбора решения на следующем занятии, количество баллов делится на 2. 

<details>
  <summary><h2>Прочие материалы</h2></summary>
  <ul>
    <li>
      <b>
        <p>Статья на Хабре <a href='https://habr.com/ru/articles/458170/'>погружение в свёрточные нейронные сети.</a></p>
      </b>
    </li>
    <li>
      <b>
        <p><a href='https://www.youtube.com/playlist?list=PLfdVzZl6HHg9y9l6U5xUjqKS13rWoQPF4'>Плейлист</a> с разбором разных тем</p>
      </b>
    </li>
  </ul>
</details>

## План практических занятий

1. Настройка рабочего окружения, разминка с numpy
2. Обучение Softmax классификатора
3. Многослойный персептрон
4. Продвинутые техники обучения нейросетей
5. Сверточные сети
6. Машинное зрение
7. Рекуррентные сети
8. Обработка текстов NLP

### Семинар 3. 
Для тех, у кого загрузка данных Cifar10 падает с ошибкой сертификата SSL:  
1. Скачать архив вручную [toronto](https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz) или [y-cloud](https://storage.yandexcloud.net/fa-bucket/cifar-10-python.tar.gz)  
2. Положить в папку `data` в корне проекта.
3. Указать аргумент в методе `test_utils.get_preprocessed_data(local_data=True)`

Для получения 5 баллов нужно реализовать обучение сети в файле `seminar3.py` и формирование отчета в папке  `output/seminar3`. 
За основу можно взять код из второго семинара. 
Это задание не оценивается скриптом, только вручную, поэтому оценки будут доведены позже.  

### Семинар 4. 
Как и в 3 семинаре, для получения 5 баллов нужно реализовать обучение сети в файле `seminar4.py` и формирование отчета в папке  `output/seminar4`. 
Это задание не оценивается скриптом, только вручную, поэтому оценки будут доведены позже.  

### Семинар 6. 
Необходимо обучить модель **бинарной** классификации на датасете Cats and Dogs. 
Точность модели должна быть выше 0.8 на закрытой тестовой выборке.
Размер модели не должен превышать 50 МБ. 
Если Вы загрузите модель большего размера или меньшей точностью, то будет начислено 3 балла.   
.env файл находится в папке гугл диска вместе с лекциями. 

### Семинар 7. 
Обучение модели бинарной классификации текстов SMS. 
По структуре этот семинар очень похож на шестой. 
Так же нужно загрузить данные, обучить модель с разными гиперпараметрами, валидировать на `spam_test.csv` и загрузить в хранилище S3. 
Accuracy, precision на тестовой выборке должны быть выше 0.95, recall > 0.9. 
Токенайзер на тесте должен быть обучен на обучающей выборке, иначе метрики сильно пострадают. 
Можете реализовать сериализацию и десериализацию токенайзера [Source](https://www.tensorflow.org/api_docs/python/tf/keras/preprocessing/text/Tokenizer#to_json). 
Для моделей с метриками ниже 0.95 оценка будет 3 балла, выше - 5 баллов.  

### Семинар 8. 
Зарегистрируйтесь на huggingface, логин используйте тот же что и на github. 
Добавьтесь в организацию Financial University DABD. 
Создайте токен с правом на запись, дообучите GPT-2 и опубликуйте модель! 



