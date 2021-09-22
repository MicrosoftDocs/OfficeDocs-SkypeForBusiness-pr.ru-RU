---
title: 'Руководство по безопасному использованию Microsoft Teams: как безопасно использовать Teams на общих компьютерах'
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Руководство по безопасному использованию Microsoft Teams на общем компьютере рабочего места.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 689899ed6e2aaf576a3d743c7a48ca36a647691c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623221"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a>Безопасное использование Microsoft Teams на общих компьютерах

По возможности предприятиям *рекомендуется* использовать подход "Никому не доверяй" для клиентских устройств посредством возможностей управления устройством, проверок работоспособности и внедрения политик устройства, шифрования на уровне устройства и других функций безопасности.

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Изображение подхода Никому не доверяй c демонстрацией явной проверки, предоставления минимальных разрешений и предположения бреши в системе безопасности (основных принципов подхода Никому не доверяй) в синих кругах.":::

Администраторы могут создавать безопасные условия, *настаивая* на проверке, предоставляя минимальные разрешения и предполагая компрометацию, — стандарты, обеспечивающие действия, снижающие риски для пользователей и данных.

> [!TIP]
> Более подробный анализ принципов "Никому не доверяй" см. в [этих видео](/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a>Советы по безопасному использованию Microsoft Teams на общем компьютере

Признавая невозможность или нецелесообразность для каждого сценария, тем не менее администраторам важно соблюдать руководство по использованию Teams на общем компьютере или неуправляемом устройстве, прилагая для этого все усилия.

Планы по возможности сразу должны разрабатываться в соответствии с руководством.

1. Используйте функции безопасности платформы операционной системы.
    1. Настройте операционную систему на установку автоматических обновлений, получаемых от поставщика операционной системы (для систем Майкрософт это можно сделать с помощью [**Центра обновления Windows**](https://support.microsoft.com/help/12373/windows-update-faq)). 
    1. Включите все функции шифрования устройства, такие как [**BitLocker**](/windows/security/information-protection/bitlocker/bitlocker-overview), и используйте безопасный ключ для доступа к устройству. Обратите внимание, что [**BitLocker поддерживается в большинстве современных устройств с Windows 10**](/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10). 
    1. Используйте функции антивирусной защиты, например предоставляемые [**Защитником Windows**](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), на своих устройствах.
    1. Настоятельно рекомендуется использовать [отдельные учетные записи пользователей](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) для каждого пользователя в системе.
    1. *Не* предоставляйте и не используйте права администратора права для неадминистративных функций (например, для просмотра веб-страниц, запуска Teams и т. д.).

Если невозможно выполнить инструкции, указанные выше, советуем использовать прочие рекомендации по защите браузера:

1. Примените возможности защиты браузера.
    1. Используйте приватные сеансы просмотров, чтобы свести к минимуму данные и журнал, сохраняемые на диске. Например, используйте [просмотр InPrivate в Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [просмотр в режиме инкогнито в Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en) или возможности вашего конкретного браузера для просмотра веб-страниц в приватном режиме. 
    1. Рекомендуется изменить поведение системы на включение приватного режима просмотра *по умолчанию*. 

2. Открывайте и используйте [веб-приложение Teams](https://teams.microsoft.com) (иногда называемое *веб-* клиентом), а не скачиваемый клиент Teams.

3. После завершения использования общей системы вы должны выполнить следующие действия: 
    1. [Выйдите из Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).
    1. Закройте все вкладки и окна браузера.
    1. Выйдите из устройства.

Перечисленные выше элементы не являются исчерпывающим списком рекомендаций или элементов безопасности, охватывающих все случаи. Могут существовать дополнительные действия, применяемые в вашей среде (например, администраторы безопасности могут использовать безопасные ссылки и безопасные вложения для Teams, если вы применяете [Office 365 ATP план 1 или 2](/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)). Однако эти действия являются отправной точкой для создания руководства по использованию Teams на общих устройствах.

## <a name="more-information"></a>Дополнительные сведения

[BitLocker в диспетчере конфигураций](/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[BitLocker для Windows 10 в Intune](/mem/intune/protect/encrypt-devices)

[Безопасность конечной точки в Intune](/mem/intune/protect/endpoint-security)

[Включение](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) антивирусной программы в Microsoft Defender в параметрах безопасности Windows и [выполнение сканирований](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)

[Статья о центре безопасности Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[Веб-клиент Teams/веб-приложение Teams](./get-clients.md#web-client)

[Безопасность и Microsoft Teams](./teams-security-guide.md)
