---
title: Планирование маршрутизации исходящих голосовых вызовов в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
description: Learn about outbound voice routing in Skype for Business Server Enterprise Voice, including call routing settings, dial plans, normalization rules, voice policies, PSTN usage records, and voice routes.
ms.openlocfilehash: 9a26f734faaa7bb070c826a427b47f805ad7438f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-outbound-voice-routing-in-skype-for-business-server-2015"></a>Планирование маршрутизации исходящих голосовых вызовов в Skype для бизнеса Server 2015
 
Learn about outbound voice routing in Skype for Business Server Enterprise Voice, including call routing settings, dial plans, normalization rules, voice policies, PSTN usage records, and voice routes.
  
Outbound call routing applies to Enterprise Voice calls that are destined for a public switched telephone network (PSTN) gateway, trunk, or private branch exchange (PBX). When a Skype for Business user places a call, the server normalizes the phone number to E.164 format, if necessary, and attempts to match it to a SIP URI. При невозможности сопоставления на сервере применяется логическая схема маршрутизации исходящих вызовов на основе представленной строки набора. Эта логическая схема задается путем настройки параметров сервера, описание которых приведено в следующей таблице.
  
**Skype for Business Server Outbound Call Routing Settings**

|**Object**|**Описание**|
|:-----|:-----|
|Абонентская группа  <br/> |Абонентская группа — это именованный набор правил нормализации, которые преобразуют номера телефонов для именованного расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для авторизации телефонов и маршрутизации вызовов.  <br/> |
|Правило нормализации  <br/> |Правила нормализации указывают, как телефонные номера, выраженные в разных форматах, должны маршрутизироваться для каждого конкретного расположения, пользователя или контактного объекта. Одна и та же строка набора может интерпретироваться и преобразовываться по-разному в зависимости от местоположения, из которого она была набрана, и лица или контактного объекта, выполнившего вызов. Ряд правил нормализации, связанный с конкретным расположением, составляет абонентскую группу.  <br/> |
|Политика голосовой связи  <br/> |Политика голосовой связи связывает одну или несколько записей режима работы с ТСОП с одним пользователем или группой пользователей. Политика голосовой связи также предоставляет список функций вызовов, которые можно включать или отключать.  <br/> |
|Запись режима работы с ТСОП  <br/> |Запись режима работы с ТСОП задает класс вызовов (например, внутренний, местный или междугородный), которые могут выполняться разными пользователями или группами пользователей в организации.  <br/> |
|Маршрут вызова  <br/> |Маршрут вызова связывает телефонные номера назначения с конкретными каналами и записями режимов работы с ТСОП. Шлюз ТСОП рассматривается как магистраль.  <br/> |
   
## <a name="dial-plans-and-normalization-rules"></a>Абонентские группы и правила нормализации

Абонентская группа — это именованный набор правил нормализации, которые преобразуют номера телефонов для именованного расположения, отдельного пользователя или контактного объекта в единый стандартный формат (E.164) для авторизации телефонов и маршрутизации вызовов. 
  
Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в требуемое расположение, требуемому пользователю или контактному объекту. Одна и та же строка набора номера может интерпретироваться и преобразовываться по-разному в зависимости от расположения, в котором она была набрана, и лица или контактного объекта, разместившего вызов.
  
### <a name="dial-plan-scope"></a>Область абонентской группы

Область действия абонентской группы определяет уровень иерархии, на котором возможно применение данной абонентской группы. In Skype for Business Server, a user can be assigned a specific per-user dial plan. If a user dial plan is not assigned, the Front End pool dial plan is applied. If there is no Front End pool pool dial plan, the site dial plan is applied. Наконец, если к пользователя не применимы никакие другие абонентские группы, применяется глобальная абонентская группа.
  
Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Skype for Business. As the administrator, you can manage and assign dial plan scope levels by using Skype for Business Server Control Panel.
  
> [!NOTE]
> Абонентская группа шлюза телефонной сети общего пользования (ТСОП) уровня служб применяется к входящим звонкам с конкретного шлюза. 
  
