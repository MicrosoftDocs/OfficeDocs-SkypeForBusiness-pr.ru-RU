---
title: Управление учетными записями ресурсов в Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Из этой статьи вы узнаете, как создавать, изменять учетные записи ресурсов и управлять ими в Microsoft Teams.
ms.openlocfilehash: b9c7f5575d5e6df4370c07bf1cd581cbd1a396dd
ms.sourcegitcommit: 9504b7a67e593f5575060b09b69817325e2a1f77
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2022
ms.locfileid: "69111136"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Управление учетными записями ресурсов в Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Дальнейшие действия

После завершения настройки учетной записи ресурса и назначения номера службы при необходимости вы можете использовать учетную запись ресурса с автосекретарем или очередью вызовов.

Дополнительные сведения см. в следующих справочниках:

- [Облачный автосекретарь](create-a-phone-system-auto-attendant.md)
- [Очередь облачных вызовов](create-a-phone-system-call-queue.md)

Вы можете изменить **отображаемое имя** учетной записи ресурса и тип **учетной записи ресурса** с помощью параметра **Изменить** . По завершении нажмите кнопку **Сохранить** .

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Изменение существующей учетной записи ресурса для использования лицензии на учетную запись ресурса телефона Teams
Чтобы переключить лицензии в существующей учетной записи ресурса с **Телефонная система стандартная Teams** лицензии на **учетную запись Телефонная система Microsoft Teams ресурсов**, необходимо приобрести лицензию на **учетную запись ресурса телефона Teams**, а затем выполните действия, описанные в разделе Центр администрирования Microsoft 365 [переместить пользователей в другую подписку](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Всегда удаляйте полную лицензию Телефонная система стандартная Teams и назначьте **лицензию Телефонная система Microsoft Teams учетной записи ресурсов** в том же действии лицензии. Если удалить старую лицензию, сохранить изменения учетной записи, добавить новую лицензию, а затем снова сохранить параметры учетной записи, учетная запись ресурса может работать не так, как ожидалось. В этом случае рекомендуется создать новую учетную запись ресурса для **лицензии учетной записи Телефонная система Microsoft Teams ресурсов** и удалить неисправную учетную запись ресурса.

## <a name="skype-for-business-server-2019"></a>Skype для бизнеса Server 2019

Учетные записи ресурсов, размещенные в Skype для бизнеса Server 2019, которые можно использовать с облачными очередями вызовов и облачными автосекретарями, см. в статье [Планирование очередей вызовов в облаке](/SkypeforBusiness/hybrid/plan-call-queue) или [Планирование облачных автосекретарей](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Гибридные реализации (числа, размещенные в прямой маршрутизации) настраиваются с помощью командлета [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) на локальном сервере Skype для бизнеса Server 2019.

Идентификаторы приложений, которые необходимо использовать при создании экземпляров приложения:

- **Автосекретарь:** ce933385-9390-45d1-9512-c8d228074e07
- **Очередь вызовов:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Если вы хотите, чтобы в очереди вызовов или автосекретаре можно было искать пользователей Skype Для бизнеса Server 2019, следует создать учетные записи ресурсов в Skype для бизнеса Server 2019, так как учетные записи сетевых ресурсов не синхронизируются с Active Directory. Если записи SRV DNS для sipfederationtls разрешаются в Skype для бизнеса Server 2019, учетные записи ресурсов **должны** быть созданы в Skype для бизнеса Server 2019 с помощью оболочки управления SfB и синхронизированы с Azure AD.

Для гибридных реализаций с Skype для бизнеса Server:

   [Планирование автосекретарей в облаке](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Планирование очередей звонков в облаке](/SkypeforBusiness/hybrid/plan-call-queue)

   [Настройка локальных учетных записей ресурсов](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Удаление учетной записи ресурса

Убедитесь, что номер телефона не связывается с учетной записью ресурса перед его удалением, чтобы избежать зависание номера службы в режиме ожидания.

После этого вы можете удалить учетную запись ресурса в Центр администрирования Microsoft 365 на вкладке Пользователи.

Чтобы отсоединить телефонный номер прямой маршрутизации от учетной записи ресурса, используйте следующий командлет:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
