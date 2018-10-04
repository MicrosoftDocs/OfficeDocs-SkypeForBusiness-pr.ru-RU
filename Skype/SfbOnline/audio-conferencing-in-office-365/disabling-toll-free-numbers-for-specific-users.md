---
title: Отключение бесплатных номеров для определенных пользователей Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Администраторы управляют тем, как организаторы могут использовать бесплатные номера для их собраний.
ms.openlocfilehash: 316497b6b4569ffef4419b6ed2ce6994c604d16a
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370614"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Отключение бесплатных номеров для определенных пользователей Skype для бизнеса Online

> [!Note]
> Для получения информации об отключении бесплатных номеров для пользователей Teams см.  [Отключение бесплатных номеров для определенных пользователей Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Если в организации имеются бесплатные номера моста аудиоконференций Microsoft, можно разрешить или запретить их использование на собраниях определенных организаторов.  

By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control. 

Если бесплатные номера отключены для определенного организатора 
 - Бесплатный номер не будет включен в приглашения на собрания. 
 - Бесплатные номера не будут указаны в списке на странице «Найти локальный номер», на которую ссылаются приглашения на собрания. 
 - Участники не смогут присоединиться к собранию указанного организатора при наборе любого бесплатного номера организации. 
 - Все собрания организатора будут автоматически перенесены, а бесплатный номер будет удален из них.  

    > [!IMPORTANT]
    > При этом будут повторно отправлены все приглашения электронной почты организатора всем участникам этих собраний. 

 - Участники могут продолжать присоединяться к собраниям организатора с помощью бесплатных номеров. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Отключение бесплатных номеров для определенных пользователей 


1. В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**, а затем выберите пользователя из списка доступных пользователей. 

2. In the Action pane, click **Edit**. 

3. Снимите флажок **Разрешить использование бесплатных номеров для присоединения к собраниям этого пользователя**. 
 
4. Нажмите кнопку **Сохранить**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Использование PowerShell**  

You can use the AllowTollFreeDialIn parameter of the Set-CsOnlineDialInConferencingUser cmdlet to enable or disable this control. For example: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
