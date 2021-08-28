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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Узнайте, как переместить пользователей в Skype для бизнеса Online.
ms.openlocfilehash: a865b5ece2802f11bbbd103b10e52ff82f1ef804
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58614983"
---
# <a name="move-users-from-on-premises-to-skype-for-business-online"></a>Перемещение пользователей из локальной среды в Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

После перемещения пользователя из локального в Skype для бизнеса Online пользователь взаимодействует с Skype для бизнеса Online за его функции. Все контакты, которые существовали на месте, будут доступны в Skype для бизнеса Online, а все существующие собрания, организованные пользователем в будущем, обновляются таким образом, чтобы ссылки указывают на Skype для бизнеса Online. Если пользователь включен для аудиоконференций, на собраниях также будут включены координаты входа.  Чтобы переместить пользователей из локальной среды в Skype для бизнеса Online, используйте Move-CsUser или панель управления Skype для бизнеса Server, которые являются локальной программой. 

Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако.

> [!NOTE]
> В рамках подготовки к предстоящему выходу на пенсию Skype для бизнеса Online корпорация Майкрософт упростила переход организаций на Teams. При перемещении пользователей из локального в облако пользователям автоматически назначен режим TeamsOnly, а их собрания из локального помещения автоматически преобразуются в Teams собрания, как если бы коммутатор был задан, независимо от того, был ли на самом деле указан `-MoveToTeams` переключатель.  До выхода на пенсию Skype для бизнеса Online организации, которые требуют перемещения пользователей из локального в Skype для бизнеса Online, могут достичь этого за два шага, обновив режим пользователя после перехода пользователя в *TeamsOnly.* Однако в ближайшее время невозможно будет назначить режим, кроме TeamsOnly, пользователям, уехав в облако.  
 
## <a name="move-users-with-move-csuser"></a>Перемещение пользователей с помощью Move-CsUser 

Move-CsUser доступно в локальном окне Skype для бизнеса PowerShell. Вы должны иметь достаточные привилегии как в локальной среде, так и в Microsoft 365 организации, как описано в необходимых административных [учетных данных.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для бизнеса Server Management Shell с учетными данными локального доступа и использовать параметр для указания учетных данных для учетной записи Microsoft 365 с необходимой административной `-Credential` ролью.

Перемещение пользователя в интернет с помощью Move-CsUser:

- Укажите, что пользователь перемещается с помощью параметра Identity.
- Укажите параметр -Target со значением sipfed.online.lync. <span> com".
- Если у вас нет одной учетной записи с достаточными разрешениями как на локальном, так и на Microsoft 365, используйте параметр -credential для обеспечения учетной записи достаточными разрешениями в Microsoft 365.
- Если учетная запись с разрешениями в Microsoft 365 не заканчивается в ".onmicrosoft. <span> com", затем необходимо указать параметр -HostedMigrationOverrideUrl с правильным значением, как описано в необходимых административных [учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Следующая последовательность cmdlet может быть использована для перемещения пользователя Skype для бизнеса Online и назначает режим по умолчанию клиента пользователю. Предполагается, что Microsoft 365 учетная запись является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.

```PowerShell
# From an on-premises Skype for Business Server or Lync Server 2013 management shell window, run:
 
$cred=Get-Credential
$url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $cred -HostedMigrationOverrideUrl $url
 
# And then from a Teams PowerShell window, remove TeamsOnly mode by running: 
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName $null
```

Если учетная запись администратора включена в MFA (многофакторная проверка подлинности), не укажите параметр -Credential. Администратору будет предложено использовать учетные данные.

## <a name="move-users-with-skype-for-business-server-control-panel-and-teams-admin-center"></a>Перемещение пользователей с Skype для бизнеса Server панели управления и Teams Центра администрирования

1. Откройте приложение Skype для бизнеса Server панели управления.
2. В левой навигации выберите **Пользователи**.
3. Используйте **Поиск,** чтобы найти пользователя(ы) вы хотели бы перейти в Skype для бизнеса Online.
4. Выберите пользователя(ы), а затем  из выпадаемой ниже списка действия выберите Перемещение выбранных пользователей в Skype для бизнеса **Online** или Перемещение выбранных **пользователей в Teams**. Любой из вариантов сначала перемещает пользователя в режим TeamsOnly, но после перемещения можно назначить другой режим. 
5. В мастере нажмите кнопку **Далее**.
6. В случае запроса вопишитесь Microsoft 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.
7. Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.
8. Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.
9. Откройте центр администрирования Teams и выберите "Пользователи" в левой навигации. 
10. Щелкните нужный пользователь в listview. 
11. Нажмите **кнопку Изменить** в разделе, в Teams **обновления.**
12. В правом флауате выберите нужный режим сосуществования и нажмите кнопку **Применить**.
 

## <a name="see-also"></a>См. также

[Move-CsUser](/powershell/module/skype/move-csuser)
