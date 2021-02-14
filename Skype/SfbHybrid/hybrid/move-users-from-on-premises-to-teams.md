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
description: Сводка. Узнайте, как перенести параметры пользователей и переместить пользователей в Teams.
ms.openlocfilehash: 49763d7674946eb179188554326863f4860252c3
ms.sourcegitcommit: 7966991c398cd80f6bd0bb21e57a6b2a97c09ea9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "49130650"
---
# <a name="move-users-from-on-premises-to-teams"></a>Перемещение пользователей из локальной среды в Teams

Когда пользователь перемещается из локальной точки в режим "Только Teams", его домашняя учетная запись Skype для бизнеса перемещается из локальной в интернет-сеть, а пользователю назначено приложение TeamsUpgradePolicy с режимом mode=TeamsOnly.  После того как пользователь перемещается из локальной сети в режим TeamsOnly:

- Все входящие звонки и чаты от других пользователей (отправленные из Skype для бизнеса или Teams) будут перенаправываться в клиент Teams пользователя.
- Пользователь сможет работать с другими пользователями Skype для бизнеса (как в интернете, так и в локальной сети).
- Пользователь сможет общаться с пользователями в федераированных организациях.
- Новые собрания, запланированные этим пользователем, являются собраниями Teams.
- Пользователь по-прежнему может присоединяться к любым собраниям Skype для бизнеса.
- Существующие собрания пользователя, запланированные на будущее, будут перенесены из локальной сети в Teams.
- Контакты, которые существовали локально, доступны в Teams вскоре после того, как пользователь впервые вошел в систему.
- Пользователи не могут инициировать звонки или чаты из Skype для бизнеса и не могут планировать новые собрания в Skype для бизнеса. Если они попытаются открыть клиент Skype для бизнеса, они будут перенаправлены на использование Teams, как показано ниже. Если клиент Teams не установлен, он будет направлен в веб-версию Teams с помощью браузера.<br><br>
    ![Перенаправление пользователя в Teams](../media/go-to-teams-page.png)