Уровни области абонентской группы определяются следующим образом.
  
- **Абонентская группа пользователей**: может быть назначена отдельным пользователям, группам или контактным объектам. Голосовые приложения могут запрашивать абонентскую группу на уровне пользователей в случае получения звонка, для которого установлено пользовательское значение по умолчанию телефонного контекста. В рамках назначения абонентской группы контактный объект считается отдельным пользователем.
    
- **Абонентская группа пула**: создается на уровне службы для любого шлюза ТСОП или пула регистратора в топологии организации. Для определения абонентской группы пула необходимо указать конкретную службу (шлюз ТСОП или пул регистратора), к которой применяется абонентская группа. 
    
- **Абонентская группа сайтов**: может создаваться для всего сайта за исключением пользователей, групп или контактных объектов, которым назначена абонентская группа пулов или абонентская группа пользователей. Чтобы определить абонентскую группу, следует указать сайт, к которому она применяется.
    
- **Глобальная абонентская группа**: абонентская группа по умолчанию, установленная вместе с продуктом. Вы можете изменить глобальную абонентскую группу, но не можете удалить ее. This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.
    
### <a name="planning-for-dial-plans"></a>Планирование абонентских групп

Для планирования абонентской группы выполните следующие действия.
  
- Укажите все адреса, по которым у вашей организации есть офис.
    
    Этот список должен быть полным и актуальным. По мере роста и развития организации его следует пересматривать. В большой международной компании с большим количеством небольших филиалов эта задача может потребовать довольно много времени.
    
- Укажите допустимые шаблоны номеров для каждого сайта.
    
    Наиболее трудоемкой частью планирования абонентские группы является определение допустимых шаблонов номеров для каждого сайта. В некоторых случаях, возможно, получится скопировать правила нормализации, созданные для одной абонентской группы, в другие группы (особенно если соответствующие сайты находятся в пределах той же страны или региона или даже континента). В других случаях внесение небольших изменений в номера одной абонентской группы может быть достаточным для их использования в других абонентских группах.
    
- Разработайте схему для именования абонентских групп в рамках всей организации.
    
    Принятие стандартной схемы именования гарантирует согласованность данных в пределах организации и упрощает решение задач обслуживания и обновления.
    
- Решите, требуется ли использовать несколько абонентских групп для одного расположения. 
    
    If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.
    
- Решите, требуются ли абонентские группы для индивидуальных пользователей. For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules. For details, see [Plan for Enterprise Voice resiliency in Skype for Business Server 2015](enterprise-voice-resiliency.md).
    
- Определите область абонентской группы (как описано выше в данном разделе).
    
To create a dial plan, you specify values in the following fields, as required, by using Skype for Business Server Control Panel or Skype for Business Server Management Shell.
  
#### <a name="name-and-simple-name"></a>Имя и простое имя

Для абонентских групп пользователей следует указать информативное имя, указывающее пользователей, группы или контактные объекты, которым будет назначена данная абонентская группа. Для абонентских групп сайтов поле "Имя" предварительно заполнено именем сайта и не может быть изменено. For pool dial plans, the Name field is pre-populated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.
  
The dial plan Simple Name is pre-populated with a string that is derived from the dial plan name. Поле "Простое имя" доступно для редактирования, что позволяет создать для абонентских групп информативное соглашение об именовании. TheSimple Name value cannot be empty and must be unique. Рекомендуется разработать соглашение об именовании для всей организации и последовательно применять его для всех сайтов и пользователей.
  
#### <a name="description"></a>Описание

Рекомендуется вводить общеупотребительные узнаваемые имена географических расположений, к которым применяются соответствующие абонентские группы. Например, если имя абонентской группы — London.Contoso.com, рекомендуемым описанием будет "Лондон". 
  
#### <a name="dial-in-conferencing-region"></a>Регион конференц-связи с телефонным подключением

Если выполняется развертывание конференц-связи с телефонным подключением, необходимо указать регион конференц-связи с телефонным подключением, чтобы связать соответствующие номера доступа с абонентской группой. 
  
