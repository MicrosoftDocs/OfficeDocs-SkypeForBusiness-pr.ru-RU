---
title: Перемещение пользователей из локальной среды в Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Узнайте, как переместить пользователей в Skype для бизнеса Online.
ms.openlocfilehash: 4d74cdebc5477d0204f69b64c2c05a4435212b3f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110625"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Перемещение пользователей из локальной среды в Skype для бизнеса Online

После перемещения пользователя из локального в Skype для бизнеса Online пользователь взаимодействует со Skype для бизнеса Online для его функциональных возможностей. Все контакты, которые существовали на месте, будут доступны в Skype для бизнеса Online, а все существующие собрания, организованные пользователем в будущем, обновляются таким образом, чтобы ссылки указывают на Skype для бизнеса Online. Если пользователь включен для аудиоконференций, на собраниях также будут включены координаты входа.  Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте либо Move-CsUser, либо панель управления Skype для бизнес-серверов, которые являются средствами локального использования. 

Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.
 
## <a name="move-users-with-move-csuser"></a>Перемещение пользователей с помощью Move-CsUser 

Move-CsUser доступно в локальном окне Skype для управления бизнесом PowerShell. Вы должны иметь достаточные привилегии как в локальной среде, так и в организации Microsoft 365/Office 365, как описано в необходимых административных [учетных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)данных. Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для управления бизнес-серверами с учетными данными локального сервера и использовать параметр для указания учетных данных для учетной записи `-Credential` Microsoft 365 или Office 365 с необходимой административной ролью.

Перемещение пользователя в интернет с помощью Move-CsUser:

- Укажите, что пользователь перемещается с помощью параметра Identity.
- Укажите параметр -Target со значением sipfed.online.lync. <span> com".
- Если в помещении и Office 365 нет одной учетной записи с достаточными разрешениями, используйте параметр -credential для обеспечения учетной записи достаточными разрешениями в Office 365.
- Если учетная запись с разрешениями в Office 365 не заканчивается в ".onmicrosoft. <span> com", затем необходимо указать параметр -HostedMigrationOverrideUrl с правильным значением, как описано в необходимых административных [учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Следующая последовательность смещается для перемещения пользователя в Skype для бизнеса Online. Предполагается, что учетная запись Microsoft 365 или Office 365 является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Если учетная запись администратора включена в MFA (многофакторная проверка подлинности), не укажите параметр -Credential. Администратору будет предложено использовать учетные данные.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Перемещение пользователей с панели управления Skype для бизнес-серверов 

1. Откройте панель управления Skype для бизнес-серверов.
2. В левой навигации выберите **Пользователи**.
3. Используйте **Поиск,** чтобы найти пользователя(ы) вы хотите перейти в Skype для бизнеса Online.
4. Выберите пользователя(ы), а затем, из выпадаемой выше списка действия, выберите Перемещение выбранных пользователей **в Skype для бизнеса Online**. 
5. В мастере нажмите кнопку **Далее**.
6. При запросе вопишитесь в Microsoft 365 или Office 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.
7. Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.
8. Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.

## <a name="see-also"></a>См. также

[Move-CsUser](/powershell/module/skype/move-csuser)