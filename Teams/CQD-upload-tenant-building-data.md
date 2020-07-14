---
title: Отправка клиента и создание данных на панели мониторинга качества вызова (CQD)
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: Сведения о том, как передавать сведения о клиентах и зданиях на панели мониторинга качества вызовов (CQD).
ms.openlocfilehash: d8a27ab45a01d1b0eccc28716bee9fa838fb8de5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086087"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a>Отправка клиента и создание данных на панели мониторинга качества вызова (CQD)


Чтобы получить максимальную выпускную панель мониторинга качества звонков (CQD), мы рекомендуем вам отправить свой клиент и собрать данные. Существует два типа файлов данных клиента: [Сборка](#upload-building-data-file) и [Конечная точка](#endpoint-data-file).

Вы можете загрузить образец шаблона данных клиента [здесь](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true). Чтобы получить справку по созданию сопоставления, прочитайте раздел [Создание схемы здания для CQD](CQD-building-mapping.md).

На панели мониторинга сводные отчеты CQD выберите **отправить данные клиента** из меню CQD **Параметры** (значок шестеренки в верхней части CQD). Отсюда администраторы могут отправлять сведения о сборке и конечную точку своей организации, например сопоставлять IP-адреса и географические данные, отображая каждую точку доступа к беспроводной сети и ее MAC-адрес и т. д.

1. Откройте CQD (в центре администрирования Teams или at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ), а затем щелкните значок шестеренки в правом верхнем углу, а затем выберите **отправить данные о клиенте** на странице **Сводные отчеты** .

   ![Снимок экрана: диалоговое окно, которое появляется при загрузке данных](media/qerguide-image-tenantdataupload.png)
    
2. Кроме того, если вы впервые посещаете CQD, вам будет предложено отправить данные о сборке. Чтобы быстро перейти на страницу **отправки данных клиента** , можно нажать кнопку **Отправить** .

   ![Снимок экрана: объявление о том, что пользователь отправляет данные о сборке](media/qerguide-image-buildingdatauploadbanner.png)

3. На странице **Отправка данных клиента** нажмите кнопку **Обзор** , чтобы выбрать файл данных.

4. После выбора файла данных укажите **дату начала** и, при необходимости, укажите дату окончания.

5. После выбора **даты начала**нажмите кнопку **Отправить** , чтобы отправить файл в CQD. <br><br>Перед передачей файла он проверяется. Если проверка завершится сбоем, отобразится сообщение об ошибке с запросом на исправление файла. На приведенном ниже рисунке показана ошибка, возникающая при неправильном числе столбцов в файле данных.

   ![Пример диалогового окна, в котором отображается ошибка при отправке данных при сборке](media/qerguide-image-buildingdatauploaderror.png)
 
6. Если во время проверки появления ошибок не возникло, Отправка файла будет выполнена успешно. Затем вы можете просмотреть загруженный файл данных в таблице **Мои отправленные** данные, в которой показан полный список всех загруженных файлов для текущего клиента в нижней части страницы.

> [!NOTE]
> Для завершения обработки файла здания может потребоваться до четырех часов. <br><br> Если вы уже загрузили файл здания и вам нужно добавить подсети, которые могут быть пропущены или исключены, измените исходный файл, добавив в него новую подсеть, удалите текущий файл и повторно добавьте новый измененный файл. В CQD может быть только один активный файл данных здания. 


## <a name="upload-building-data-file"></a>Отправка файла данных здания

Первый тип файла данных клиента в CQD — это файл данных **здания** . Столбец Subnet является производным, разворачивая столбец Network + NetworkRange, а затем присоединяется к столбцу подсети в первой подсети или столбце второй подсети, чтобы отобразить сведения о здании, городе, стране или регионе. Формат загружаемого файла данных должен соответствовать следующим критериям для прохождения проверки перед отправкой:
  
- Файл должен иметь формат TSV (столбцы разделяются ТАБУЛЯЦИей) или CSV-файл (столбцы разделяются запятыми).
- Файл данных не содержит строку заголовка таблицы. Предполагается, что первая строка файла данных является реальными данными, а не метками заголовков, например "сеть".
- Типы данных в файле могут быть только строкой, целым числом или логическим значением. Для целочисленного типа данных значение должно быть числовым значением. Логические значения должны быть как 0, так и 1.
- Если столбец использует строковый тип данных, поле данных может быть пустым, но по-прежнему должно разделяться символом табуляции или запятыми. Пустое поле данных просто присваивает пустую строковое значение.
- Для каждой строки должно быть 14 столбцов, каждый столбец должен иметь соответствующий тип данных, а столбцы должны быть в том порядке, в котором они указаны в приведенной ниже таблице (запятыми или разделителями табуляции).

**Формат файла данных для создания**

| Имя столбца        | Тип данных | Пример                   | Рекомендации              |
|--------------------|-----------|---------------------------|-----------------------|
| NetworkIP          | String    | 192.168.1.0               | Обязательный              |
| NetworkName        | String    | США/Сиэтл/Сиэтл (SEA-1) | Обязательно<sup>1</sup>  |
| NetworkRange       | Число    | 26                        | Обязательный              |
| BuildingName       | String    | СИЭТЛ — МОРСКОЙ ВОЛНЫ (1 – 7)             | Обязательно<sup>1</sup>  |
| OwnershipType      | String    | Contoso                   | Необязательно               |
| BuildingType       | String    | Прекращение ИТ            | Необязательно               |
| BuildingOfficeType | String    | Техника               | Необязательно               |
| City               | String    | Сиэтл                   | Рекомендуется           |
| ZipCode            | String    | 98001                     | Рекомендуется           |
| Страну            | String    | Американские                        | Рекомендуется           |
| State              | String    | Красноярский край                        | Рекомендуется           |
| Region             | String    | MSUS                      | Рекомендуется           |
| InsideCorp<sup>2</sup>         | Bool      | 1             | Обязательный              |
| ExpressRoute<sup>3</sup>       | Bool      | до             | Обязательный              |
| VPN;                | Bool      | до                         | Необязательно               |

<sup>1</sup> Шаблоны, не требующиеся для CQD, настроены для отображения здания и сетевого имени.

<sup>2</sup> Этот параметр можно использовать, чтобы показать, входит ли подсеть в корпоративную сеть. Вы можете настроить использование для других целей.

<sup>3</sup> Этот параметр можно использовать, чтобы показать, использует ли сеть Azure ExpressRoute. Вы можете настроить использование для других целей.  

**Образец строки:**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> Диапазон сети может использоваться для представления supernet (сочетание нескольких подсетей с одним префиксом маршрутизации). Для всех новых выгрузок построения будут проверяться все перекрывающиеся диапазоны. Если вы ранее загрузили файл здания, вы должны скачать текущий файл и повторно загрузить его, чтобы определить перекрытие и устранить проблему перед повторной отправкой. Перекрытие в ранее загруженных файлах может привести к неправильному сопоставлению подсетей для зданий в отчетах. Некоторые реализации виртуальных частных сетей не сообщат сведения о подсети. При добавлении подсети VPN в файл построения вместо одной записи для подсети рекомендуется добавлять отдельные записи для каждого адреса в подсети VPN в виде отдельной сети 32-бит. Каждая строка может иметь одинаковые стандартные метаданные. Например, вместо одной строки для 172.16.18.0/24 необходимо иметь 256 строк с одной строкой для каждого адреса между 172.16.18.0/32 и 172.16.18.255/32 включительно.
>
> VPN-столбец является необязательным и по умолчанию будет равен 0. Если для столбца VPN задано значение 1, подсеть, представленная этой строкой, будет полностью развернута для соответствия всем IP-адресам в подсети.  Используй это экономно и только для подсетей VPN, так как полное расширение этих подсетей может отрицательно повлиять на время запроса запросов, связанных с созданием данных.


### <a name="supernetting"></a>Компенсация

Вы можете использовать в качестве подсети подсеть, которая обычно называется междоменной маршрутизацией (CIDR) вместо определения каждой из них. *Supernet* — это сочетание нескольких подсетей, использующих один префикс маршрутизации. Вместо добавления записи для каждой подсети вы можете использовать этот адрес. Поддерживая подсетей, но мы не рекомендуем использовать ее.

Например, маркетинг здания компании Contoso состоит из подсетей, указанных ниже.

-   10.1.0.0/24 — Первый этаж
-   10.1.1.0/24 — второй этаж
-   10.1.2.0/24 — третье основание
-   10.1.3.0/24 — четвертый этаж

Вместо того чтобы добавлять записи для каждой подсети, вы можете использовать ее в качестве адреса в этом примере: 10.1.0.0/22.

-   Network = 10.1.0.0
-   Диапазон сети = 22

Ниже приведены некоторые рекомендации, которые необходимо выполнить перед реализацией бесвзаимных сетей.

-   Подсеть может использоваться только в сопоставлении подсети с 8-битным и 28-битным масками.

-   Для подсети требуется меньше времени, но за счет снижения богатости ваших данных. Допустим, у вас возникла проблема, связанная с качеством, в которой используется подсеть 10.1.2.0. Если вы реализовали подсеть, вы не знаете, где находится сборка подсети или какой тип сети (например, лаборатория). Если вы определили все подсети для создания и отправки сведений о расположении этажей, вы сможете увидеть это отличие.

-   Важно удостовериться в том, что адрес является правильным и не может перехватывать ненужные подсети.

-   Найти 192.168.0.0 в данных очень часто. Для многих организаций это указывает на то, что пользователь находится дома. Для других пользователей это схема IP-адреса для сопутствующего офиса. Если в вашей организации есть офисы, использующие такую конфигурацию, не включайте их в файл здания, так как вы не сможете отличать домашние и внутренние сети с помощью [обычных подсетей](quality-of-experience-review-guide.md#common-subnets). 

> [!IMPORTANT]
> Диапазон сети можно использовать для представления supernet. Все новые загружаемые файлы данных будут проверяться на наличие перекрывающихся диапазонов. Если вы ранее загрузили стандартный файл, вы должны скачать текущий файл и отправить его повторно, чтобы определить перекрытие и устранить проблему. Перекрытие в ранее загруженных файлах может привести к неправильному сопоставлению подсетей для зданий в отчетах.

### <a name="vpn"></a>VPN;

Данные качества взаимодействия (QoE), которые клиенты отправляют в Microsoft 365 или Office 365, в которой источник данных CQD, включают флаг VPN. CQD увидят это в качестве первого VPN-и второго VPN-измерения. Тем не менее, этот флаг полагается на то, что в Windows для поставщика услуг VPN указана служба адаптера удаленного доступа. Не все поставщики услуг VPN правильно регистрируют адаптеры удаленного доступа. Из-за этого вы, возможно, не сможете использовать встроенные фильтры запросов VPN. Существует два подхода к размещению подсетей VPN в файле сведений о сборке.

- Укажите **Сетевое имя** , введя в это поле значение "VPN" для подсетей VPN.

  ![Снимок экрана: отчет QCD с VPN-подключением с использованием сетевого имени](media/qerguide-image-vpnnetworkname.png)

- Определите **имя здания** , введя в это поле значение "VPN" для подсетей VPN.

  ![Снимок экрана отчета QCD с именем для создания VPN](media/qerguide-image-vpnbuildingname.png)

> [!IMPORTANT]
> Некоторые реализации VPN не сообщают информацию о подсети. Если это произошло в ваших отчетах, мы рекомендуем вам при добавлении подсети VPN в файл здания вместо одной записи для подсети, добавьте отдельные записи для каждого адреса в подсети VPN в отдельной сети 32-bit. Каждая строка может иметь одинаковые стандартные метаданные. Например, вместо одной строки для 172.16.18.0/24 имеется 253 строк с одной строкой для каждого адреса из 172.16.18.1/32 в 172.16.18.254/32 включительно.


> [!NOTE]
> VPN-подключениям известно, что сетевое подключение может быть недоступно, если подключение к Интернету является беспроводным. При просмотре качества по сравнению с VPN-подключением вы не можете предположить, что тип соединения определен точно.


## <a name="endpoint-data-file"></a>Файл данных конечной точки

Другой тип файла данных клиента CQD — файл данных **конечной точки** . Значения столбцов используются в первом имени конечной точки клиента записи вызова или в столбце имени конечной точки клиента для отображения сведений о создании конечной точки, модели или типе. Формат загружаемого файла данных должен соответствовать следующим критериям для прохождения проверки перед отправкой:

- Файл должен иметь формат TSV (столбцы разделяются ТАБУЛЯЦИей) или CSV-файл (столбцы разделяются запятыми).
- Содержимое файла данных не содержит заголовков таблиц. Предполагается, что первая строка файла данных является реальными данными, а не меткой заголовка, например "EndpointName".
- Для всех шести столбцов используется только тип данных String. Максимально допустимая длина составляет 64 символов.
- Поле данных может быть пустым, но по-прежнему должно разделяться символом табуляции или запятыми. Пустое поле данных просто присваивает пустую строковое значение.
- EndpointName должны быть уникальными, в противном случае отправка завершается сбоем. Если в одной строке или двух строках используется один и тот же элемент EndpointName, конфликт может привести к неправильному присоединению.
- EndpointLabel1, EndpointLabel2 и EndpointLabel3 являются настраиваемыми наклейками. Они могут быть пустыми строками или значениями, например "ИТ-отдел обозначены в 2018 ноутбука" или "актива 5678".
- Для каждой строки должно быть шесть столбцов, а столбцы должны находиться в указанном ниже порядке.

  **Порядок полей:**

EndpointName, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2, EndpointLabel3

  **Образец строки:**

`1409W3534, Fabrikam Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018,`  



## <a name="update-a-building-file"></a>Обновление файла здания

При сборе сведений о сборке и подсети администраторы часто загружают файл здания в несколько итераций с течением времени, добавляя новые подсети и сведения о собрании, так как они станут доступны. В этом случае вам потребуется заново загрузить файл здания. Этот процесс похож на начальную отправку, описанную в предыдущем разделе, с некоторыми исключениями, как указано в следующем разделе.

> [!Important]
> В каждый момент времени активным может быть только один файл здания. Несколько файлов здания не являются совокупными.

## <a name="add-net-new-subnets"></a>Добавление новых подсетей в сети

Иногда вам потребуется добавить новые подсети в CQD, которые не были первоначально включены в топологию сети. Чтобы добавить новую подсеть, выполните указанные ниже действия на странице **отправки данных клиента** в CQD:

2.  Скачайте исходный файл, если у вас еще нет актуальной копии.
1.  Удаление текущего файла в CQD.
1.  Измените первоначальный файл здания и укажите дату окончания, которая приходится на один день до того, как были получены новые подсети.
1.  Добавляйте новые подсети к исходному стандартному файлу.
1.  Загрузите обновленный стандартный файл и установите дату начала в течение одного дня после завершения предыдущего здания.

## <a name="add-missing-subnets"></a>Добавление недостающих подсетей

После отправки сведений о сборках для управляемых сетей все управляемые сети должны иметь ассоциацию здания. Однако это не всегда так. как правило, пропущено несколько подсетей. Чтобы найти недостающие сети, ознакомьтесь со сведениями **об отсутствующей подсети** на странице **отчеты качества взаимодействия** в CQD. Это представляет все подсети с 10 или более, не определенными в файле данных здания, и помечены как внешние. Убедитесь в том, что в этом списке нет управляемых сетей. Если у вас нет подсетей, выполните описанные ниже действия, чтобы обновить исходный файл данных и заново добавить его в CQD.

1. Перейдите на страницу **отправки данных клиента** в CQD.
1. Скачайте исходный файл, если у вас еще нет актуальной копии.
1. Удаление текущего файла в CQD.
1. Добавляйте новые подсети в исходный файл.
1. Добавьте файл здания. Не забудьте установить дату начала по крайней мере на восемь месяцев, прежде чем CQD будет обрабатывать исторические данные.


> [!IMPORTANT]
> Вам потребуется добавить идентификатор клиента в фильтр запроса для **второго идентификатора клиента** в этот отчет, чтобы отфильтровать отчет, чтобы просмотреть только данные клиента своей организации. В противном случае в отчете будут показаны Федеративные подсети.

> [!NOTE] 
> Не забудьте настроить фильтр отчета "месячный год" на текущий месяц. Выберите **изменить**и настройте фильтр отчета " **месяц года** ", чтобы сохранить новый месяц по умолчанию.


## <a name="related-topics"></a>Связанные статьи

[Создание схемы здания для CQD](CQD-building-mapping.md)

[Улучшение и мониторинг качества связи для Teams](monitor-call-quality-qos.md)

[Что такое CQD?](CQD-what-is-call-quality-dashboard.md)

[Настройка панели мониторинга качества звонков (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Данные CQD и отчеты](CQD-data-and-reports.md)

[Использование CQD для управления качеством звонков и собраний](quality-of-experience-review-guide.md)

[Измерения и меры, доступные в CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Классификация потоков в CQD](stream-classification-in-call-quality-dashboard.md)

[Анализ данных CQD с помощью Power BI](CQD-Power-BI-query-templates.md)