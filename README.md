# Описание объектной модели больницы
*Больница* – вид медицинского учреждения, направленного на лечение больных и/или специализированную диагностику заболеваний.

Есть два варианта взаимодействия с приложением: как [пациент](#пользователь-как-пациент) и как [лечащий врач](#пользователь-как-лечащий-врач).

При открытии приложения на экране пользователь может ввести индивидуальный код. (Каждый лечащий врач имеет свой индивидуальный код,  пациент получает индивидуальный код при регистрации его в больнице.)

Рассмотрим возможные варианты взаимодействия с приложением.

## Пользователь как лечащий врач:
Для начала использования пользователь вводит индивидуальный код. Автоматически подгружается информация о пациентах данного пользователя. Пользователь переходит на главный экран.

**Главный экран** вмещает в себя таблицу с данными, загруженными из базы данных.

ФИО | Палата | Статус | Анализ | Диагноз
--- | ------ | ------ | ------ | -------

Для добавления/изменения пользователь нажимает на строку, содержащую информацию о пациенте , которую необходимо дополнить/изменить.

Пользователь может устанавливать/изменять поля: Статус, Анализ, Диагноз.

При нажатии на поле **Статус**, появляется возможность заполнить поле текстом.

При нажатии на поле **Анализ**, появляется возможность вписать название анализа/процедуры и установить время сбора в формате *hh:mm*.

При нажатии на поле **Диагноз**, появляется возможность ввести название диагноза, предоставляется выбор отображать ли диагноз пациенту.

Внизу экрана расположена кнопка: Сохранить изменения.

Помимо прочего, лечащему врачу может прийти экстренное сообщение вызова от пациента на экран. Сообщение содержит в себе ФИО пациента, номер палаты и его статус.

## Пользователь как пациент:

При правильном вводе индивидуального кода информация о пользователе считывается, а пользователь переходит на главный экран.

**Главный экран** вмещает в себя 1 текстовое поле «Дата поступления» и 4 иконки: *«Расписание», «Анализы/Процедуры», «О диагнозе», «Экстренный вызов».*

Текстовое поле **«Дата поступления»** содержит в себе дату регистрации пациента в формате *d-m-Y*.

При нажатии на иконку **«Расписание»**, осуществляется переход на новый экран. На нем расписан распорядок дня больницы в формате *«Время» - «Место»,«Событие»*. 

При нажатии на иконку **«Анализы/Процедуры»**, осуществляется переход на новый экран. На нем описаны все процедуры и анализы, которые пациент должен сделать. Также указаны время анализов и кабинет. 

Эти данные заполняет лечащий врач. Если никаких анализов/процедур не было назначено, то экран остается пустым.

При нажатии на иконку **«О диагнозе»**, осуществляется переход на новый экран. Если лечащий врач установил диагноз, этот диагноз будет показан на экране у пользователя. По названию диагноза будет загружена краткая информация о диагнозе и соответствующие рекомендации.

На каждом экране, кроме главного располагается кнопка *«SOS»*, при нажатии на нее, пользователь отправляет сигналы экстренного вызова лечащему врачу.⠀

## Направления развития:
+ После входа пациент может выбрать английский язык интерфейса .
+ При появлении нового анализа/процедуры приходит уведомление. 
+ При нажатии на иконку «Переводчик», осуществляется переход на новый экран. Открывается переводчик, пользователь может ввести текст на удобном ему языке и перевести его на русский.

## User stories:

-   Как [лечащий врач](#пользователь-как-лечащий-врач) я хочу иметь быстрый доступ к данным о пациентах, чтобы координировать следующие этапы лечения.
    
-   Как [лечащий врач](#пользователь-как-лечащий-врач) я хочу простой, интуитивно-понятный интерфейс, чтобы экономить время.
    
-   Как [лечащий врач](#пользователь-как-лечащий-врач) я хочу изменять данные о пациенте, чтобы данные оставались актуальными.
    
-   Как [лечащий врач](#пользователь-как-лечащий-врач) я хочу получать информацию об экстренных вызовах от пациентов, чтобы быстро на них реагировать.
    
-   Как [пациент](#пользователь-как-пациент) я хочу простой, интуитивно-понятный интерфейс, чтобы экономить время.
    
-   Как [пациент](#пользователь-как-пациент) я хочу видеть расписание больницы, чтобы правильно управлять своим временем.
    
-   Как [пациент](#пользователь-как-пациент) я хочу видеть предстоящие анализы/процедуры, чтобы не забывать их выполнять.
    
-   Как [пациент](#пользователь-как-пациент) я хочу видеть диагноз и информацию о нём, чтобы иметь представление о своем текущем состоянии.
        
-   Как [пациент](#пользователь-как-пациент) я хочу иметь возможность быстро вызвать лечащего врача, чтобы оперативно получить помощь при резком ухудшении самочувствия.

## Entity relationship diagram:

![Entity relationship diagram](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/8c772e1166aca0e84816f16fa44625a63876143d/diagrams/ER.png)

## BPMN diagrams:

![BPMN diagram](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/f0eb9d1169026ff911b1a2f4c9fc179b2829e196/diagrams/bpmn_diagram.png)

## Use case diagrams:

![Use_case_pacient](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/c7b9dbce50e039839b9ac0f76f2ca7957a521e2d/diagrams/usecase_pacient.png)
![Use_case_doctor](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/c7b9dbce50e039839b9ac0f76f2ca7957a521e2d/diagrams/usecase_doctor.png)

## UML class diagrams:
- Базовая:



- После входа пациент может выбрать английский язык интерфейса:

![uml_class_exxt1](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/053fc5f0f524053ec8593154de33c1403e9f0dd6/diagrams/uml_class_exxt1.png)

- При появлении нового анализа/процедуры приходит уведомление:



- При нажатии на иконку «Переводчик», осуществляется переход на новый экран. Открывается переводчик, пользователь может ввести текст на удобном ему языке и перевести его на русский:




## State diagram:

Диаграмма состояний перехода между окнами.

![uml_state](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/f0f08bfd59e449d5408f795a640947d6578fad95/diagrams/uml_state.png)

## Макет интерфейса
![ui_1](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/5a82a801ce330493579b3be3bce7312c132cdd55/diagrams/ui_1.jpg)
![ui_2](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/5a82a801ce330493579b3be3bce7312c132cdd55/diagrams/ui_2.jpg)
![ui_3](https://github.com/fcumay/Hospital-app-model.-OnTime/blob/5a82a801ce330493579b3be3bce7312c132cdd55/diagrams/ui_3.jpg)