Перед перемещением пользователей обязательно просмотрите необходимые условия для перемещения пользователей в облако. [](move-users-between-on-premises-and-cloud.md#prerequisites) Также обязательно просмотрите руководство по миграции и совместному использованию для организаций, использующих [Teams вместе со Skype для бизнеса.](/microsoftteams/migration-interop-guidance-for-teams-with-skype)


> [!NOTE]
> Чтобы контакт был перемещен в Teams, необходимо отключить единое хранилище контактов в учетной записи SfB на основе учетной записи SfB.


Существует два способа перемещения пользователя из локальной сети в Teams:

- Если вы используете версию, более ранную, чем Skype для бизнеса Server 2015 с cu8, перемещение требует двух шагов (которые можно с помощью скриптов сделать вместе как один шаг, если это необходимо):
  - [Перемещение пользователя из Skype для бизнеса Server (локально) в Skype для бизнеса Online.](move-users-from-on-premises-to-skype-for-business-online.md)
  - После того как пользователь будет находится в Skype для бизнеса Online, назначьте пользователю TeamsUpgradePolicy режим = TeamsOnly. Чтобы предоставить режим TeamsOnly, запустите следующий командлет в окне PowerShell Skype для бизнеса Online: `Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams`
- Если у вас есть средства администрирования из Skype для бизнеса Server 2015 CU8 или более поздней, вы можете использовать описанный выше метод или сделать это перемещение за один шаг, как описано ниже. Кроме того, при желании вы можете предоставить уведомление в клиенте Skype для бизнеса перед их перемещением только в Teams, а также при желании загрузить клиент Teams автоматически клиентом Skype для бизнеса.

## <a name="move-a-user-directly-from-skype-for-business-on-premises-to-teams-only"></a>Перемещение пользователя непосредственно из локальной сети Skype для бизнеса в только Teams

Средства локального администрирования в Skype для бизнеса Server 2015 с cu8, а также в Skype для бизнеса Server 2019 позволяют переместить пользователей из локального режима в режим "Только Teams" за один шаг с помощью командлета Move-CsUser в PowerShell или панели управления Skype для бизнеса Server, как описано ниже.

### <a name="move-to-teams-using-move-csuser"></a>Переход на Teams с помощью Move-CsUser

Move-CsUser доступна в окне PowerShell локальной оболочки управления Skype для бизнеса. Действия ниже и необходимые разрешения такие же, как перемещение пользователя в Skype для бизнеса Online, за исключением того, что необходимо также указать переключатель MoveToTeams, и необходимо убедиться, что пользователю также предоставлена лицензия на Teams (в дополнение к Skype для бизнеса Online).

Необходимо иметь достаточные привилегии как в локальной среде, так и в облачной службе (Microsoft 365 или Office 365), как описано в необходимых учетных данных [администратора.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials) Можно использовать одну учетную запись с привилегиями в обеих средах или запустить окно локальной оболочки управления Skype для бизнеса Server с учетными данными локальной среды и использовать параметр для указания учетных данных для учетной записи `-Credential` Microsoft 365 или Office 365 с необходимой административной ролью.

Чтобы переместить пользователя в режим "Только Teams" с помощью move-CsUser:

- Укажите пользователя, который будет перемещаться, с помощью `Identity` параметра.
- Укажите параметр -Target со значением sipfed.online.lync. <span> com".
- Укажите `MoveToTeams` переключатель.
- Если у вас нет одной учетной записи с достаточными разрешениями как в локальной, так и в облачной службе (Microsoft 365 или Office 365), используйте этот параметр, чтобы предоставить учетную запись с достаточными разрешениями в `-credential` Office 365.
- Если учетная запись с разрешениями в Microsoft 365 или Office 365 не заканчивается на "onmicrosoft". <span> com", необходимо указать параметр с правильным значением, как описано в `-HostedMigrationOverrideUrl` [необходимых учетных данных администратора.](move-users-between-on-premises-and-cloud.md#required-administrative-credentials)

Следующая последовательность командлетов может использоваться для перемещения пользователя в TeamsOnly и предполагает, что учетные данные Microsoft 365 или Office 365 — это отдельная учетная запись, которая предоставляется в качестве входных данных для Get-Credential запроса.

  ```powershell
  $cred=Get-Credential
  $url="https://admin1a.online.lync.com/HostedMigration/hostedmigrationService.svc"
  Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -MoveToTeams -Credential $cred -HostedMigrationOverrideUrl $url
  ```

### <a name="move-to-teams-using-skype-for-business-server-control-panel"></a>Переход на Teams с помощью панели управления Skype для бизнеса Server

1. Откройте приложение панели управления Skype для бизнеса Server.
2. В области навигации слева выберите **"Пользователи"**.
3. Используйте **поиск** пользователей, которые вы хотите перейти в Teams.
4. Выберите пользователей, а затем в  выпадаемом списке "Действие" выберите "Переместить выбранных **пользователей в Teams".**
5. В мастере нажмите кнопку **Далее**.
6. При запросе во sign in to Microsoft 365 or Office 365 with an account that ends in .onmicrosoft.com and has sufficient permissions.
7. Нажмите **кнопку**"Далее", а затем еще раз, чтобы переместить пользователя. 
8. Обратите внимание, что сообщения о состоянии, касающиеся успешного или неудачного сбоя, предоставляются в верхней части основного приложения панели управления, а не в мастере.

## <a name="notify-your-skype-for-business-on-premises-users-of-the-upcoming-move-to-teams"></a>Уведомление пользователей локальной сети Skype для бизнеса о предстоящем переходе на Teams

Средства локального администрирования в Skype для бизнеса Server 2015 с cu8, а также в Skype для бизнеса Server 2019 позволяют уведомлять пользователей локальной сети Skype для бизнеса о предстоящем переходе на Teams. Если включить эти уведомления, пользователи увидят уведомление в клиенте Skype для бизнеса (Win32, Mac, Web и mobile), как показано ниже. Если пользователи  нажмет кнопку "Попробовать", клиент Teams будет запущен, если он установлен; в противном случае пользователи переходят в веб-версию Teams в браузере. По умолчанию, когда уведомления включены, клиенты Win32 Skype для бизнеса автоматически скачивает клиент Teams, чтобы до перемещения пользователя в режим "Только Teams" был доступен богатый клиент; однако вы также можете отключить это поведение.  Уведомления настраиваются с использованием локальной версии, а скачиванием в тихом режиме для клиентов Win32 управляется с помощью локального `TeamsUpgradePolicy` `TeamsUpgradeConfiguration` cmdlet.

> [!TIP]
> Для работы в Skype для бизнеса 2015 с cu8 некоторым серверам может потребоваться перезагрузка.

![Уведомление о предстоящем переходе на Teams](../media/teams-upgrade-notification.png)

Чтобы уведомить пользователей локальной сети о том, что они скоро будут обновлены до Teams, создайте новый экземпляр TeamsUpgradePolicy с notifySfBUsers=true. Затем назначьте эту политику пользователям, которых вы хотите уведомить, назначив политику непосредственно пользователю или назначив политику на уровне сайта, пула или глобального уровня. Следующие cmdlets create and grant a user-level policy:

```powershell
New-CsTeamsUpgradePolicy -Identity EnableNotifications -NotifySfbUser $true
Grant-CsTeamsUpgradePolicy -Identity username@contoso.com -PolicyName EnableNotifications
```

Автоматическая загрузка Teams через клиент Skype для бизнеса Win32 управляется с помощью локального командлета TeamsUpgradeConfiguration с параметром DownloadTeams. Эта конфигурация создается на глобальном уровне, на уровне сайта и пула. Например, следующая команда создает конфигурацию для сайта Redmond1:

```powershell
New-CsTeamsUpgradeConfiguration -Identity "site:redmond1"
```

По умолчанию значение DownloadTeams — True; однако он *будет* соблюдаться, только если NotifySfbUser = True для данного пользователя.

## <a name="see-also"></a>См. также

[Move-CsUser](https://docs.microsoft.com/powershell/module/skype/move-csuser)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy
)

[Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

[Сосуществование со Skype для бизнеса](/microsoftteams/coexistence-chat-calls-presence)
