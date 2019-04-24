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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Узнайте, известные проблемы с телефонной для Office 365 (вызов ТСОП) и что можно сделать о них. '
ms.openlocfilehash: 01a49749f472b6a3e591295cff7184dc26fd564a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233228"
---
# <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

Тарифные планы в Office 365 являются новой возможностью в Скайп для бизнеса в Интернет. Ниже представлены проблемы, которые они отслеживаемые и активно изучению. Они потенциально разрешается при обновлении компонента в будущем построения в Office 365 и Скайп для бизнеса в Интернет.
  
## <a name="calling-plans-known-issues"></a>Известные проблемы планов звонков

|**Известные проблемы**|**Комментарии**|
|:-----|:-----|
|Переход от Технический обзор лицензий для производственной лицензии для вызова планы не обновлять автоматически лицензии.  <br/> |Сначала приобрести новых лицензий так, чтобы они готов к назначению для пользователей. Удаление лицензии акции (Tech Preview) от пользователя, а затем **сразу ЖЕ** назначить новых лицензий **Планирование внутреннего вызова** и/или **Внутренний и планирование International вызов** для пользователя. <br/> Если удаление и добавление лицензий для нескольких пользователей, чрезвычайно важным фактором, что удалить лицензии у всех пользователей с помощью Windows PowerShell и **сразу ЖЕ** назначение лицензий для всех пользователей, также с помощью Windows PowerShell. При этом будет убедитесь, что без нарушения в обслуживании при обработке больших объемов назначение лицензии пользователя. Примеры скриптов PowerShell в разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Примечание:** При использовании локального подключения к ТСОП для пользователей гибридной вы *только* необходимо назначить лицензии **Телефонной системой** . **Не** должен также назначить голосовой связи, вызов планирование. При включении вызов планы в Office 365 для пользователей, которые находятся в Office 365, необходимо по-прежнему назначение **Планирование внутренних звонков** или **Внутренний и вызов планирование International** лицензии для этих пользователей. В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Если вам потребуется получить дополнительные номера телефонов, чем это, пожалуйста, [обратитесь в службу поддержки продуктов бизнес - Admin справки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 