---
title: Назначение и изменение мест для экстренного размещения для пользователей
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
description: В этой статье вы узнаете, как назначить или изменить место для экстренного размещения пользователей в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9bd69356be22954ee1b1b44b2dcc1a52c1e72507
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634888"
---
# <a name="assign-or-change-the-place-for-an-emergency-location-for-a-user"></a>Назначение или изменение местоположения для экстренного экстренного ситуация для пользователя

Независимо от [](pstn-connectivity.md) того, какой способ подключения к ОКП выбран, каждому номеру телефона или пользователю необходимо на назначенную службу "Планы звонков Майкрософт", "Подключение" или "Прямая маршрутизовка местоположения для экстренного &mdash; &mdash; вызова".

Однако в зависимости от варианта подключения к ПСС способ управления местоположениями экстренных служб и их назначение для пользователя может различаться. Дополнительные сведения см. в [управлении экстренных вызовов.](what-are-emergency-locations-addresses-and-call-routing.md)

В этой статье описано,  как назначить или изменить расположение для экстренного ситуация для пользователя в центре администрирования Microsoft Teams или с помощью PowerShell.

Эта статья относится к планам звонков и операторам Подключение.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **Номера голосовой**  >  **Телефон голосовой Телефон**.

2. На странице **Телефон чисел** щелкните **вкладку** Числа, выберите номер пользователя в списке и нажмите кнопку **Изменить**.

3. В области **Правка** в области **Местоположение для экстренного ситуация** сделайте следующее:

    - Чтобы назначить место, найщите его и выберите место в результатах поиска.

    - Чтобы изменить место, которое уже назначено пользователю, щелкните **X,** чтобы удалить существующее расположение и место, найдите его и выберите нужное место.

4. В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о телефонном номере, отключите или включите отправку электронной почты пользователю со сведениями о **телефонном номере**. По умолчанию этот режим в том же режиме.

5. Нажмите кнопку **Применить**.

## <a name="using-powershell"></a>С помощью PowerShell

См. [set-CsOnlineLisLocation](/powershell/module/skype/set-csonlinelislocation).
    
## <a name="related-topics"></a>Статьи по теме

- [Управление звонками экстренных служб](what-are-emergency-locations-addresses-and-call-routing.md)
- [Назначение или изменение расположения для экстренного реагирования для пользователя](assign-change-emergency-location-user.md)
- [Добавление, изменение и удаление расположения для экстренного реагирования для организации](add-change-remove-emergency-location-organization.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)