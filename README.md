# Описание объектной модели больницы
*Больница* – вид медицинского учреждения, направленного на лечение больных и/или специализированную диагностику заболеваний.

Есть два варианта взаимодействия с приложением: как 
**пациент** [пациент](#Врач) и как **лечащий врач**.

При открытии приложения на экране пользователь может выбрать удобный ему язык интерфейса и ввести индивидуальный код. (Каждый лечащий врач имеет свой индивидуальный код,  пациент получает индивидуальный код при регистрации его в больнице.)

Рассмотрим возможные варианты взаимодействия с приложением.
#Врач
## Пользователь как лечащий врач 
Для начала использования пользователь вводит индивидуальный код. Автоматически из базы данных подгружается информация о пациентах данного пользователя. Пользователь переходит на главный экран.

**Главный экран** вмещает в себя таблицу с данными, загруженными из базы данных.

ФИО | Палата | Статус | Анализ | Диагноз
--- | ------ | ------ | ------ | -------


Для добавления/изменения пользователь нажимает на строку, содержащую информацию о пациенте , которую необходимо дополнить/изменить.

При нажатии на нужную строку пользователь переходит на новый экран. Экран содержит в себе 5 текстовых полей, которые соответствуют названиям колонок таблицы. Пользователь может устанавливать/изменять поля: Статус, Анализ, Диагноз.

При нажатии на поле **Статус**, появляется возможность заполнить поле текстом.

При нажатии на поле **Анализ**, появляется возможность вписать название анализа/процедуры и установить время сбора в формате *hh:mm*.

При нажатии на поле **Диагноз**, появляется возможность ввести название диагноза, предоставляется выбор отображать ли диагноз пациенту.

При переходе на любой экран, кроме главного, снизу расположены кнопки: Сохранить изменения, Перейти на главный экран.

Помимо прочего, лечащему врачу может прийти экстренное сообщение вызова от пациента на любой экран. Сообщение содержит в себе ФИО пациента, номер палаты и его статус.

## Пользователь как пациент

При правильном вводе индивидуального кода информация о пользователе считывается из базы данных больницы, а пользователь переходит на главный экран.

Главный экран вмещает в себя 1 текстовое поле «Дата поступления» и 5 иконок: *«Расписание», «Анализы/Процедуры», «О диагнозе», «Переводчик», «Экстренный вызов».*

Текстовое поле **«Дата поступления»** содержит в себе дату регистрации пациента в формате *d-m-Y*.

При нажатии на иконку **«Расписание»**, осуществляется переход на новый экран. На нем расписан распорядок дня больницы в формате *«Время» - «Событие»*. 

При нажатии на иконку **«Анализы/Процедуры»**, осуществляется переход на новый экран. На нем в виде таблицы описаны все процедуры и анализы, которые пациент должен сделать. В формате

Название | Время сбора | Рекомендации 
-------- | ----------- | ------------ 

Таблицу заполняет лечащий врач, при появлении нового анализа/процедуры приходит уведомление. Уведомление так же приходит за 10 минут до времени сбора. Если никаких анализов/процедур не было назначено, то таблица остаётся пустой.  
  

При нажатии на иконку **«О диагнозе»**, осуществляется переход на новый экран. Если лечащий врач установил диагноз, этот диагноз будет показан на экране у пользователя. По названию диагноза из базы данных будет загружена краткая информация о диагнозе и соответствующие рекомендации.

При нажатии на иконку **«Переводчик»**, осуществляется переход на новый экран. Открывается переводчик, пользователь может ввести текст на удобном ему языке и перевести его на русский.

На каждом экране, кроме главного располагается кнопка **«Главное меню»**, при нажатии на неё пользователь переходит на главный экран. Ещё на экране располагается кнопка **«SOS»**, при нажатии на нее, пользователь отправляет сигналы экстренного вызова лечащему врачу.
⠀
⠀
⠀
⠀
⠀
⠀


## User stories

-   Как **лечащий врач** я хочу иметь быстрый доступ к данным о  пациентах, чтобы координировать следующие этапы лечения.
    
-   Как **лечащий врач** я хочу простой, интуитивно-понятный интерфейс, чтобы экономить время.
    
-   Как **лечащий врач** я хочу изменять данные о пациенте, чтобы данные оставались актуальными.
    
-   Как **лечащий врач** я хочу получать информацию об экстренных вызовах от пациентов, чтобы быстро на них реагировать.
    
-   Как **пациент** я хочу простой, интуитивно-понятный интерфейс, чтобы экономить время.
    
-   Как **пациент** я хочу видеть расписание больницы, чтобы правильно управлять своим временем.
    
-   Как **пациент** я хочу получать напоминание об анализах/процедурах, чтобы не забывать их выполнять.
    
-   Как **пациент** я хочу видеть диагноз и информацию о нём, чтобы иметь представление о своем текущем состоянии.
    
-   Как **пациент** я хочу иметь возможность использовать переводчик, чтобы иметь возможность выразить мысль не обладая навыками нужного языка.
    
-   Как **пациент** я хочу иметь возможность быстро вызвать врача, чтобы оперативно получить помощь при резком ухудшении самочувствия.
