---
title: Назначение или изменение расположения для экстренного реагирования для пользователя
author: lanachin
ms.author: v-lanac
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
description: В этой статье рассказывается о том, как назначить или изменить расположение для экстренного реагирования для пользователей в Организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 096e2dead1ede4f9769dafd85dfac23d6c44f399
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232480"
---
# <a name="assign-or-change-an-emergency-location-for-a-user"></a>Назначение или изменение расположения для экстренного реагирования для пользователя

Когда вы настраиваете планы звонков, вам нужно назначить место для экстренного номера каждому абоненту или пользователю. В европейских странах расположение для экстренного реагирования связано с номером телефона, когда вы получаете его из Office 365 или переносите номер телефона в Office 365. В США расположение для экстренного реагирования связано с номером телефона, когда он назначен пользователю. Адрес для экстренного реагирования можно изменить, если пользователь, которому он назначен, переместится в новое место. Дополнительные сведения об адресах и местоположениях для экстренных случаев смотрите в разделе [Управление вызовом экстренной](what-are-emergency-locations-addresses-and-call-routing.md)помощи.
  
Сведения о том, как получить план звонков и затраты на него, можно найти [в разделе Лицензирование надстроек для Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

Вы можете назначить или изменить расположение для экстренного реагирования для пользователя в центре администрирования Microsoft Teams или с помощью PowerShell.

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

1. В левой области навигации центра администрирования Microsoft Teams щелкните номера **голосовых**  >  **телефонов**.

2. На странице **номера телефонов** выберите в списке номер пользователя, а затем нажмите кнопку **изменить**.

3. На панели **редактирования** в разделе **расположение для экстренного**реагирования выполните одно из указанных ниже действий.

   - Чтобы назначить место для экстренного реагирования, выполните поиск и выберите место для экстренного реагирования.

   - Чтобы изменить расположение для экстренного реагирования, уже назначенное пользователю, нажмите **X** , чтобы удалить существующее расположение, а затем найдите и выберите расположение, которое вы хотите назначить.

4. Нажмите кнопку **Сохранить**.

## <a name="using-powershell"></a>Использование PowerShell

Смотрите раздел [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser). 

    
## <a name="related-topics"></a>Статьи по теме

- [Управление вызовом экстренной помощи](what-are-emergency-locations-addresses-and-call-routing.md)
- [Добавление, изменение и удаление расположения для экстренного реагирования для организации](add-change-remove-emergency-location-organization.md)
- [Добавление, изменение и удаление места для расположения для экстренного реагирования для организации](add-change-remove-emergency-place-organization.md)
- [Назначение или изменение места для расположения для экстренного реагирования для пользователя](assign-change-emergency-place-user.md)
- [Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)
- [Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
