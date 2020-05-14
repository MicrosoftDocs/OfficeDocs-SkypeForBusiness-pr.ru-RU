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
description: Сведения о том, как перемещать пользователей в Skype для бизнеса Online.
ms.openlocfilehash: a9fb80046195580daca6dfc7f810b2e0c1877f1c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221119"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Перемещение пользователей из локальной среды в Skype для бизнеса Online

После того как вы перемещаете пользователя из локальной среды в Skype для бизнеса Online, пользователь взаимодействует с Skype для бизнеса Online для своих функций. Все контакты, которые существовали в локальной среде, будут доступны в Skype для бизнеса Online, а все существующие собрания, упорядоченные для будущего пользователя, будут обновлены, поэтому ссылки указывают на Skype для бизнеса Online. Если пользователю разрешено проведение голосовой конференц-связи, собрания также будут включать координаты для телефонного подключения.  Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте командлет Move-CsUser или панель управления Skype для бизнеса Server, оба из которых являются локальными средствами. 

Прежде чем перемещать пользователей, обязательно изучите [необходимые условия](move-users-between-on-premises-and-cloud.md#prerequisites) для перемещения пользователей в облако.
 
## <a name="move-users-with-move-csuser"></a>Перемещение пользователей с помощью Move — CsUser 

Move-CsUser доступен из локального окна PowerShell для командной консоли Skype для бизнеса. У вас должны быть достаточные права как в локальной среде, так и в организации Microsoft 365/Office 365, как описано в разделе [обязательные административные учетные данные](move-users-between-on-premises-and-cloud.md#required-administrative-credentials). Можно использовать одну учетную запись с правами в обеих средах или можно запустить локальное окно командной консоли Skype для бизнеса Server с локальными учетными данными и использовать `-Credential` параметр для указания учетных данных для учетной записи Microsoft 365 или Office 365 с необходимой административной ролью.

Чтобы переместить пользователя в Интернет с помощью Move-CsUser:

- Укажите пользователя для перемещения с помощью параметра Identity.
- Укажите параметр-target со значением "sipfed. Online. Lync. <span> com ".
- Если у вас нет одной учетной записи с достаточными разрешениями в локальной среде и Office 365, используйте параметр – Credential для предоставления учетной записи с достаточными разрешениями в Office 365.
- Если учетная запись с разрешениями в Office 365 не заканчивается на ". onmicrosoft <span> ". com ", то необходимо указать параметр-Хостедмигратионоверридеурл с правильным значением, как описано в разделе [обязательные административные учетные данные](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Для перемещения пользователя в Skype для бизнеса Online можно использовать следующую последовательность командлетов. Предполагается, что учетные данные Microsoft 365 или Office 365 являются отдельной учетной записью и предоставляются в качестве входных данных для приглашения Get-Credential.

```PowerShell
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
 
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
```

Если учетная запись администратора включает в себя MFA (многофакторная проверка подлинности), не указывайте параметр-Credential. Администратору потребуется ввести учетные данные.

## <a name="move-users-with-skype-for-business-server-control-panel"></a>Перемещение пользователей с помощью панели управления Skype для бизнеса Server 

1. Откройте приложение панели управления Skype для бизнеса Server.
2. В области навигации слева выберите пункт **Пользователи**.
3. Используйте **Find** , чтобы найти пользователей, которых вы хотите переместить в Skype для бизнеса Online.
4. Выберите пользователей, а затем в раскрывающемся списке **действий** над списком выберите **переместить выбранных пользователей в Skype для бизнеса Online**.
5. В мастере нажмите кнопку **Далее**.
6. При появлении соответствующего запроса войдите в Microsoft 365 или Office 365 с помощью учетной записи, которая оканчивается на. onmicrosoft.com и обладает достаточными разрешениями.
7. Нажмите кнопку **Далее**, а **затем еще раз,** чтобы переместить пользователя.
8. Обратите внимание на то, что сообщения о состоянии Success или Failure представлены в верхней части главного приложения панели управления, а не в мастере.

## <a name="see-also"></a>См. также

[Move — CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)
