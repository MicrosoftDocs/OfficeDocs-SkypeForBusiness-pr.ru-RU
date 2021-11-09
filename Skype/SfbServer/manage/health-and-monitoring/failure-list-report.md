---
title: Отчет о списке отказов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: Сводка. Сведения о отчете о списке отказов в Skype для бизнеса Server.
ms.openlocfilehash: 37442d95c3a79bffbd79ebd74a793f5d3e1f3fb4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858296"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>Отчет о списке отказов в Skype для бизнеса Server 
 
**Сводка:** Узнайте о отчете о списке отказов в Skype для бизнеса Server.
  
Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.
  
## <a name="accessing-the-failure-list-report"></a>Доступ к отчету Failure List (Список ошибок)

Отчет о списке отказов можно получить, нажав любой из следующих метрик в отчете о рассылке отказов в [Skype для бизнеса Server:](failure-distribution-report.md)
  
- Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))
    
- Top modalities (sessions) (Основные условия (сеансы))
    
- Top pools (sessions) (Основные пулы (сеансы))
    
- Top sources (sessions) (Основные источники (сеансы))
    
- Top components (sessions) (Основные компоненты (сеансы))
    
- Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))
    
- Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))
    
- Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))
    
В отчете о списке отказов вы можете получить доступ к отчету о подробностях одноранговых сеансов в Skype для бизнеса Server, [щелкнув](peer-to-peer-session-detail-report.md) метрику детализации сеанса для одноранговой сессии. Чтобы открыть отчет Conference Detail (Сведения о конференции), щелкните показатель Conference (Конференция) для конференции.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Рекомендации по использованию отчета Failure List (Список ошибок)

Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:
  
Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).
  
Важно отметить, что отчет Failure List (Список ошибок) не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками. (К примеру, отчет Failure List (Список ошибок) не предоставляет функции фильтрации данных.) Однако если вы экспортируете данные и затем преобразуете их в файл данных с разделителями-запятыми, то для ответа на вышеуказанные вопросы можно использовать Windows PowerShell. Предположим, что вы сохранили данные в CSV-файле C:\Data\Failure_List.csv. Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды: 
  
```PowerShell
$failures = Import-Csv -Path " C:\Data\Failure_List.csv"
$failure |Sort-Object "From user" | Select-Object "From user" -Unique
```

Эти команды возвращают сведения, схожие со следующими:
  
<pre>
    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com
</pre>

Следующие команды возвращают общее число сеансов каждого пользователя, завершившихся с ошибкой:
  
```PowerShell
$failures = Import-Csv -Path "C:\Data\Failure_List.csv"
$failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending
```

Эти команды возвращают сведения, схожие со следующими:
  
<pre>
Count    Name
 -----    ----
    20    Pilar.Ackerman@litwareinc.com
    20    David.Ahs@litwareinc.com
    16    Gilead.Amosnino@litwareinc.com
    16    Ken.Myero@litwareinc.com
    14    Henrik.Jensen@litwareinc.com
</pre>

## <a name="filters"></a>Фильтры

Нет. В отчете Failure List (Список ошибок) нельзя использовать фильтр.
  
## <a name="metrics"></a>Метрики

В следующей таблице приведены сведения, содержащиеся в отчете Failure List (Список ошибок) для каждого звонка, завершившегося с ошибкой.
  
**Показатели отчета Failure List (Список ошибок)**

|**Название**|**Возможность сортировки по этому показателю**|**Описание**|
|:-----|:-----|:-----|
|**Reported time** (Время создания отчета) <br/> |Нет  <br/> |Дата и время создания отчета.  <br/> |
|**Запрос** <br/> |Нет  <br/> |Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.  <br/> |
|**Response code** (Код ответа) <br/> |Нет  <br/> |Код ответа SIP, отправленный при сбое конференции.  <br/> |
|**Diagnostic ID** (ИД диагностики) <br/> |Нет  <br/> |Уникальный идентификатор (в виде заголовка ms-diagnostics), добавленный к сообщению SIP, который предоставляет полезные сведения для устранения ошибок.  <br/> |
|**Join cost time (ms)** (Время присоединения (мс)) <br/> |Нет  <br/> |Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.  <br/> |
|**From user** (От пользователя) <br/> |Нет  <br/> |SIP-адрес пользователя, инициировавшего звонок.  <br/> |
|**From user agent** (От агента пользователя) <br/> |Нет  <br/> |Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.  <br/> |
|**To user** (К пользователю) <br/> |Нет  <br/> |SIP-адрес пользователя, принявшего звонок.  <br/> |
   

