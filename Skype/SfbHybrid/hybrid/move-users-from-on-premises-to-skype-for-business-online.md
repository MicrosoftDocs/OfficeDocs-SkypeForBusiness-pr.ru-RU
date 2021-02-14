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
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221119"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Перемещение пользователей из локальной среды в Skype для бизнеса Online

После перемещения пользователя из локальной сети в Skype для бизнеса Online он взаимодействует со Skype для бизнеса Online для его функциональности. Все контакты, которые существовали локально, будут доступны в Skype для бизнеса Online, а все существующие собрания, организованные пользователем в будущем, будут обновлены таким образом, чтобы ссылки указывают на Skype для бизнеса Online. Если для пользователя включена аудиоконференция, собрания также будут включать координаты телефонного номера.  Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте либо Move-CsUser, либо панель управления Skype для бизнеса Server, которые являются локальной средой. 

Перед перемещением пользователей обязательно просмотрите предварительные условия для перемещения пользователей в облако. [](move-users-between-on-premises-and-cloud.md#prerequisites)
 
## <a name="move-users-with-move-csuser"></a>Перемещение пользователей с Move-CsUser 

Move-CsUser доступна в окне PowerShell локальной оболочки управления Skype для бизнеса. Необходимо иметь достаточные привилегии как в локальной среде, так и в организации Microsoft 365/Office 365, как описано в необходимых учетных данных [администратора.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Можно использовать одну учетную запись с привилегиями в обеих средах или запустить окно локальной оболочки управления Skype для бизнеса Server с учетными данными локальной среды и указать учетные данные для учетной записи `-Credential` Microsoft 365 или Office 365 с необходимой административной ролью.

Чтобы переместить пользователя в Интернет с помощью Move-CsUser:

- Укажите пользователя, который будет перемещаться, с помощью параметра Identity.
- Укажите параметр -Target со значением sipfed.online.lync. <span> com".
- Если у вас нет одной учетной записи с достаточными разрешениями как в локальной службе, так и в Office 365, используйте параметр -credential, чтобы предоставить учетную запись с достаточными разрешениями в Office 365.
- Если учетная запись с разрешениями в Office 365 не заканчивается на ".onmicrosoft". <span> com", затем необходимо указать параметр -HostedMigrationOverrideUrl с правильным значением, как описано в необходимых учетных данных [администратора.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

Для перемещения пользователя в Skype для бизнеса Online можно использовать следующую последовательность. Предполагается, что учетные данные Microsoft 365 или Office 365 — это отдельная учетная запись, которая предоставляется в качестве входных данных для Get-Credential запроса.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Если для учетной записи администратора включена многофакторная проверка подлинности, не указывляй параметр -Credential. Администратору будут предложены учетные данные.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Перемещение пользователей с помощью панели управления Skype для бизнеса Server 

1. Откройте приложение панели управления Skype для бизнеса Server.
2. В области навигации слева выберите **"Пользователи".**
3. Use **Find** to locate the user(s) you would like to move to Skype for Business Online.
4. Выберите пользователей, а затем в  выпадаемом списке "Действие" выберите "Переместить выбранных пользователей **в Skype для бизнеса Online".**
5. В мастере нажмите кнопку **Далее**.
6. При запросе во sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.
7. Нажмите **кнопку**"Далее", а затем еще раз, чтобы переместить пользователя. 
8. Обратите внимание, что сообщения о состоянии, касающиеся успешного или неудачного сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.

## <a name="see-also"></a>См. также

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
