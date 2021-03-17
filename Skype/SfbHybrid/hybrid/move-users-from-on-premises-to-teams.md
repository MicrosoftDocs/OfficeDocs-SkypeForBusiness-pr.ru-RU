---
title: Перемещение пользователей из Skype для бизнеса Server 2019 в Teams
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
description: Сводка. Сведения о переносе параметров пользователей и переносе пользователей в Teams.
ms.openlocfilehash: c84cdbe5f91816ddfabd476540e47f3d1871a427
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836986"
---
# <a name="move-users-from-on-premises-to-teams"></a>Перемещение пользователей из локальной среды в Teams

Когда пользователь перемещается из локального помещения в Teams Only, домашний skype для бизнеса пользователя перемещается из локального в online, а пользователю назначена TeamsUpgradePolicy с mode=TeamsOnly.  После того как пользователь перемещается из локального в режим TeamsOnly:

- Все входящие вызовы и чаты от других пользователей (будь то отправлены из Skype для бизнеса или teams) будут отправлены в клиент teams пользователя.
- Пользователь сможет работать с другими пользователями, которые используют Skype для бизнеса (будь то в Интернете или на локальной основе).
- Пользователь сможет общаться с пользователями в федерадных организациях.
- Новые собрания, запланированные этим пользователем, это собрания Teams.
- Пользователь по-прежнему может присоединяться к любым собраниям Skype для бизнеса.
- Запланированные ранее собрания пользователя будут перенесены из локального в Teams.
- Контакты, которые существовали на месте, доступны в Teams вскоре после того, как пользователь впервые вошел в систему.
- Пользователи не могут инициировать звонки или чаты из Skype для бизнеса и не могут планировать новые собрания в Skype для бизнеса. Если они попытаются открыть клиент Skype для бизнеса, они будут перенаправлены для использования Teams, как показано ниже. Если клиент Teams не установлен, он будет направлен в веб-версию Teams с помощью браузера.<br><br>
    ![Сообщение, перенаправление пользователя в Teams](../media/go-to-teams-page.png)

