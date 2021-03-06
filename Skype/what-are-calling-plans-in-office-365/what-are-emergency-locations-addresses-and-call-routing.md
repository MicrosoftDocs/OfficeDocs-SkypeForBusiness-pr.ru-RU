---
title: "Что такое местоположения для экстренного реагирования, адреса для экстренного реагирования и маршрутизация экстренных вызовов?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.AddressAndLocation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
description: "Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. "
---

# Что такое местоположения для экстренного реагирования, адреса для экстренного реагирования и маршрутизация экстренных вызовов?

При настройке планов звонков Office 365 необходимо назначить каждому телефонному номеру адрес для экстренного реагирования. Это нужно сделать либо при получении номера, либо при назначении номера пользователю для поддержки экстренных вызовов. Прежде чем назначать адрес, его необходимо создать и проверить. Проверка позволит гарантировать, что адрес является допустимым, имеет корректный формат и его могут использовать службы экстренного реагирования. При необходимости вы можете указать более точное местоположение пользователя, например этаж, крыло или офис по конкретному адресу. В отличие от адресов для экстренного реагирования проверять эти местоположения не нужно.
  
## Что такое адреса для экстренной связи?

Адрес для экстренного реагирования является обязательным для действующих телефонных номеров, но то, когда его нужно указывать, зависит от страны или региона. В США такой адрес **требуется** при назначении номера пользователю. В других странах, например в Европе, Африке и на Ближнем Востоке (регион EMEA), адрес для экстренного реагирования **требуется** при получении телефонного номера в Office 365 либо при передаче номера от другого оператора или поставщика услуг.
  
В качестве адреса для экстренного реагирования используется физический адрес с указанием улицы и номера дома. Это должен быть непосредственный адрес офиса, где работает ваша организация, например:  *129343, Москва, проезд Серебрякова, д. 2, корп. 1, 9 этаж*  . При экстренном вызове этот адрес используется для поиска ближайших экстренных служб и должен помочь оперативно найти звонящего. Если ваша компания имеет несколько офисов, возможно, имеет смысл указать несколько физических адресов.
  
Нужно обязательно подтвердить, что адрес существует официально и указан в правильном формате, чтобы с ним могли работать экстренные службы. Вы можете создавать и хранить неподтвержденные адреса, но не можете назначать их пользователям. Назначение доступно только после проверки и сохранения. Если вам нужно изменить сохраненный проверенный адрес, создайте для этого новый.
  
## Что такое местоположения для экстренного реагирования?

Местоположения для экстренного реагирования связаны с адресом для экстренного реагирования и дают более точное представление о конкретном месте в здании. Обычно это этаж, крыло или номер офиса, где находится пользователь. Вы можете задать для адреса сколько угодно таких местоположений.
  
Адрес для экстренного реагирования, назначаемый пользователю, фактически является идентификатором местоположения, на который идет ссылка при назначении адреса. Идентификатор местоположения содержит указанный адрес для экстренного реагирования (улицу или физический адрес). В случаях, когда внутреннее местоположение указывать не требуется, в каждый адрес для экстренного реагирования включается стандартное местоположение для экстренного реагирования. 
  
## Что такое маршрутизация экстренных вызовов?

Вышеуказанные адреса и местоположения используются для перенаправления экстренных вызовов в ближайший диспетчерский центр экстренных служб. Когда пользователь Skype для бизнеса набирает номер экстренной службы, его вызов перенаправляется в необходимую дежурно-диспетчерскую службу, которая в разных странах и регионах определяется по-разному. В некоторых странах, например в Великобритании и США, сначала определяется текущее местоположение абонента, после чего звонок соединяется с диспетчерским центром, ответственным за эту точку. В других странах и регионах звонки направляются непосредственно в диспетчерский центр, который обслуживает телефонный номер звонящего.
  
## Создание, добавление и назначение пользователям адресов и местоположений для экстренного реагирования

1. **Планирование местоположений для экстренного реагирования**. В первую очередь определите, какие адреса могут потребоваться вам для экстренного реагирования. Укажите все свои физические адреса. Затем, опираясь на них, решите, нужно ли вам уточнять расположение. Например, если у организации три четырехэтажных офисных здания, укажите три адреса для экстренного реагирования и дополнительно этажи с первого по четвертый для каждого из них.
    
2. **Создание и проверка местоположений для экстренного реагирования** Следующий этап  создание и проверка адресов для экстренного реагирования. Созданный адрес для экстренного реагирования можно проверить. Информацию о создании адреса для экстренного реагирования см. в статье[Добавление или удаление адреса для экстренного реагирования для вашей организации](add-or-remove-an-emergency-address-for-your-organization.md).
    
    > [!IMPORTANT]
    > Нужно обязательно подтвердить, что физический адрес существует официально и указан в правильном формате. В некоторых случаях даже если адрес не полностью верный (например, есть ошибка в названии города), он все равно может пройти проверку. При проверке анализируются все части адреса и определяется, достаточно ли в нем сведений для направления вызова в подходящий диспетчерский центр экстренных служб. Если данных достаточно, процедура проверки вернет адрес как подтвержденный. После этого вы можете назначить его номеру телефона. 
  
3. **Получение номеров телефонов**. Следующий шаг  получение телефонных номеров для ваших пользователей. Вы можете получить их в Office 365 или "перенести" в Office 365 уже имеющиеся у вас телефонные номера. Полные пошаговые инструкции см. в статье [Передача номеров телефонов в Office 365](transfer-phone-numbers-to-office-365.md).
    
4. **Назначение номеров телефонов**. Последний этап  предоставление пользователям возможности совершать и принимать телефонные звонки. Для этого необходимо назначить номер каждому пользователю. Назначение телефонного номера описано в статье [Назначение, изменение или удаление номера телефона пользователя](assign-change-or-remove-a-phone-number-for-a-user.md).
    
## См. Также:

#### 

[Skype для бизнеса Online: отказ от ответственности для экстренных вызовов](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[Условия и положения, распространяющиеся на экстренные вызовы](emergency-calling-terms-and-conditions.md)
  
[Звука по телефону период бесплатных конференц-связи](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

