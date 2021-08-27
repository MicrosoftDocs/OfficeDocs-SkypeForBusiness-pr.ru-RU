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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Администраторы управляют тем, как организаторы могут использовать бесплатные номера для их собраний.
ms.openlocfilehash: 5ae82a1eef27793f700c50936e9dec37cd6c9ddd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587939"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Отключение бесплатных номеров для определенных пользователей Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
 
> [!Note]
> Для получения информации об отключении бесплатных номеров для пользователей Teams см.  [Отключение бесплатных номеров для определенных пользователей Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Если в организации имеются бесплатные номера моста аудиоконференций Microsoft, можно разрешить или запретить их использование на собраниях определенных организаторов.  

По умолчанию для всех пользователей в организации разрешены бесплатные номера, что означает, что эти номера (при наличии) могут использовать участники для присоединения к собраниям. Если это является нежелательным для некоторых пользователей в организации, можно запретить для определенных пользователей использование этих номеров на собраниях с помощью средства управления бесплатными номерами. 

Если бесплатные номера отключены для определенного организатора 
 - Бесплатный номер не будет включен в приглашения на собрания. 
 - Бесплатные номера не будут указаны в списке на странице «Найти локальный номер», на которую ссылаются приглашения на собрания. 
 - Участники не смогут присоединиться к собранию указанного организатора при наборе любого бесплатного номера организации. 
 - Все собрания организатора будут автоматически перенесены, а бесплатный номер будет удален из них.  

    > [!IMPORTANT]
    > При этом будут повторно отправлены все приглашения электронной почты организатора всем участникам этих собраний. 

 - Участники могут продолжать присоединяться к собраниям организатора с помощью бесплатных номеров. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Отключение бесплатных номеров для определенных пользователей 

В Центре **Microsoft Teams администрирования:**

1. В левой области навигации щелкните **Пользователи** и выберите пользователя из списка доступных пользователей.

2. Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.

3. Установить **Включить бесплатные номера в запросы на** собрания от этого пользователя в **выключенное .** 

4. Нажмите **кнопку Сохранить.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Использование PowerShell**  

Можно использовать параметр AllowTollFreeDialIn Set-CsOnlineDialInConferencingUser командлета Set-CsOnlineDialInConferencingUser, чтобы включить или отключить этот параметр. Например: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
