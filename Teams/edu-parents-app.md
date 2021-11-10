---
title: Настройка администратором приложения "Родители Microsoft EDU" в Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams для статьи с EDU, документировать предварительные условия и настроить приложение "Родители".
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9243dfedb11c9102673e821bd2fac9d06cf3c834
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887297"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Развертывание приложения "Родители" в Microsoft Teams

Приложение "Родители" помогает преподавателям безопасно общаться с родителями и опекунами учащихся в их командах класса с помощью Teams чата, который будет масштабироваться в масштабах всей организации преподавателя. Все данные об опекунах и родителях Синхронизация сведений о школе, что позволяет ИТ-сотрудникам настроить все условия.

## <a name="requirements"></a>Требования

### <a name="school-data-sync"></a>Синхронизация сведений о школе

- Чтобы заполнить контактные данные родителей и опекунов каждого учащегося, вам потребуется Синхронизация сведений о школе (SDS). 
  - [Развертывание SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Если вам нужна помощь в настройке SDS  и заполнении контактов, связанных с родителями и опекунами, для учащихся в клиенте, обратитесь в службу успешного обслуживания клиентов EDU по:
  - Завершение процесса RFA на [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Открытие билета в службу [поддержки](https://aka.ms/sdssupport).

### <a name="teams-admin-center---policies"></a>Teams Центр администрирования — политики

- Владельцы группы класса должны включить Teams чат.
- Владельцы команд класса должны иметь внешний доступ к учетным Teams, которые **не управляются организацией.** 
  - Эта возможность должна быть включена на уровне клиента и на уровне пользователей. Параметры на уровне клиента можно найти в > **внешний доступ** в Teams администрирования. Этот параметр также можно получить с помощью PowerShell. Доступ к политикам внешнего доступа на уровне пользователей можно получить только с помощью PowerShell. Дополнительные инструкции см. в командах PowerShell ниже.

## <a name="enabling-external-access-with-teams-accounts-not-managed-by-an-organization"></a>Включение внешнего доступа Teams учетных записей, не управляемых организацией

1. Установите последнюю версию модуля Microsoft Teams PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Используя учетные данные с полномочиями администратора, запустите следующие команды:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

Параметр политики, который обеспечивает внешний доступ Teams учетных записей, не управляемых организацией на уровне пользователя (), по умолчанию включен для всех политик внешнего доступа на уровне `EnableTeamsConsumerAccess` пользователя. Параметры политики на уровне клиента и политики на уровне пользователя должны быть включены для внешних учетных записей Teams, которые не управляются организацией. Если вы не хотите, чтобы этот доступ был включен для всех пользователей в клиенте, убедитесь, что параметр на уровне клиента отключен, обновите политики внешнего доступа на уровне пользователя, которые назначены пользователям, и включите параметр на уровне клиента.

Чтобы проверить, какие политики внешнего доступа на уровне пользователя существуют и кому они назначены, можно сделать следующее:
    
3. Проверьте, какие политики внешнего доступа на уровне пользователя существуют.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Для каждой политики, кроме глобальной, проверьте, какие пользователи назначены политике. Примечание. Все пользователи, которым не назначена определенная политика, снова будут подпадать под "глобальную" политику. Всем новым пользователям, добавленным в клиент, будет назначена глобальная политика.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

Так как для всех политик внешнего доступа на уровне пользователей по умолчанию установлено значение true, вы можете создать или изменить существующие политики внешнего доступа с скорректированной настройкой и (или) перенаправить пользователей на новые или существующие политики с помощью следующих рабочихлетов `EnableTeamsConsumerAccess` `EnableTeamsConsumerAccess` PowerShell:

- Создание новой политики внешнего [доступа: New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Настройка существующей политики внешнего доступа (включая глобальную): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> Невозможно изменить следующие политики подписки по умолчанию: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". По умолчанию всем пользователям была назначена политика FederationAndPICDefault, но теперь новым пользователям по умолчанию назначена глобальная политика. Если вам нужно изменить параметры политики для пользователей, которым назначены эти политики по умолчанию подписки, назначьте им различные политики с правильными настройками.

- Назначение политики внешнего доступа одному пользователю: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Назначение политики для набора пользователей: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

После правильной настройки политик внешнего доступа на уровне пользователя для пользователей в клиенте вы можете включить параметр на уровне клиента () с помощью следующего `AllowTeamsConsumer` cmdlet:

- Настройка параметров конфигурации федерации для клиента: [Set-CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)

## <a name="disabling-the-parents-app"></a>Отключение приложения "Родители"

Приложение "Родители" включено по умолчанию, поэтому все владельцы команд класса будут видеть его в своих командах класса. 

Приложение можно отключить на уровне клиента, используя разрешение и блокировку приложений в Microsoft Teams центре администрирования. [](manage-apps.md#allow-and-block-apps) Если приложение отключено на уровне клиента, оно будет заблокировано для всех пользователей, даже если включены разрешения на уровне пользователей.

Приложение также можно отключить на уровне пользователя с помощью управления политиками разрешений [приложений в Microsoft Teams.](teams-app-permission-policies.md)

## <a name="more-information"></a>Дополнительные сведения

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [CsTenantFederationConfiguration](/powershell/module/skype/set-cstenantfederationconfiguration)
