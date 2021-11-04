---
title: Настройка администратора для приложения Microsoft Parents EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams для документов из статьи EDU и настройка PowerShell для приложения "Родители".
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8cd05f6ad2b238b4db2d611a6fc00e5f8a57189f
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785152"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Развертывание родительского приложения в Microsoft Teams

Родительское приложение помогает преподавателям безопасно общаться с родителями и опекунами учащихся в их классах с помощью Teams чата, который будет масштабироваться в масштабах всей организации преподавателя. Все данные об опекунах и родителях Синхронизация сведений о школе, что позволяет преподавателям и ИТ-сотрудникам настроить все условия.

## <a name="requirements"></a>Требования

### <a name="school-data-sync"></a>Синхронизация сведений о школе

- Чтобы заполнить Синхронизация сведений о школе контактных данных каждого учащегося, вам **потребуется** Синхронизация сведений о школе (SDS).
  - [Развертывание SDS](/schooldatasync/how-to-deploy-sds-using-sds-v2.1-csv-files)

- Если вам нужна помощь по настройке SDS и включите родительские контакты в клиенте, обратитесь в службу успешного обслуживания клиентов EDU по:
  - Завершение процесса RFA на [FastTrack](https://www.microsoft.com/fasttrack?rtc=1).
  - Открытие билета в службу [поддержки](https://aka.ms/sdssupport).

### <a name="teams-admins-center---policies"></a>Teams Центр администрирования — политики

- Владелец класса должен включить чат
- Владелец класса должен иметь внешний доступ **с учетными Teams, которые не управляются организацией.** 
  - Этот параметр можно найти в > внешний доступ на уровне клиента или если вы хотите включить для определенного набора пользователей, см. PowerShell ниже.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Включение федератного чата для каждого пользователя

1. Установите последнюю версию модуля Microsoft Teams PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force –AllowClobber
    ```
    
2. Используя учетные данные с полномочиями администратора, в окне команд запустите следующую команду:

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

Параметр политики, который Teams внешний доступ на уровне пользователя (EnableTeamsConsumerAccess), по умолчанию включен для всех политик внешнего доступа на уровне пользователя. Для доступа к внешнему доступу пользователей необходимо включить параметры на уровне клиента (AllowTeamsConsumer Teams) и политику на уровне пользователя. Если вы не хотите, чтобы все пользователи в вашем клиенте включили внешний доступ Teams, обновите политики внешнего доступа на уровне пользователей, которые назначены пользователям, прежде чем включить параметр на уровне клиента.

Если вам нужно проверить, какие политики внешнего доступа на уровне пользователей существуют и кому они назначены, можно сделать следующее:
    
3. Проверьте, какие политики внешнего доступа существуют на уровне пользователя.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Для каждой политики, кроме глобальной, проверьте, какие пользователи назначены политике. Примечание. Все пользователи, которым не назначена определенная политика, снова будут подпадать под "глобальную" политику

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>Дополнительные параметры PowerShell

Так как для всех политик внешнего доступа на уровне пользователей по умолчанию установлен параметр EnableTeamsConsumerAccess, если вы хотите изменить любую из этих политик для настройки параметра EnableTeamsConsumerAccess, вы можете создать новые политики внешнего доступа с скорректированной настройкой или перенастроить пользователей на новые или существующие политики с помощью следующей PowerShell:

- Создание политики внешнего доступа (создание политики внешнего доступа и определение параметров): [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Настройка существующей политики внешнего доступа (изменяет параметры существующей политики внешнего доступа, включая глобальную)): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> По умолчанию нельзя изменить следующие подписки: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". Если вам нужно изменить параметры политики для пользователей, которым назначены эти политики, назначьте им различные политики с правильными настройками.

- Назначение политики внешнего доступа одному пользователю: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Назначение политики для набора пользователей: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

После того как вы будете уверены, что политики внешнего доступа на уровне пользователей настроены правильно для всех пользователей, вы можете включить параметр на уровне клиента, который управляет внешним доступом Teams для клиента, используя следующий cmdlet:

- Настройка параметров конфигурации федерации для клиента (для параметра AllowTeamsConsumer задайте true): [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>Отключение приложения "Родители"

Приложение "Родители" включено по умолчанию, поэтому все владельцы занятий будут видеть его в команде класса. Приложение можно отключить на уровне клиента, используя разрешение и блокировку приложений в Microsoft Teams центре администрирования. [](manage-apps.md#allow-and-block-apps) Если эта возможность отключена на уровне клиента, она будет заблокирована для всех пользователей, даже если включено разрешение на уровне пользователя.

Это также можно отключить на уровне пользователя с помощью [Управление политиками разрешений приложений в Microsoft Teams]. (teams-app-permission-policies.md).

## <a name="more-information"></a>Дополнительные сведения

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Назначение политики пользователю](/powershell/module/skype/grant-csexternalaccesspolicy)
