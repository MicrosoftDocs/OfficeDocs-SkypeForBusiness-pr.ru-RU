---
title: Известные проблемы планов звонков
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Изучите известные проблемы, связанные с тарифным планом по КОММУТИРУЕМой телефонной связи и действиями, которые вы можете сделать.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220739"
---
# <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

Планы звонков — это новая функция, которую можно найти в Skype для бизнеса Online. Ниже перечислены проблемы, которые отслеживаются и активно изучаются. Они будут потенциально разрешены, когда функция будет обновлена в последующих сборках.
  
## <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

|**Известная ошибка**|**Примечания**|
|:-----|:-----|
|Переход с лицензий на техническую версию на производственные лицензии на планы звонков не обновляет лицензию автоматически.  <br/> |Сначала приобретите новые лицензии, чтобы они были готовы к назначению вашим пользователям. Удалите лицензию рекламный (ознакомительная версия) от пользователя, а затем **немедленно** назначьте новый **план внутренних звонков** и (или) лицензиям на **внутренние и международные звонки** для пользователя. <br/> При удалении и добавлении лицензий для нескольких пользователей чрезвычайно важно удалить лицензии всех пользователей с помощью Windows PowerShell, а затем **немедленно** назначить лицензии для всех пользователей также с помощью Windows PowerShell. Это гарантирует, что при обработке больших объемов назначений лицензий пользователей не происходит нарушение обслуживания. Пример сценариев PowerShell приведен в разделе [Назначение лицензий Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Примечание.** Если вы используете локальную сеть PSTN для гибридных пользователей *, вам нужно* назначить лицензию на **телефонную систему** . Вы также **не** должны назначать план голосовых вызовов. Тем не менее, если вы включаете планы звонков в Microsoft 365 или Office 365 для пользователей, которые находятся в Microsoft 365 или Office 365, необходимо по-прежнему назначать **план внутренних звонков** или лицензию на **внутренние и международные звонки** для этих пользователей. Смотрите раздел [Назначение лицензий Skype для бизнеса и Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Если вам нужно получить больше номеров телефонов, [обратитесь в службу поддержки для бизнес-продуктов — Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
