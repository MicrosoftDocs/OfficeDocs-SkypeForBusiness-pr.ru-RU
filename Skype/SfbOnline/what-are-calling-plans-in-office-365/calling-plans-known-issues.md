---
title: "Вызов планы известные проблемы"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: "Узнайте, известные проблемы с телефонной для Office 365 (вызов ТСОП) и что можно сделать о них. "
ms.openlocfilehash: cb572c9de92cd53384c07c4e48779598ca73bb8c
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="calling-plans-known-issues"></a>Вызов планы известные проблемы

Тарифные планы в Office 365 являются новой возможностью в Скайп для бизнеса в Интернет. Ниже представлены проблемы, которые они отслеживаемые и активно изучению. Они потенциально разрешается при обновлении компонента в будущем построения в Office 365 и Скайп для бизнеса в Интернет.
  
## <a name="calling-plans-known-issues"></a>Вызов планы известные проблемы

|**Известные проблемы**|**Комментарии**|
|:-----|:-----|
|Переход от Технический обзор лицензий для производственной лицензии для вызова планы не обновлять автоматически лицензии.  <br/> |Сначала приобрести новых лицензий так, чтобы они готов к назначению для пользователей. Удаление лицензии акции (Tech Preview) от пользователя, а затем **сразу ЖЕ** назначить новых лицензий **Планирование внутреннего вызова** и/или **Внутренний и планирование International вызов** для пользователя. <br/> Если удаление и добавление лицензий для нескольких пользователей, чрезвычайно важным фактором, что удалить лицензии у всех пользователей с помощью Windows PowerShell и **сразу ЖЕ** назначение лицензий для всех пользователей, также с помощью Windows PowerShell. При этом будет убедитесь, что без нарушения в обслуживании при обработке больших объемов назначение лицензии пользователя. Примеры скриптов PowerShell в разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Примечание:** При использовании локального подключения к ТСОП для пользователей гибридной вы *только* необходимо назначить лицензии **Телефонной системой** . **Не** должен также назначить голосовой связи, вызов планирование. При включении вызов планы в Office 365 для пользователей, которые находятся в Office 365, необходимо по-прежнему назначение **Планирование внутренних звонков** или **Внутренний и вызов планирование International** лицензии для этих пользователей. В разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Если вам потребуется получить дополнительные номера телефонов, чем это, пожалуйста, [обратитесь в службу поддержки продуктов бизнес - Admin справки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](transferring-phone-numbers-common-questions.md)

[Типы номеров телефонов, используемые в планах звонков](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Управление номерами телефонов организации](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Условия и положения, распространяющиеся на экстренные вызовы](emergency-calling-terms-and-conditions.md)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://go.microsoft.com/fwlink/?LinkID=692099)
