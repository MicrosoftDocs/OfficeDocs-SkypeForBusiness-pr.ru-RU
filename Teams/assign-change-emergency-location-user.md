---
title: Назначение или изменение расположения для экстренного реагирования для пользователя
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
f1.keywords:
- NOCSH
description: В этой статье вы узнаете, как назначить или изменить местоположение для экстренного помощи пользователям в организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8352c702d2c6d32b6384599499aa326def49fa4e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809569"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Назначение или изменение расположения для экстренного реагирования для пользователя

При настройке планов звонков необходимо назначить расположение для экстренного вызова каждому номеру или пользователю. В европейских странах местоположение для экстренного звонков связано с номером при его передаче из Microsoft 365 или Office 365 либо при переносе номера в Microsoft 365 или Office 365. В США местоположение для экстренного помощи связано с номером телефона, который назначен пользователю. Адрес для экстренного помощи можно изменить, если пользователь, который ему назначен, перемещается в новое расположение. Дополнительные информацию о местоположениях и адресах для экстренного вызова см. в подмносях "Что такое местоположения для экстренного помощи, места и маршруты [экстренных вызовов?".](/microsoftteams/what-are-emergency-locations-addresses-and-call-routing)
  
Чтобы узнать, как получить планы звонков и сколько они стоят, см. лицензирование [надстройки Teams.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
В Центре администрирования Microsoft Teams или с помощью PowerShell можно назначить или изменить местоположение для экстренного решения.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации Центра администрирования Microsoft Teams щелкните **"Номера**  >  **голосовых телефонов".**

2. На странице **"Номера телефонов"** перейдите **на** вкладку "Номера", выберите в списке номер пользователя и нажмите кнопку **"Изменить".**

3. В области **"Правка"** в **области "Местоположение для экстренного помощи"** сделайте одно из следующего:

   - Чтобы назначить местоположение для экстренного режима, наберите его и выберите его.

   - Чтобы изменить уже назначенное пользователю расположение для экстренного помощи, щелкните **X,** чтобы удалить существующее расположение, а затем найдите и выберите нужное расположение.

4. В зависимости от того, хотите ли вы отправить пользователю сообщение электронной почты со сведениями о телефонном номере, отключите или включите для пользователя электронной почты сведения о **телефонном номере.** По умолчанию этот режим имеет значение "В этом режиме".

5. Нажмите кнопку **Применить**.

## <a name="using-powershell"></a>С помощью PowerShell

См. [set-CsOnlineVoiceUser.](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser) 

    
## <a name="related-topics"></a>Статьи по теме

- [Управление экстренным вызовом](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление расположения для экстренного реагирования для организации](add-change-remove-emergency-location-organization.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Назначение или изменение места для расположения для экстренного реагирования для пользователя](assign-change-emergency-place-user.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
