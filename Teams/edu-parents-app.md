---
title: Настройка администратором родительского Teams для образования
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams документировать необходимые условия и настроить родителей в Teams для образования.
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af6433cb3e5ca0e1849322bdd128915e826e219b
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2022
ms.locfileid: "63040067"
---
# <a name="set-up-parent-connection-in-microsoft-teams-for-education"></a>Настройка родительского подключения в Microsoft Teams для образования

Родительское подключение в Teams для образования помогает преподавателям безопасно общаться с родителями и опекунами учащихся в их командах класса с помощью Teams чата, который будет масштабироваться в масштабах всей организации преподавателя. Все данные об опекунах и родителях Синхронизация сведений о школе, что позволяет ИТ-сотрудникам настроить все условия.

После того как родители и опекуны настроены, они могут общаться с преподавателями своих учеников, используя Teams чата. Инструкции по подключению родителей и опекунов к преподавателям см. в Подключение с преподавателями в [Teams](https://support.microsoft.com/topic/connect-with-educators-in-teams-ec2430c3-952a-4ba4-9891-1d1cab577960).

Родители также работают с контролируемым чатом. Родители и опекуны не имеют полных разрешений на доступ Teams, что означает, что они не могут начинать беседы с учащимися или удалять пользователей с полными разрешениями (например, преподавателей) из чатов. Дополнительные сведения о контрольном чате см[. в этой](supervise-chats-edu.md) Microsoft Teams.

## <a name="requirements"></a>Требования

### <a name="school-data-sync"></a>Синхронизация сведений о школе

- Для заполнения Синхронизация сведений о школе контактных данных каждого учащегося и опекуна необходимо в Синхронизация сведений о школе (SDS).
  - [Развертывание SDS](/schooldatasync/parents-and-guardians-in-sds)

- Если вам нужна помощь в настройке SDS и заполнении контактов, связанных с родителями и опекунами, для учащихся в клиенте, обратитесь в службу успешного обслуживания клиентов EDU по:
  - Завершение процесса RFA [на FastTrack.](https://www.microsoft.com/fasttrack?rtc=1)
  - Открытие билета в службу [поддержки](https://aka.ms/sdssupport).

- В настоящее время SDS поддерживает только просмотр данных на основе CSV для родительских контактов. однако вы можете использовать [синхронизацию API PowerSchool](/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync) или [Синхронизацию API OneRoster](/schooldatasync/how-to-deploy-school-data-sync-by-using-oneroster-sync) для всех данных в список и просто добавить родительские контакты с помощью CSV-файлов.
  - Создайте второй профиль синхронизации в формате [синхронизации SDS v1 CSV](/schooldatasync/school-data-sync-format-csv-files-for-sds).
  - Потяните два [пустых](/schooldatasync/parent-contact-sync-file-format) родительских файла с остальными файлами v1 (только с заглавными словами).
    - User.csv
    - Guardianrelationship.csv
  - Чтобы просмотреть образец CSV-файлов v1, см. в GitHub [атрибуты](https://github.com/OfficeDev/O365-EDU-Tools/tree/master/CSV%20Samples/SDS%20Format/Min%20Required%20Attributes).
  - Если вы хотите автоматизировать потянивание CSV-файлов после начальной синхронизации, ознакомьтесь с нашим документом автоматизации синхронизации [CSV-файлов](/schooldatasync/csv-file-sync-automation).
  - За помощью в настройке синхронизации данных SDS можно связаться с [](https://www.microsoft.com/fasttrack?rtc=1) нашей успешной командой клиентов или создать [билет в службу поддержки](https://edusupport.microsoft.com/support?product_id=data_sync).

### <a name="teams-admin-center---policies"></a>Teams администрирования — политики

- Владельцы группы класса должны Teams чат включен.
- Владельцы команд класса должны иметь внешний доступ к учетным **Teams, которые не управляются организацией**.
  - Этот должен быть включен на уровне клиента и на уровне пользователя. Параметры на уровне клиента можно найти в > **внешний доступ** в центре администрирования Teams клиента. Этот параметр также можно получить с помощью PowerShell. Доступ к политикам внешнего доступа на уровне пользователей можно получить только с помощью PowerShell. Дополнительные инструкции см. в командах PowerShell ниже.

> [!NOTE]
>Родители и опекуны классифицируются как внешние пользователи в функции "Родители", то есть у них нет полных прав клиента. У них есть доступ только к чату или чатам, в которые они добавлены, а также к файлам, изображениям и другому содержимому, к совместному доступу в чате.
>
>Кроме того, внешние пользователи могут видеть присутствие (в автономном режиме, в сети, занят и т. д.), но его можно отключить с помощью PowerShell для защиты конфиденциальности пользователей. В PowerShell используйте [Set-CsPrivacyConfiguration](/powershell/module/skype/set-csprivacyconfiguration?view=skype-ps) и установите ``EnablePrivacyMode=true``.
>
>Даже если родители и опекуны являются внешними пользователями, их вклад в чаты можно обнаружить. Узнайте, как проводить исследования Teams eDiscovery, изучив их в этой [Microsoft Teams.](ediscovery-investigation.md)

## <a name="allow-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Разрешить внешний доступ с учетными Teams, которые не управляются организацией

Чтобы разрешить преподавателям общаться с родителями и опекунами в Teams, ИТ-администратор клиента для образования должен обновить политики клиента, чтобы разрешить внешний доступ Teams учетным записям за пределами клиента. Дополнительные сведения об управлении внешним доступом можно получить [в этой Microsoft Teams](manage-external-access.md).

Вот как можно включить внешний доступ для родителей и опекунов.

1. Установите последнюю предварительную Microsoft Teams PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```

2. Используя учетные данные с полномочиями администратора, запустите следующие команды:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

    Параметр политики, который включает внешний доступ Teams учетных записей, не управляемых организацией на уровне пользователя (`EnableTeamsConsumerAccess`), по умолчанию включен для всех политик внешнего доступа на уровне пользователя. Параметры политики на уровне клиента и политики на уровне пользователя должны быть включены для внешнего доступа к учетным Teams, которые не управляются организацией. Если вы не хотите, чтобы этот доступ был включен для всех пользователей в клиенте, убедитесь, что параметр на уровне клиента отключен, обновите политики внешнего доступа на уровне пользователя, которые назначены пользователям, а затем включите параметр на уровне клиента.

    Чтобы проверить, какие политики внешнего доступа на уровне пользователя существуют и кому они назначены, можно сделать следующее:

3. Проверьте, существуют ли политики внешнего доступа на уровне пользователя.

    ```powershell
    Get-CsExternalAccessPolicy
    ```

4. Для каждой политики, кроме глобальной, проверьте, какие пользователи назначены политике.

   > [!NOTE]
   > Все пользователи, которым не назначена определенная политика, снова будут подпадать под "глобальную" политику. Всем новым пользователям, добавленным в клиент, будет назначена глобальная политика.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

`EnableTeamsConsumerAccess` Так как для всех политик внешнего доступа на уровне пользователей по умолчанию установлено значение true, `EnableTeamsConsumerAccess` вы можете создать или изменить существующие политики внешнего доступа с скорректированной настройкой и (или) перенаправить пользователей на новые или существующие политики с помощью следующих надстройок PowerShell:

- Создание новой политики внешнего доступа [: New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Настройка существующей политики внешнего доступа (включая глобальную): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Невозможно изменить следующие политики подписки по умолчанию: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". По умолчанию всем пользователям была назначена политика FederationAndPICDefault, но теперь новым пользователям по умолчанию назначена глобальная политика. Если вам нужно изменить параметры политики для пользователей, которым назначены эти политики по умолчанию подписки, назначьте им различные политики с правильными настройками.

- Назначение политики внешнего доступа одному пользователю: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Назначение политики для набора пользователей: [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

После правильной настройки политик внешнего доступа на уровне пользователя для пользователей в клиенте вы можете включить параметр на уровне клиента (`AllowTeamsConsumer`) с помощью следующего cmdlet:

- Настройка параметров конфигурации федерации для клиента: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="turn-on-the-parents-app-in-the-teams-admin-center"></a>Включит приложение "Родители" в Центре Teams администрирования

Приложение "Родители" по умолчанию отключено, поэтому владельцы команд класса не будут видеть его в своих командах класса, пока оно не будет разрешено через центр Teams администрирования. Приложение "Родители" включено в центре администрирования Teams с помощью разрешить приложения[, заблокированные издателями](manage-apps.md#apps-blocked-by-publishers).

В любое время приложение можно отключить на уровне клиента, используя разрешение и блокировку [](manage-apps.md#allow-and-block-apps) приложений Teams центре администрирования. Если она отключена на уровне клиента, она будет заблокирована для всех пользователей, даже если на уровне пользователя включены разрешения.

Приложение "Родители" также можно отключить на уровне пользователя с помощью управления политиками разрешений приложений в [Microsoft Teams](teams-app-permission-policies.md).

## <a name="more-information"></a>Дополнительные сведения

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
