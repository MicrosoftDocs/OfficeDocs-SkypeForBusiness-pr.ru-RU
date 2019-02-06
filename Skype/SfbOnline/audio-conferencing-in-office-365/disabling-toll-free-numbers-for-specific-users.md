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
ms.openlocfilehash: f553cc3abad8f4490d06099554c188881ef47e24
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753761"
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

Из **центра администрирования группами Майкрософт**:

1. На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.

2. Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.

3. Значение **включают бесплатные номера в приглашении на собрание из этого пользователя** **из системы**. 

4. Нажмите кнопку **Сохраните.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Использование PowerShell**  

Можно использовать параметр AllowTollFreeDialIn Set-CsOnlineDialInConferencingUser командлета Set-CsOnlineDialInConferencingUser, чтобы включить или отключить этот параметр. Например: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
