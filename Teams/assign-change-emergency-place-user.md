---
title: Назначение или изменение мест для экстренного реагирования для пользователей
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Из этой статьи вы узнаете, как назначить или изменить расположение для экстренного реагирования для пользователей в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60bd471e42eb6e8c2404eef47636da2c9894268c
ms.sourcegitcommit: 179713dd2b22736c0d63060a6351eb69ec4abff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2022
ms.locfileid: "68551643"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Назначение или изменение расположения для экстренного реагирования для пользователя

Независимо от варианта подключения [по ТСОП](pstn-connectivity.md)&mdash;, необходимо назначить каждому номеру телефона или пользователю тарифный план Microsoft Calling Plans, Operator Connect, Teams Phone Mobile&mdash;или прямую маршрутизацию местоположения для экстренного реагирования.

Однако в зависимости от варианта подключения к ТСОП способ управления и назначения местоположения для экстренного реагирования для пользователя может отличаться. Дополнительные сведения см. в разделе ["Управление экстренными звонками"](what-are-emergency-locations-addresses-and-call-routing.md).

В этой статье описывается, как назначить или  изменить расположение для экстренного реагирования для пользователя в Центре администрирования Microsoft Teams или с помощью PowerShell.

Эта статья относится к тарифным планам, Operator Connect и Teams Phone Mobile.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните номера **голосовых** > **телефонов**.

2. На странице **"Номера телефонов** " откройте вкладку **"** Номера", выберите номер пользователя в списке и нажмите кнопку "Изменить **"**.

3. На панели **"** Правка" в **разделе "Местоположение для экстренного реагирования**" выполните одно из следующих действий:

    - Чтобы назначить место, найдите расположение или место, а затем выберите место в результатах поиска.

    - Чтобы изменить место, которое уже назначено пользователю, щелкните **X** , чтобы удалить существующее расположение и место, найдите и выберите нужное место.

4. В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о номере телефона, отключите или включите Email с информацией о **телефонных номерах**. По умолчанию этот параметр включен.

5. Нажмите кнопку **Применить**.

## <a name="using-powershell"></a>С помощью PowerShell

См [. раздел Set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>См. также

- [Управление экстренными звонками](what-are-emergency-locations-addresses-and-call-routing.md)
- [Назначение или изменение расположения для экстренного реагирования для пользователя](assign-change-emergency-location-user.md)
- [Добавление, изменение и удаление расположения для экстренного реагирования для организации](add-change-remove-emergency-location-organization.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов для организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)