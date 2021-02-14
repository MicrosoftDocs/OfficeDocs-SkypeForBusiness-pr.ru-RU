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
description: Узнайте об известных проблемах с планом звонков по ЗВОНКОВ по ННР и о том, как с ними работать.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220739"
---
# <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

Планы звонков — это новая функция Skype для бизнеса Online. Ниже даны текущие вопросы, которые отслеживаются и активно исследуются. Они могут быть устранены при обновлении функции в будущих сборках.
  
## <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

|**Известная проблема**|**Примечания**|
|:-----|:-----|
|При переходе с лицензий на техническую версию на лицензии для планов звонков лицензия не обновляется автоматически.  <br/> |Сначала приобретите новые лицензии, чтобы они были готовы к назначению пользователям. Удалите промолилиза (техническую версию)  у пользователя, а затем  СРАЗУ назначьте ему новые лицензии на план внутренних и (или) международных и внутренних звонков.  <br/> При удалении и добавлении лицензий для нескольких пользователей крайне важно удалить лицензии у всех пользователей, использующих Windows PowerShell а затем сразу назначить лицензии всем пользователям, также использующим Windows PowerShell.  Это позволит не прерывать работу службы при обработке больших объемов пользовательских лицензий. Примеры сценариев PowerShell см. в примере назначения лицензий Skype для [бизнеса и Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Примечание.** Если вы используете для гибридных пользователей локальное подключение  через ДНР, необходимо только назначить лицензию на **телефонную систему.** Назначать **план голосовых** звонков не следует. Однако если вы включите планы звонков в Microsoft 365 или Office 365 для пользователей Microsoft 365  или Office 365, им все равно потребуется назначить им план внутренних звонков или лицензию на план внутренних и международных звонков.  См. ["Назначение лицензий Skype для бизнеса и Microsoft Teams".](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

> [!NOTE]
> Если вам нужно больше номеров телефонов, обратитесь в службу поддержки продуктов [для бизнеса: справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
