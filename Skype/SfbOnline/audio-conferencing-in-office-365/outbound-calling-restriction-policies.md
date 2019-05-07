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
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы могут определять доступные пользователям типы аудиоконференций и вызовов конечных пользователей по ТСОП.
ms.openlocfilehash: acd75df192211465071940148e35bc7e269c7976
ms.sourcegitcommit: d1b14268efe334aa93a6889f25fcfe46e07d5daa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2019
ms.locfileid: "33584226"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Политики ограничений для исходящих звонков аудиоконференций и пользовательских звонков по ТСОП

Как администратор, вы можете использовать элементы управления исходящими вызовами для ограничения типов аудиоконференций и вызовов конечных пользователей по ТСОП, доступных пользователям в вашей организации. 

Outbound call controls can be applied on a per-user basis and provide the following two controls to independently restrict each type of outbound calls. By default, both controls are set to allow international and domestic outbound calls. 

|Элемент управления|Описание|Параметры элемента управления|
|:-----|:-----|:-----|
|Вызовы аудиоконференции по ТСОП|Ограничивает тип исходящих </br>вызовов, которые разрешено выполнять </br>во время собраний, организованных пользователем.|Международные и внутренние (по умолчанию)</br>Внутренний</br>Нет|
|Вызовы конечных пользователей по ТСОП|Ограничивает тип вызовов, </br>доступных пользователю.|Международные и внутренние (по умолчанию)</br>Внутренний</br>Нет|

   > [!NOTE]
   > Вызов считается внутри страны, если Набираемый номер в одной стране, где Office 365 настроен для организатора собрания (в случае аудиоконференций) или конечного пользователя (в случае вызовы в ТСОП конечного пользователя). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Ограничение исходящих вызовов аудиоконференций 

![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью центра администрирования группами Майкрософт**

1. На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.

2. В верхней части страницы нажмите кнопку **Изменить**.

3. Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.

4. В разделе **Разрешение на телефонные вызовы во время собраний**выберите нужный параметр ограничения телефонных вызовов.

5. Нажмите кнопку **Сохранить**. 

![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**

1.  В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей.

2.  In the Action pane, click **Edit**.

3.  В разделе **Ограничение телефонных вызовов во время собраний с этим пользователем** выберите нужный параметр ограничения телефонных вызовов.

    ![Параметры ограничения исходящих вызовов](../images/restrictions-to-dial-outs.png)

5. Нажмите кнопку **Сохранить**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

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
