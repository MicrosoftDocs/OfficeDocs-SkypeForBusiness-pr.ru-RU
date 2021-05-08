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
ms.openlocfilehash: 8c028044fe8c4b808a419503091f9ecf767cfe4d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237965"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Перемещение пользователей из локальной среды в Skype для бизнеса Online

После перемещения пользователя из локального в Skype для бизнеса Online пользователь взаимодействует с Skype для бизнеса Online за его функции. Все контакты, которые существовали на месте, будут доступны в Skype для бизнеса Online, а все существующие собрания, организованные пользователем в будущем, обновляются таким образом, чтобы ссылки указывают на Skype для бизнеса Online. Если пользователь включен для аудиоконференций, на собраниях также будут включены координаты входа.  Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте Move-CsUser или панель управления Skype для бизнеса Server, которые являются локальной программой. 

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.
 
## <a name="move-users-with-move-csuser"></a>Перемещение пользователей с помощью Move-CsUser 

Move-CsUser доступно в локальном окне Skype для бизнеса PowerShell. Вы должны иметь достаточные привилегии как в локальной среде, так и в организации Microsoft 365/Office 365, как описано в необходимых административных [учетных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)данных. Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для бизнеса Server Management Shell с учетными данными локального использования и использовать параметр для указания учетных данных для учетной записи Microsoft 365 или Office 365 учетной записи с необходимой административной `-Credential` ролью.

Перемещение пользователя в интернет с помощью Move-CsUser:

- Укажите, что пользователь перемещается с помощью параметра Identity.
- Укажите параметр -Target со значением sipfed.online.lync. <span> com".
- Если у вас нет одной учетной записи с достаточными разрешениями как на локальной, так и Office 365, используйте параметр -credential для обеспечения учетной записи достаточными разрешениями в Office 365.
- Если учетная запись с разрешениями в Office 365 не заканчивается в ".onmicrosoft. <span> com", затем необходимо указать параметр -HostedMigrationOverrideUrl с правильным значением, как описано в необходимых административных [учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Для перемещения пользователя в Skype для бизнеса Online можно использовать следующую последовательность Skype для бизнеса. Предполагается, что Microsoft 365 или Office 365 учетная запись является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Если учетная запись администратора включена в MFA (многофакторная проверка подлинности), не укажите параметр -Credential. Администратору будет предложено использовать учетные данные.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Перемещение пользователей с Skype для бизнеса Server панели управления 

1. Откройте приложение Skype для бизнеса Server панели управления.
2. В левой навигации выберите **Пользователи**.
3. Используйте **Поиск,** чтобы найти пользователя(ы) вы хотели бы перейти в Skype для бизнеса Online.
4. Выберите пользователя(ы), а затем, из выпадаемой выше списка действия, выберите Перемещение выбранных пользователей в **Skype для бизнеса Online**. 
5. В мастере нажмите кнопку **Далее**.
6. Если вам будет предложено войти, Microsoft 365 или Office 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.
7. Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.
8. Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.

## <a name="see-also"></a>См. также

[Move-CsUser](/powershell/module/skype/move-csuser)