Перед перемещением пользователей обязательно просмотрите [необходимые](move-users-between-on-premises-and-cloud.md#prerequisites) условия для перемещения пользователей в облако. Кроме того, не забудьте просмотреть руководство по миграции и совместной работе для организаций, использующих [Teams вместе со Skype для бизнеса.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> Унифицированный магазин контактов должен быть отключен на учетной записи SfB на предварительной основе для перемещений контакта в Teams.


Существует два метода перемещения пользователя из локального помещения в Teams:

- Если вы используете версию раньше, чем Skype для бизнеса Server 2015 CU8, для перемещения требуется два шага (которые можно сценарий, которые можно сделать вместе как один шаг, если требуется):
  - [Перемещение пользователя из Skype для бизнеса Server (на месте) в Skype для бизнеса Online](move-users-from-on-premises-to-skype-for-business-online.md).
  - После того как пользователь находится в Skype для бизнеса Online, назначьте пользователю TeamsUpgradePolicy режим= TeamsOnly. Чтобы предоставить режим TeamsOnly, запустите следующий командлет из окна Skype для бизнеса Online PowerShell: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Если у вас есть средства администрирования из Skype для бизнеса Server 2015 CU8 или более поздней, вы можете использовать метод выше, или вы можете сделать этот шаг в один шаг, как описано ниже. Кроме того, вы можете дополнительно предоставить уведомление в клиенте Skype для бизнеса перед их перемещением в Teams Only, а также необязательно, чтобы клиент Teams был безмолвно загружен клиентом Skype для бизнеса.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Перемещение пользователя напрямую из Skype для бизнеса на локальном сайте в Teams Only

Средства локального администрирования в Skype для бизнеса Server 2015 с cu8, а также в Skype для бизнеса Server 2019 позволяют перемещать пользователей из локального режима в режим Teams Only в одном шаге с помощью командлета Move-CsUser в PowerShell или панели управления Skype для бизнес-серверов, как описано ниже.

### <a name="move-to-teams-using-move-csuser"></a>Перемещение в Teams с Move-CsUser

Move-CsUser доступно в локальном окне Skype для управления бизнесом PowerShell. Действия ниже и необходимые разрешения такие же, как перемещение пользователя в Skype для бизнеса Online, за исключением того, что вы также должны указать переключатель MoveToTeams, и вы должны убедиться, что пользователю также была предоставлена лицензия для Teams (в дополнение к Skype для бизнеса Online).

Вы должны иметь достаточные привилегии как в локальной среде, так и в облачной службе (Microsoft 365 или Office 365), как описано в необходимых административных [учетных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)данных. Можно использовать одну учетную запись, которая имеет привилегии в обеих средах, или можно запустить локальное окно Skype для управления бизнес-серверами с учетными данными локального сервера и использовать параметр для указания учетных данных для учетной записи `-Credential` Microsoft 365 или Office 365 с необходимой административной ролью.

Перемещение пользователя в режим Teams Only с помощью Move-CsUser:

- Укажите пользователя для перемещения с помощью `Identity` параметра.
- Укажите параметр -Target со значением sipfed.online.lync. <span> com".
- Укажите `MoveToTeams` переключатель.
- Если у вас нет одной учетной записи с достаточными разрешениями как в локальной, так и в облачной службе (Microsoft 365 или Office 365), используйте этот параметр для поставки учетной записи с достаточными разрешениями в `-credential` Office 365.
- Если учетная запись с разрешениями в Microsoft 365 или Office 365 не заканчивается в "onmicrosoft. <span> com", необходимо указать параметр с правильным значением, как описано в `-HostedMigrationOverrideUrl` [необходимых административных учетных данных](move-users-between-on-premises-and-cloud.md#required-administrative-credentials).

Следующая последовательность командлетов может использоваться для перемещения пользователя в TeamsOnly и предполагает, что учетная запись Microsoft 365 или Office 365 является отдельной учетной записью и предоставляется в качестве ввода для Get-Credential запроса.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

> [!TIP]
> Поскольку существуют различные условия, требующие различных параметров, по умолчанию в большинстве случаев существует команда:

```powershell
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -UseOAuth -HostedMigrationOverrideUrl $url
```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Перемещение в Teams с помощью панели управления Skype для бизнес-серверов

1. Откройте панель управления Skype для бизнес-серверов.
2. В левой навигации выберите **Пользователи**.
3. Используйте **Поиск,** чтобы найти пользователя(ы), который вы хотите перейти в Teams.
4. Выберите пользователя(ы), а затем, из выпадаемой выше списка действия, выберите Перемещение выбранных **пользователей в Teams.** 
5. В мастере нажмите кнопку **Далее**.
6. При запросе вопишитесь в Microsoft 365 или Office 365 с учетной записью, которая заканчивается в .onmicrosoft.com и имеет достаточно разрешений.
7. Нажмите **кнопку Далее,** а **затем** еще раз, чтобы переместить пользователя.
8. Обратите внимание, что сообщения о состоянии, касающиеся успеха или сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Уведомление пользователей Skype для бизнеса о предстоящем переходе в Teams

Собственные средства администрирования в Skype для бизнеса Server 2015 с cu8, а также в Skype для бизнеса Server 2019 позволяют уведомлять пользователей Skype для бизнеса о предстоящем переходе в Teams. Когда вы включаете эти уведомления, пользователи увидят уведомление в клиенте Skype для бизнеса (Win32, Mac, web и mobile), как показано ниже. Если пользователи нажимают кнопку **Try it,** клиент Teams будет запущен, если он установлен; в противном случае пользователи будут перенавигуться в веб-версию Teams в браузере. По умолчанию при включении уведомлений клиенты Win32 Skype для бизнеса безмолвно загружают клиент Teams, чтобы богатый клиент был доступен до перехода пользователя в режим Teams Only; однако вы также можете отключить это поведение.  Уведомления настраиваются с помощью локальной версии, а бесшумная загрузка для клиентов Win32 контролируется с помощью локального `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` комлета.

> [!TIP]
> Некоторым серверам может потребоваться перезагрузка для работы в Skype для бизнеса 2015 с cu8.

![Уведомление о предстоящем переходе в Teams](../media/teams-upgrade-notification.png)

Чтобы уведомить пользователей о скором обновлении до Teams, создайте новый экземпляр TeamsUpgradePolicy с Помощью NotifySfBUsers=true. Затем назначьте эту политику пользователям, которых вы хотите уведомить, назначив политику непосредственно пользователю или установив политику на сайте, пуле или глобальном уровне. Следующие cmdlets создать и предоставить политику на уровне пользователя:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Автоматическая загрузка Teams через клиент Skype для бизнеса Win32 контролируется с помощью командлета TeamsUpgradeConfiguration с параметром DownloadTeams. Вы создаете эту конфигурацию на глобальном, сайте и уровне пула. Например, следующая команда создает конфигурацию для сайта Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

По умолчанию значение DownloadTeams является true; Однако это честь только *в* том случае, если NotifySfbUser = True для данного пользователя.

## <a name="see-also"></a>См. также

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Сосуществование со Skype для бизнеса](/microsoftteams/coexistence-chat-calls-presence)
