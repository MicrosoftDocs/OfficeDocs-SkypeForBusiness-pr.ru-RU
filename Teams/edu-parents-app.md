---
title: Настройка администратора для приложения Microsoft Parents EDU
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Microsoft Teams для документов в статье EDU и настройка PowerShell для приложения "Родители".
ms.localizationpriority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b79319da9f901fc4546c25d5165f4d2361521a7
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537010"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Развертывание родительского приложения в Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Включение родительского приложения в Microsoft Teams — это простой процесс для администраторов, позволяющий преподавателям безопасно общаться с учащимися и их контактами, которые остаются в клиенте и которые будут масштабироваться в масштабах всей организации вашего преподавателя.

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
  - Этот параметр можно найти в параметрах для всей организации > внешнего доступа на уровне клиента или если вы хотите включить для определенного набора пользователей, см. PowerShell ниже.

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

По умолчанию параметр на уровне клиента, который Teams внешний доступ для клиента (AllowTeamsConsumer), отключен. Однако параметр политики, который Teams внешний доступ на уровне пользователя (EnableTeamsConsumerAccess), по умолчанию включен для всех политик внешнего доступа на уровне пользователя. Для доступа к внешне Teams му доступу пользователя необходимо включить как параметры на уровне клиента, так и параметры политики на уровне пользователя. Если вы не хотите, чтобы все пользователи в вашем клиенте включили внешний доступ Teams, обновите политики внешнего доступа на уровне пользователей, которые назначены пользователям, прежде чем включить параметр на уровне клиента.

Если вам нужно проверить, какие политики внешнего доступа на уровне пользователей существуют и кому они назначены, можно сделать следующее:
    
3. Проверьте, какие политики внешнего доступа существуют на уровне пользователя.

    ```powershell
    Get-CsExternalAccessPolicy -Include All
    ```

4. Для каждой политики, кроме глобальной, проверьте, какие пользователи назначены политике. Примечание. Все пользователи, которым не назначена определенная политика, снова будут подпадать под "глобальную" политику.

    ```powershell
    Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq “<PolicyName>"} | Select-Object DisplayName,ObjectId,UserPrincipalName
    ```

### <a name="further-powershell-options"></a>Дополнительные параметры PowerShell

Так как для всех политик внешнего доступа на уровне пользователей по умолчанию установлен параметр EnableTeamsConsumerAccess, если вы хотите изменить любую из этих политик для настройки параметра EnableTeamsConsumerAccess, вы можете создать новые политики внешнего доступа с скорректированной настройкой или перенастроить пользователей на новые или существующие политики с помощью следующей PowerShell:

- Создание политики внешнего доступа (создание политики внешнего доступа и определение параметров): [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy)

- Настройка существующей политики внешнего доступа (изменяет параметры существующей политики внешнего доступа, включая глобальную)): [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)

> [!NOTE]
> По умолчанию нельзя изменить следующие подписки: "FederationAndPICDefault", "FederationOnly", "NoFederationAndPIC". Если вам нужно изменить параметры политики для пользователей, которым назначены эти политики, назначьте им различные политики с правильными настройками.

- Назначение политики внешнего доступа одному пользователю: [Grant-CsExternalAccessPolicy](/powershell/module/skype/grant-csexternalaccesspolicy)

- Назначение политики для набора пользователей: [New-CsBatchPolicyAssignmentOperation](/powershell/module/skype/new-csbatchpolicyassignmentoperation)

После того как вы будете уверены, что политики внешнего доступа на уровне пользователей настроены правильно для всех пользователей, вы можете включить параметр на уровне клиента, который управляет доступом Teams внешнего доступа к нему для клиента, используя следующий cmdlet:

- Настройка параметров конфигурации федерации для клиента (для параметра AllowTeamsConsumer задайте true): [Set-CsTenantFederationConfiguration (SkypeForBusiness)](/powershell/module/skype/set-cstenantfederationconfiguration)

### <a name="disabling-the-parents-app"></a>Отключение приложения "Родители"

Приложение "Родители" включено по умолчанию, поэтому все владельцы занятий будут видеть его в команде класса. Приложение можно отключить на уровне клиента, используя разрешение и блокировку приложений в Microsoft Teams центре администрирования. [](manage-apps.md#allow-and-block-apps) Если эта возможность отключена на уровне клиента, она будет заблокирована для всех пользователей, даже если включено разрешение на уровне пользователя.

Это также можно отключить на уровне пользователя с помощью [Управление политиками разрешений приложений в Microsoft Teams]. (teams-app-permission-policies.md).

## <a name="more-information"></a>Дополнительные сведения

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Назначение политики пользователю](/powershell/module/skype/grant-csexternalaccesspolicy)
