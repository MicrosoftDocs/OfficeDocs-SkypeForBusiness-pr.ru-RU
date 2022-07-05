---
title: Управление учетными записями ресурсов в Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: В этой статье вы узнаете, как создавать, изменять учетные записи ресурсов и управлять ими в Microsoft Teams.
ms.openlocfilehash: 0b8c77f7d6371ba1bfefa9837488415405e48f67
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615805"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Управление учетными записями ресурсов в Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Дальнейшие действия

После завершения настройки учетной записи ресурса и назначения номера службы при необходимости вы можете использовать учетную запись ресурса с автосекретарем или очередью вызовов.

Дополнительные сведения см. в следующих ссылках:

- [Облачный автосекретарь](create-a-phone-system-auto-attendant.md)
- [Очередь облачных вызовов](create-a-phone-system-call-queue.md)

Отображаемое имя учетной записи ресурса и тип учетной записи **ресурса** можно изменить с помощью **параметра "Изменить**". По **завершении** нажмите кнопку "Сохранить".

## <a name="change-an-existing-resource-account-to-use-a-teams-phone-resource-account-license"></a>Изменение существующей учетной записи ресурса для использования лицензии на учетную запись ресурса телефона Teams

Если вы решили переключить лицензии на существующую учетную запись ресурса с лицензии **Телефонная система стандартная Teams** на лицензию учетной записи ресурса **Телефонная система Microsoft Teams**, вам потребуется получить бесплатную лицензию на учетную запись ресурса **телефона Teams**, а затем выполнить действия, описанные в разделе Центр администрирования Microsoft 365 [переместить пользователей в другую подписку](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Всегда удаляйте полную лицензию Телефонная система стандартная Teams и назначайте лицензию Телефонная система Microsoft Teams **resource Account** в одной лицензии. Если удалить старую лицензию, сохранить изменения учетной записи, добавить новую лицензию, а затем снова сохранить параметры учетной записи, учетная запись ресурса может работать не так, как ожидалось. В этом случае рекомендуется создать учетную запись ресурса для лицензии Телефонная система Microsoft Teams ресурса  и удалить неработающую учетную запись ресурса.

## <a name="skype-for-business-server-2019"></a>Skype для бизнеса Server 2019

Сведения об учетных записях ресурсов, которые размещены в Skype для бизнеса Server 2019, которые можно использовать с облачными очередями звонков и облачными автосекретарями, см. в разделе ["](/SkypeforBusiness/hybrid/plan-call-queue)Планирование очередей вызовов в облаке" или "Планирование облачных автосекретарей[".](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant) Гибридные реализации (числа, размещенные в прямой маршрутизации) настраиваются с помощью командлета [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) на локальном сервере Skype для бизнеса Server 2019.

Идентификаторы приложений, которые необходимо использовать при создании экземпляров приложения:

- **Автосекретарь:** ce933385-9390-45d1-9512-c8d228074e07
- **Очередь вызовов:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Если вы хотите, чтобы пользователи Skype для бизнеса Server 2019 могли искать очередь звонков или автосекретаря, необходимо создать учетные записи ресурсов в Skype для бизнеса Server 2019, так как учетные записи сетевых ресурсов не синхронизируются с Active Directory. Когда записи DNS SRV для sipfederationtls разрешаются в Skype для бизнеса Server 2019, учетные записи ресурсов должны быть  созданы в Skype для бизнеса Server 2019 с помощью оболочки управления SfB и синхронизированы с Azure AD.

Для реализаций, гибридных с Skype для бизнеса Server:

   [Планирование автосекретарей в облаке](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [Планирование очередей звонков в облаке](/SkypeforBusiness/hybrid/plan-call-queue)

   [Настройка локальных учетных записей ресурсов](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>Удаление учетной записи ресурса

Перед удалением убедитесь, что вы отключите номер телефона от учетной записи ресурса, чтобы избежать зависания номера службы в режиме ожидания.

После этого можно удалить учетную запись ресурса в Центр администрирования Microsoft 365 на вкладке "Пользователи".

Чтобы отменить связь номера телефона прямой маршрутизации с учетной записью ресурса, используйте следующий командлет:

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
