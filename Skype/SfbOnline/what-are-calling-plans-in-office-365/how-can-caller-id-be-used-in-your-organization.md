---
title: Как можно использовать идентификатор звонящего в организации
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.
ms.openlocfilehash: 9d15d51d0044ae15b04572f0b64a21912cea720a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305436"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Как можно использовать идентификатор звонящего в организации

Идентификатором вызывающего абонента можно управлять для входящих и исходящих вызовов для пользователей телефонной системы с помощью политики, которая называется CallingLineIdentity.
  
Функциональность идентификатора вызывающего абонента доступна для всех пользователей телефонной системы независимо от возможности подключения к сети ТСОП:
  
- Подключение к сети ТСОП
    
- Подключение к локальной сети ТСОП с помощью выпуска облачного соединителя Skype для бизнеса (требуется облачный соединитель 1.4.2 или более позднего выпуска)
    
- Подключение к локальной сети ТСОП с помощью сервера Skype для бизнеса (требуется сервер Skype для бизнеса 2015 CU5 или более поздней версии)
    
> [!NOTE]
> Эта политика недоступна в сервере Skype для бизнеса 2015. 
  
## <a name="outbound-caller-id"></a>Идентификация имени вызывающего абонента

Для идентификации имени вызывающего абонента сети ТСОП доступны три варианта:
  
- Номер телефона, назначенный пользователю, который задан по умолчанию.
    
- A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.
    
- Задан как анонимный.
    
Тем не менее, невозможно назначить эти типы номеров телефонов для идентификатора вызывающего абонента:
  
- Все номера телефонов, которые классифицируются как *пользовательские* в вашем тарифном плане склада телефонных номеров
    
- Локальный номер телефона сервера Skype для бизнеса
    
Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Контроль пользователем идентификатора вызывающего абонента

The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.
  
Конечные пользователи могут установить для идентификатора вызывающего абонента значение **anonymous** с помощью вкладки " **Параметры** " в классическом клиенте Skype **** для бизнеса, выберите команду " **Скрыть мой номер телефона" и сведения о профиле для всех звонков. **.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Версия** <br/> |**Поддерживаются** <br/> |
|Технология «нажми и работай»  <br/> |Текущая платформа канала выпущена 6 декабря 2016 года - версия 1611 (сборка 7571.2072)  <br/> |Да  <br/> |
|Технология «нажми и работай»  <br/> |Первый выпуск для отложенного канала был выпущен 22 февраля 2017 года - версия 1701 (сборка 7766.2060)  <br/> |Да  <br/> |
|Технология «нажми и работай»  <br/> |Отложенный канал выпущен 13 июня 2017 г. - версия 1701 (сборка 7766.2092)  <br/> |Да  <br/> |
|MSI  <br/> |Skype для бизнеса  <br/> |Нет  <br/> |
|Mac  <br/> |Skype для бизнеса  <br/> |Нет  <br/> |
   
## <a name="inbound-caller-id"></a>Идентификация звонящего абонента

The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.
  
Чтобы задать идентификатор вызывающего абонента, см. [Назначение идентификатора абонента пользователю](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
