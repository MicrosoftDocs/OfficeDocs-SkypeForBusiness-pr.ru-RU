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
description: Узнайте о известных проблемах с планом звонков по ЗВОНКОВ и о том, как с ними можно работать.
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238025"
---
# <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Планы звонков — это новая функция в Skype для бизнеса Online. Ниже следуют текущие проблемы, которые отслеживаются и активно изучаете. Они могут быть устранены при обновлении этой функции в будущих сборках.
  
## <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

|**Известная проблема**|**Примечания**|
|:-----|:-----|
|При переходе с лицензий На техническую версию на лицензии для планов звонков лицензия не обновляется автоматически.  <br/> |Сначала приобретите новые лицензии, чтобы они были готовы к назначению пользователям. Удалите у пользователя рекламные лицензии (Техническая версия),  а затем НЕМЕДЛЕННО  назначьте ему новые лицензии на план внутренних звонков и(или) план внутренних и международных звонков.  <br/> При удалении и добавлении лицензий для нескольких пользователей очень важно удалить лицензии у всех  пользователей, использующих Windows PowerShell, а затем сразу назначить лицензии всем пользователям, также использующим Windows PowerShell. Это гарантирует отсутствие прерываний в работе службы при обработке больших объемов пользовательских лицензий. Примеры сценариев PowerShell см. в Skype для бизнеса [и Microsoft Teams лицензий.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Примечание.** Если вы используете для гибридных пользователей локальное подключение  к ОКП, необходимо назначить телефонная система **лицензию.** Назначать **план голосовых** звонков не нужно. Однако если вы включите планы звонков в Microsoft 365 или Office 365 для пользователей, которые находятся в Microsoft 365 или  Office 365, вам  потребуется назначить им план внутренних звонков или план внутренних и международных звонков. См. [Skype для бизнеса и Microsoft Teams лицензий.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

> [!NOTE]
> Если вам нужно получить больше номеров телефонов, обратитесь в службу поддержки продуктов [для бизнеса : справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
