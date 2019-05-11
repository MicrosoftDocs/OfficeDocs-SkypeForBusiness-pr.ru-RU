---
title: FAILURE List Report в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
description: 'Сводка: Сведения об отчете списка сбоев в Скайп Business Server.'
ms.openlocfilehash: 67c02e9b0366bcf850139717eedf5c3946183988
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926601"
---
# <a name="failure-list-report-in-skype-for-business-server"></a>FAILURE List Report в Скайп для Business Server 
 
**Сводка:** Сведения об отчете списка сбоев в Скайп Business Server.
  
Отчет Failure List (Список ошибок) предоставляет сведения об участниках однорангового сеанса (конференции), завершившегося с ошибкой. Эти сведения содержат URI пользователя, у которого возникла ошибка, а также код ответа SIP и ИД диагностики, связанные с ошибкой.
  
## <a name="accessing-the-failure-list-report"></a>Доступ к отчету Failure List (Список ошибок)

Failure List Report открыть, щелкнув какую-либо из следующих показателей [Отчета о распределении сбоев в Скайп для Business Server](failure-distribution-report.md):
  
- Top diagnostic reasons (sessions) (Основные причины диагностики (сеансы))
    
- Top modalities (sessions) (Основные условия (сеансы))
    
- Top pools (sessions) (Основные пулы (сеансы))
    
- Top sources (sessions) (Основные источники (сеансы))
    
- Top components (sessions) (Основные компоненты (сеансы))
    
- Top from users (sessions) (Основные пользователи с ошибками исходящей связи (сеансы))
    
- Top to users (sessions) (Основные пользователи с ошибками входящей связи (сеансы))
    
- Top from user agents (sessions) (Основные агенты пользователей, используемые в сеансах, завершившихся с ошибками (сеансы))
    
Из Failure List Report, щелкнув метрику сведений о сеансе для сеанса peer-to-peer можно вызвать [Peer-to-Peer сеанса подробный отчет в Скайп для Business Server](peer-to-peer-session-detail-report.md) . Чтобы открыть отчет сведений о конференции, нажмите показатель «Конференция» для конференции.
  
## <a name="making-the-best-use-of-the-failure-list-report"></a>Рекомендации по использованию отчета Failure List (Список ошибок)

Чтобы просмотреть описание кода ответа или ИД диагностики, наведите указатель мыши на значение. Например, если вы наведете указатель мыши на Diagnostic ID (ИД диагностики) 7 025, то вы увидите следующую всплывающую подсказку:
  
Internal server error creating media for user (Внутренняя ошибка сервера при создании среды для пользователя).
  
Важно отметить, что отчет по списку ошибок не предоставляет прямой способ получения списка всех пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, или способ определения пользователей, которые наиболее часто участвовали в сеансах, закончившихся с ошибками. (Всего, Failure List Report равно нет возможности фильтрации). Тем не менее если экспортировать данные, а затем преобразовать его в файл с разделителями-запятыми, чтобы найти ответы на вопросы, например, можно использовать Windows PowerShell. Предположим, что вы сохранили данные в CSV-файле C:\Data\Failure_List.csv. Чтобы получить список пользователей, принимавших участие в хотя бы одном сеансе, закончившемся с ошибкой, используйте следующие команды: 
  
```
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
  
```
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
  
## <a name="metrics"></a>Показатели

В следующей таблице приведены сведения, содержащиеся в отчете Failure List (Список ошибок) для каждого звонка, завершившегося с ошибкой.
  
**Показатели отчета Failure List (Список ошибок)**

|**Имя**.|**Поддержка сортировки**|**Описание**|
|:-----|:-----|:-----|
|**Время создания отчета** <br/> |Нет  <br/> |Дата и время создания отчета.  <br/> |
|**Запрос** <br/> |Нет  <br/> |Тип запроса SIP, завершившегося с ошибкой. Например, INVITE или BYE.  <br/> |
|**Код ответа** <br/> |Нет  <br/> |Код ответа SIP, отправленный при сбое конференции.  <br/> |
|**ИД диагностики** <br/> |Нет  <br/> |Прикрепленный к SIP-сообщению уникальный идентификатор (в форме заголовка ms-diagnostics), который часто содержит информацию, полезную при поиске и устранении ошибок.  <br/> |
|**Время присоединения (мс)** <br/> |Нет  <br/> |Период времени (в миллисекундах), требуемый для присоединения пользователя к конференции.  <br/> |
|**Пользователь-отправитель** <br/> |Нет  <br/> |SIP-адрес пользователя, инициировавшего вызов.  <br/> |
|**Агент пользователя, инициатора сеанса** <br/> |Нет  <br/> |Программное обеспечение, используемое конечной точкой пользователя, инициировавшего звонок.  <br/> |
|**Пользователь-получатель** <br/> |Нет  <br/> |SIP-адрес пользователя, принявшего звонок.  <br/> |
   