#### <a name="external-access-prefix"></a>Префикс внешнего доступа

You can specify an external access prefix of up to four characters (#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.
  
> [!NOTE]
> Если указан префикс внешнего доступа, не требуется создавать дополнительное правило нормализации для обработки префикса. 
  
### <a name="normalization-rules"></a>Правила нормализации

Правила нормализации определяют, как номера телефонов, заданные в различных форматах, перенаправляются в заданное расположение. Одна и та же строка номера может интерпретироваться и преобразовываться по-разному в зависимости от адреса, в котором она была набрана. Правила нормализации необходимы для маршрутизации вызовов, так как пользователи могут использовать и используют различные форматы при вводе номеров телефонов в своих списках контактов.
  
Нормализация указанных пользователями номеров телефонов позволяет получить согласованный формат, облегчающий выполнение следующих задач.
  
- Match a dialed number to the intended recipient's SIP-URI.
    
- Применение правил авторизации набора номера к вызывающей стороне.
    
Следующие поля номера могут потребоваться правилу нормализации при обработке набираемого номера.
  
- Абонентская группа
    
- Код страны
    
- Код города
    
- Длина расширения
    
- Префикс сайта
    
#### <a name="creating-normalization-rules"></a>Создание правил нормализации

Правила нормализации используют регулярные выражения .NET Framework для указания шаблонов совпадения номеров, используемых сервером для преобразования строк набора номера в формат E.164 с целью выполнения обратного поиска номеров. You create normalization rules in the Skype for Business Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Skype for Business Server Control Panel generate the corresponding regular expression for you. В любом случае после завершения вы можете ввести тестовый номер, чтобы убедиться в правильной работе правил нормализации.
  
For details about using .NET Framework regular expressions, see [".NET Framework Regular Expressions"](https://go.microsoft.com/fwlink/p/?linkId=140927).
  
#### <a name="sample-normalization-rules"></a>Примеры правил нормализации
<a name="BKMK_SampleNormalizationRules"> </a>

В следующей таблице приведены примеры правил нормализации, написанных в виде регулярных выражений .NET Framework. Эти примеры приведены только для справки, поэтому не следует рассматривать их в качестве рекомендаций по созданию правил.
  
**Table 1.Normalization Rules Using .NET Framework Regular Expressions**

|**Имя правила**|**Описание**|**Шаблон номеров**|**Преобразование**|**Пример**|
|:-----|:-----|:-----|:-----|:-----|
|4digitExtension  <br/> |Преобразование 4-значных расширений  <br/> |^(\d{4})$  <br/> |+1425555$1  <br/> |0100 преобразуется в +14255550100  <br/> |
|5digitExtension  <br/> |Преобразование 5-значных расширений  <br/> |^5(\d{4})$  <br/> |+1425555$1  <br/> |50100 преобразуется в +14255550100  <br/> |
|7digitcallingRedmond  <br/> |Преобразование 7-значных номеров в локальные номера Редмонда  <br/> |^(\d{7})$  <br/> |+1425$1  <br/> |5550100 преобразуется в +14255550100  <br/> |
|7digitcallingDallas  <br/> |Преобразование 7-значных номеров в локальные номера Далласа  <br/> |^(\d{7})$  <br/> |+1972$1  <br/> |5550100 преобразуется в +19725550100  <br/> |
|10digitcallingUS  <br/> |Преобразование 10-значных номеров в номера США  <br/> |^(\d{10})$  <br/> |+1$1  <br/> |2065550100 преобразуется в +12065550100  <br/> |
|LDCallingUS  <br/> |Преобразование номеров с междугородными префиксами в номера США  <br/> |^1(\d{10})$  <br/> |+$1  <br/> |12145550100 преобразуется в +2145550100  <br/> |
|IntlCallingUS  <br/> |Преобразование номеров с международными префиксами в номера США  <br/> |^011(\d\*)$  <br/> |+$1  <br/> |01191445550100 преобразуется в +91445550100  <br/> |
|RedmondOperator  <br/> |Преобразование 0 в оператора Редмонда  <br/> |^0$  <br/> |+14255550100  <br/> |0 преобразуется в +14255550100  <br/> |
|RedmondSitePrefix  <br/> |Преобразование номеров с сетевым префиксом (6) и кодами сайта Редмонда (222)  <br/> |^6222(\d{4})$  <br/> |+1425555$1  <br/> |62220100 преобразуется в +14255550100  <br/> |
|NYSitePrefix  <br/> |Преобразование номеров с сетевым префиксом (6) и кодами сайта Нью-Йорка (333)  <br/> |^6333(\d{4})$  <br/> |+1202555$1  <br/> |63330100 преобразуется в +12025550100  <br/> |
|DallasSitePrefix  <br/> |Преобразование номеров с сетевым префиксом (6) и кодами сайта Далласа (444)  <br/> |^6444(\d{4})$  <br/> |+1972555$1  <br/> |64440100 преобразуется в +19725550100  <br/> |
   
В следующей таблице приводится пример абонентской группы для сайта Редмонда (шт. Вашингтон, США) на основе правил нормализации, приведенных в предыдущей таблице.
  
**Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1**

|**Redmond.forestFQDN**|
|:-----|
|5digitExtension  <br/> |
|7digitcallingRedmond  <br/> |
|10digitcallingUS  <br/> |
|IntlCallingUS  <br/> |
|RedmondSitePrefix  <br/> |
|NYSitePrefix  <br/> |
|DallasSitePrefix  <br/> |
|RedmondOperator  <br/> |
   
> [!NOTE]
> Имена правил нормализации, приведенные в предыдущей таблице, не включают пробелы, но это не является обязательным требованием. Например, первое имя в таблице можно записать как "5 значное расширение" или "5-значное расширение", и оно будет допустимым. 
  
## <a name="voice-policies"></a>Политики голосовой связи

Skype for Business Server voice policies define the following for each user, site, or organization that is assigned the policy:
  
- A set of calling features that can be enabled or disabled to determine the Enterprise Voice functionality available to users.
    
- набор режимов работы с ТСОП, который определяет разрешенные типы звонков. 
    
The following steps will help you plan the voice policies that you will need for your Enterprise Voice deployment:
  
- Determine how you will configure your global voice policy (the default voice policy that is installed with the product). This policy will apply to all Enterprise Voice users who are not explicitly assigned a site-level or per-user policy.
    
- Определение требуемых политик голосовой связи на уровне сайта.
    
- Определение требуемых политик голосовой связи на уровне пользователя.
    
- Определение функций звонков, которые будут включены для каждой политики голосовых служб.
    
- Определение режимов работы с ТСОП, задаваемых для каждой политики голосовых служб.
    
### <a name="voice-policy-scope"></a>Область политики голосовых служб

Voice policy scope determines the hierarchical level at which the policy can be applied. In Skype for Business Server, you can configure voice policies with the following scope levels (listed from the most specific to the most general).
  
- **Политика голосовой связи на уровне пользователя** может быть назначена отдельным пользователям, группам или контактным объектам. Это политика самого низкого уровня. С помощью пользовательских политик голосовой связи можно включить функции для определенных пользователей или групп пользователей сайта. Например, вам может потребоваться отключить международную связь для некоторых сотрудников. При назначении политики голосовой связи контактный объект рассматривается как отдельный пользователь.
    
    > [!NOTE]
    > We recommend that you deploy a user voice policy for branch site Enterprise Voice users who are registered with the central site deployment, or users who are registered on a Survivable Branch Appliance. 
  
- **Политика голосовой связи на уровне сайта** применяется ко всему сайту за исключением пользователей, групп или контактных объектов, которым назначена политика голосовой связи на уровне пользователя. Чтобы определить политику голосовой связи на уровне сайта, вам нужно указать сайт, к которому применяется политика. Если политика голосовой связи на уровне пользователя не назначена, то используется политика голосовой связи на уровне сайта.
    
- **Глобальная политика голосовой связи** — это политика голосовой связи по умолчанию, которая устанавливается вместе с продуктом. Вы можете изменять глобальную политику голосовой связи в соответствии с потребностями организации, однако вы не можете переименовывать или удалять ее. This voice policy applies to all Enterprise Voice users, groups, and contact objects in your deployment unless you configure and assign a voice policy with more specific scope. Если вы хотите полностью отключить эту политику, убедитесь в том, что для всех сайтов и пользователей назначены настраиваемые политики.
    
### <a name="call-features"></a>Функции звонков

Для каждой политики голосовых служб можно включать или отключать следующие функции звонков.
  
- **Переадресация звонков** позволяет пользователям переадресовывать звонки на другие телефоны и устройства клиента. По умолчанию данная возможность включена.
    
- **Делегирование** позволяет пользователям указывать других пользователей, которые могут выполнять и принимать звонки от их имени. Включена по умолчанию.
    
- **Переключение звонка** позволяет пользователям передать звонок другим пользователям. По умолчанию данная возможность включена.
    
- **Парковка звонка** позволяет пользователям приостанавливать звонки и затем извлекать их на другом телефоне или клиенте. По умолчанию данная возможность отключена.
    
- **Одновременные звонки** позволяет принимать входящие звонки на дополнительном телефоне (например, мобильном телефоне) или других оконечных устройствах. По умолчанию данная возможность включена.
    
- **Групповой звонок** позволяет пользователям из заданной группы отвечать на звонки, предназначенные другим членам этой группы. По умолчанию данная возможность включена.
    
- **Перенаправление ТСОП** позволяет перенаправлять в ТСОП звонки пользователей, которым назначена эта политика, другим пользователям организации, если глобальная сеть перегружена или недоступна. По умолчанию данная возможность включена.
    
- **Переопределение политики пропускной способности** позволяет администраторам переопределять политику контроля допуска звонков для отдельного пользователя. По умолчанию данная возможность отключена.
    
- **Malicious call tracing** enables users to report malicious calls by using the Skype for Business client, and then flags such calls in the call detail records. По умолчанию эта функция отключена.
    
- **Voicemail escape** prevents calls from being immediately routed to the user's mobile phone voicemail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range, and is based on a timer value. Этот параметр включает или отключает таймер и задает его значение. It can be configured only by using the Skype for Business Server Management Shell. По умолчанию эта функция отключена.
    
- **Call forwarding and simultaneous ringing PSTN usages** enables administrators to specify the same PSTN usage as the voice policy for call forwarding and simultaneous ringing, restrict call forwarding and simultaneous ringing to internal Skype for Business users only, or specify a custom PSTN usage that is different from the voice policy's PSTN usage. По умолчанию в ТСОП применяется режим переадресации вызовов и одновременного приема вызовов, указанный в политике голосовой связи.
    
### <a name="pstn-usage-records"></a>Записи использования ТСОП

С каждой политикой голосовой связи должна быть связана хотя бы одна запись, определяющая режим работы ТСОП. Режимы работы ТСОП, связанные с политикой голосовой связи, относятся только к одновременному приему вызовов и переадресации вызовов. 
  
> [!NOTE]
> Порядок указания режимов работы с ТСОП является критически важным, поскольку при сопоставлении пользователей с маршрутами функция исходящей маршрутизации сравнивает режимы работы с ТСОП сверху вниз. Если первый режим соответствует маршруту звонка, то будет использоваться этот маршрут. В противном случае функция исходящей маршрутизации выполняет поиск следующего режима работы с ТСОП до тех пор, пока соответствие не будет найдено. По сути последующие режимы работы с ТСОП представляют собой резервные копии, если первый режим в списке недоступен. 
  
## <a name="pstn-usage-records"></a>Записи использования ТСОП

Planning PSTN usage records consists mainly of listing all the call permissions that are currently in force in your organization, from the CEO to temporary workers, consultants, and contingent staff. This process also provides an opportunity to reexamine existing call permissions and revise them. You can create PSTN usage records only for those call permissions that apply to your anticipated Enterprise Voice users, but a better long-range solution might be to create PSTN usage records for all call permissions, regardless of whether some may not currently apply to the group of users to be enabled for Enterprise Voice. If call permissions change or new users with different call permissions are added, you will have already created the required PSTN usage records.
  
В следующей таблице приведены типичные режимы работы с ТСОП.
  
**PSTN Usage Records**

|**Phone attribute**|**Описание**|
|:-----|:-----|
|Local  <br/> |Местные звонки  <br/> |
|Long-Distance  <br/> |Междугородние звонки  <br/> |
|International  <br/> |Международные звонки  <br/> |
|Delhi  <br/> |Штатные сотрудники, расположенные в г. Дели  <br/> |
|Redmond  <br/> |Штатные сотрудники, расположенные в г. Редмонд  <br/> |
|RedmondTemps  <br/> |Временные сотрудники, расположенные в г. Редмонд  <br/> |
|Zurich  <br/> |Штатные сотрудники, расположенные в г. Цюрих  <br/> |
   
Сами по себе режимы работы с ТСОП не выполняют никаких действий. Чтобы режимы работы с ТСОП начали работать, необходимо связь их со следующими данными:
  
- Политики голосовых служб, назначенные пользователям.
    
- Маршруты, назначенные номерам телефонов.
    
## <a name="voice-routes"></a>Маршруты голосовых вызовов

Call routes specify how Skype for Business Server handles outbound calls placed by Enterprise Voice users. When a user dials a number, the Front End Server normalizes the dial string to E.164 format, if necessary, and attempts to match it to a SIP URI. Если серверу не удается найти соответствие, он применяет к исходящему звонку логику маршрутизации на основании номера. Завершающий шаг в определении этой логики состоит в создании отдельного именованного маршрута звонка для каждого набора конечных номеров телефона, указанных в абонентской группе.
  
Перед определением маршрутов исходящих звонков необходимо выполнить следующие действия.
  
- Развернуть как минимум одну магистральную линию связи.
    
- При необходимости создать абонентские группы для сайтов, отдельных пользователей или контактных объектов.
    
- Создать режимы работы с ТСОП.
    
Кроме того, для включения маршрутизации исходящих звонков необходимо создать и назначить как минимум одну политику голосовых служб. Это можно выполнить как перед определением маршрутов исходящих звонков, так и после.
  
Для каждого маршрута необходимо указать следующее.
  
- Имя, позволяющее легко идентифицировать соответствующий маршрут.
    
- Описание, если для описания маршрута одного имени недостаточно (необязательно).
    
- Регулярное выражение для шаблона поиска соответствия, которое идентифицирует конечные номера телефонов, к которым применяется маршрут, а также исключения, к которым шаблон поиска соответствия не применяется
    
- Одна или более магистральных линий связи, которые необходимо назначить маршруту.
    
- Режимы работы с ТСОП, требуемые пользователям для обеспечения соответствия номеров телефонов регулярному выражению для конечных номеров телефонов.
    
You can specify call routes in the Skype for Business Server Control Panel. These call routes populate the server routing table, which Skype for Business Server uses to route calls that are destined for the PSTN.
  
### <a name="mn-trunk-support"></a>Поддержка магистрали M:N

Skype for Business Server provides flexibility in how calls are routed to the PSTN. Маршрут голосовых вызовов указывает набор магистральных линий связи, используемых для связи с ТСОП, которая может использоваться для конкретного голосового звонка. A trunk associates a Mediation Server and a port number with a PSTN gateway and listening port number. This logical association enables a Mediation Server to be associated with multiple gateways and have multiple connections to the same gateway. When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with the route. To create trunks by defining the relationships between Mediation Servers and PSTN gateways, IP-PBXs, and Session Border Controllers (SBCs), use the Topology Builder.
  
### <a name="least-cost-routing"></a>Маршрутизация по принципу наименьшей стоимости

Возможность указания магистральных линий связи, используемых для маршрутизации различных номеров, позволяет определить маршруты, имеющие наименьшую стоимость, и использовать их соответствующим образом. Общее правило выбора магистральной линии связи — выбор магистральной линии связи с ближайшим шлюзом до расположения конечного номера, чтобы минимизировать затраты на международную связь. Например, если вы находитесь в Нью-Йорке и звоните абоненту в Риме, звонок будет передаваться по сети IP в магистральную линию связи со шлюзом в офисе Рима, чтобы плата взималась только за локальный звонок.
  
For an example of how least-cost routing might be used, consider the following: Fabrikam decides to enable German users to dial U.S. numbers by using the U.S. trunk. Fabrikam also wants to configure the system so that all calls from U.S. Skype for Business Server users to Germany and adjacent countries/regions terminate on the trunk with the gateway in Germany. This routing will save money, because a call from Germany to Austria, for example, is less expensive than a call from the U.S. to Austria.
  
### <a name="translating-outbound-dial-strings"></a>Преобразование строк набора исходящих звонков

Skype for Business Server requires all dial strings to be normalized to E.164 format for the purpose of performing reverse number lookup (RNL). For trunks with gateways or private branch exchanges (PBXs) that require numbers translated in local dialing formats, Skype for Business Server enables you to create one or more rules that assist in manipulating the called number (i.e. Request URI) prior to routing it to the trunk. Например, можно составить правило, обеспечивающее удаление префикса +44 в начале строки набора номера с заменой префиксом 0144.
  
With Skype for Business Server, it is possible to create one or more rules that assist in manipulating the calling number prior to routing it to the trunk.
  
In planning your trunks that associate gateway:port pairs with Mediation Server:port pairs, it may be useful to group trunks with similar local dialing requirements, and therefore reduce the number of required translation rules and the time it takes to write them.
  
### <a name="configuring-caller-id"></a>Настройка идентификатора вызывающего абонента

Skype for Business Server provides a way to manipulate the caller ID for outbound calls. For example, if an organization wants to mask employees' direct-dial extensions and replace them with the generic corporate or departmental number, an administrator can do that by using Skype for Business Server Control Panel to suppress the caller ID and replace it with a specified alternative caller ID. In planning your routing logic, consider which individuals, groups, sites you'll want this option for—perhaps, even, for all employees.
  
> [!NOTE]
> Для звонков, перенаправляемых через ТСОП, вместо исходного ИД вызывающего абонента будет представлен общий ИД вызывающего абонента. Это может привести к тому, что звонки будут обходить статусы "Не беспокоить" или параметры конфиденциальности, которые могли быть заданы вызываемым. 
  
### <a name="additional-routing-logic"></a>Дополнительная логика маршрутизации

При создании маршрутов исходящих звонков необходимо учитывать следующие факторы, которые могут повлиять на логику маршрутизации.
  
- Если вызов устанавливается через федеративную границу, доменная часть URI используется для маршрутизации звонка в сеть предприятия, которое отвечает за применение логики внешней маршрутизации.
    
- Если часть домена в URI запроса не содержит поддерживаемый домен для организации, компонент внешней маршрутизации на сервере не будет обрабатывать соответствующий вызов.
    
- If a user is not enabled for Enterprise Voice, the server applies other routing logic, as appropriate.
    
- Если вызов перенаправляется в шлюз, который полностью занят (все каналы магистрали заняты), этот шлюз отклоняет вызов, а логика внешней маршрутизации перенаправляет вызов на следующий маршрут с наименьшей стоимостью. Этот сценарий необходимо рассмотреть более подробно, поскольку шлюз, предназначенный для небольших заграничных офисов (например, в Цюрихе), может переносить большой объем нелокального трафика для международных звонков в Швейцарию. Если размер дополнительного трафика шлюза задан неправильно, звонки в Швейцарию могут быть перенаправлены в шлюз в Германии, что приведет к увеличению расходов на международную связь.
    

