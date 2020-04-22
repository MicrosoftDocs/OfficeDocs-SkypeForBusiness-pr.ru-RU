---
title: Управлять пользовательскими параметрами аудиоконференций Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'В учетной записи администратора Office 365 можно по отдельному пользователю организации вносить изменения в параметры аудиоконференций Skype для бизнеса Online, такие как поставщик, номера платной или бесплатной линии по умолчанию, идентификатор конференции или PIN-код. '
ms.openlocfilehash: fe6814bee547e80d6bcb6fc367d055dce13d513d
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777994"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-skype-for-business-online"></a>Управлять пользовательскими параметрами аудиоконференций Skype для бизнеса Online

> [!Note]
> Для сведений по управлению пользовательскими параметрами в Microsoft Teams см. [Управлять пользовательскими параметрами аудиоконференций в Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-a-user-in-teams).

As an Office 365 admin, you can edit the Audio Conferencing settings—such as the provider, default toll or toll-free number, conference ID, or PIN—for an individual user in your organization. If you want to edit settings for your organization, see [Manage the Audio Conferencing settings for my organization](manage-the-audio-conferencing-settings-for-my-organization.md).

 
1. Войдите в свою рабочую или учебную учетную запись.
    
2. Выберите **Центры администрирования** > **Skype для бизнеса**.
    
3. В центре администрирования Skype для бизнеса выберите пункт **Пользователи**.
    
4. Выберите пользователя, параметрами которого необходимо управлять, затем в панели «Действия» нажмите **Изменить**![, чтобы отобразить значок функции «Изменить»](../images/4d8bea48-be68-4e0e-a54c-73decf7ea4ec.png).
    
5. В левой панели навигации выберите **Аудиоконференция** , затем на странице пользователя — « **Свойства** », и внесите изменения в любые из следующих параметров:
    
|**Параметр**|**Описание**|
|:-----|:-----|
|**Имя поставщика** <br/> |Выберите поставщика из списка.  <br/><br/> **Примечание:** остальные параметры в этой таблице применяются только в том случае, если выбрать Microsoft в качестве поставщика аудиоконференций.           |
|**Бесплатный номер по умолчанию** (обязательно) <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Бесплатные номера по умолчанию** <br/> |For a third-party providers, these phone numbers are the ones you received from the audio conferencing provider. If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge. Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.  <br/> |
|**Разрешить использование бесплатных номеров в канале Microsoft своей организации, чтобы подключиться к собранию данного пользователя** <br/> |Выберите эту опцию, чтобы разрешить пользователю бесплатных номеров подключаться к собраниям.  <br/> |
|**Отправка сведений о конференции по электронной почте** <br/> |Click this link only if you want to immediately send an email to the user with his or her conference ID and phone number. (This email does not include the PIN.) See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).  <br/> |
|**Идентификатор конференции** <br/> |Select **Reset** if you need to reset the conference ID for the user. For more information, see [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).  <br/> |
|**КРЕПЛЯТЬ** <br/> |Select **Reset** if you need to reset the PIN for the user. For more information, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).  <br/> |
|**Разрешить неаутентифицированным абонентам быть первыми в собрании** <br/> |Выберите эту опцию, чтобы разрешить неаутентифицированным абонентам подключиться к собраниям первыми.  <br/> |
|**Ограничения на исходящие соединения в собраниях этого пользователя** <br/> |Выберите опцию в этом списке, чтобы установить ограничения на исходящие соединения с национальными сетями или заблокировать все исходящие соединения в собраниях.  <br/> |
  
![Отображается страница свойств аудиоконференции для пользователя](../images/228550f7-92be-416d-9ab1-7c2ef54dd4e6.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Статьи по теме

[Управление настройками аудиоконференции для организации](manage-the-audio-conferencing-settings-for-my-organization.md)

[Общие вопросы об аудиоконференциях](/MicrosoftTeams/audio-conferencing-common-questions)
