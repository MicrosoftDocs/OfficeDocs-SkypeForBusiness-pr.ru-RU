---
title: Политики ограничений для исходящих звонков аудиоконференций и пользовательских звонков по ТСОП
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: Администраторы могут определять доступные пользователям типы аудиоконференций и вызовов конечных пользователей по ТСОП.
ms.openlocfilehash: 830ab45178c10ab485d50aafd66a4bf5d4db9011
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836889"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Политики ограничений для исходящих звонков аудиоконференций и пользовательских звонков по ТСОП

Как администратор, вы можете использовать элементы управления исходящими вызовами для ограничения типов аудиоконференций и вызовов конечных пользователей по ТСОП, доступных пользователям в вашей организации. 

Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls. 

|Управления|Описание|Параметры элемента управления|
|:-----|:-----|:-----|
|Вызовы аудиоконференции по ТСОП|Ограничивает тип исходящих </br>вызовов, которые разрешено выполнять </br>во время собраний, организованных пользователем.|Международные и внутренние (по умолчанию)</br>Внутренний</br>Нет|
|Вызовы конечных пользователей по ТСОП|Ограничивает тип вызовов, </br>доступных пользователю.|Международные и внутренние (по умолчанию)</br>Внутренний</br>Нет|

   > [!NOTE]
   > Звонок считается внутренним, если номер набирается в той же стране, в которой была настроена программа Office 365 для организатора собрания (в случае голосовой конференции) или конечных пользователей (в случае с ТЕЛЕФОНными звонками для конечных пользователей). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Ограничение исходящих вызовов аудиоконференций 

![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**

1. На панели навигации слева выберите пункт **Пользователи**, а затем выберите пользователя из списка доступных пользователей.

2. В верхней части страницы нажмите кнопку **изменить**.

3. Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.

4. В разделе **Разрешение на телефонные вызовы во время собраний**выберите нужный параметр ограничения телефонных вызовов.

5. Нажмите кнопку **Сохранить**. 

![Значок с логотипом Skype для бизнеса](media/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**

1.  В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите в раздел**Пользователи** **голосовой конференции** > и выберите пользователя из списка доступных пользователей.

2.  In the Action pane, click **Edit**.

3.  В разделе **Ограничение телефонных вызовов во время собраний с этим пользователем** выберите нужный параметр ограничения телефонных вызовов.

    ![Параметры ограничения исходящих вызовов](media/restrictions-to-dial-outs.png)

5. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Использование PowerShell**

Outbound call restrictions are controlled by a single policy called OnlineDialOutPolicy which has a restriction attribute for each. The policy cannot be customized, rather there are pre-defined policy instances for each combination of the settings. 

You can use the Get-CSOnlineDialOutPolicy cmdlet to view the outbound calling policies and assign them to users by using the Grant-CSDialOutPolicy cmdlet. (Please note that the Grant cmdlet doesn’t contain the word “Online” as the Get cmdlet does.) 

В следующей таблице представлена общая информация о каждой политике.

|||
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь также может выполнять внутренние и международные исходящие вызовы.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять внутренние и международные исходящие вызовы.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера. Этот пользователь может выполнять внутренние и международные исходящие вызовы.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    Пользователь, участвующий в аудиоконференции, может звонить на внутренние и международные телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    Пользователь, участвующий в аудиоконференции, может звонить только на внутренние телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять только внутренние исходящие вызовы по ТСОП.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    Пользователь, участвующий в аудиоконференции, не может звонить на любые телефонные номера; этот пользователь может выполнять исходящие вызовы по ТСОП только на номера экстренной связи.    |
