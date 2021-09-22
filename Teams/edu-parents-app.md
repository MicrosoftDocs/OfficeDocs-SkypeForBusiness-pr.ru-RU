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
ms.openlocfilehash: 9ca2c252964f610ee13924f25f5d4ca8e31b9d59
ms.sourcegitcommit: 4a9ea18808d17e2eb6e4e2e7e3894e33c14e8631
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2021
ms.locfileid: "59475916"
---
# <a name="deploying-the-parents-app-in-microsoft-teams"></a>Развертывание родительского приложения в Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Включение родительского приложения в Microsoft Teams — это простой процесс для администраторов, позволяющий преподавателям безопасно общаться с учащимися и их контактами, которые остаются в клиенте и которые будут масштабироваться в масштабах всей организации преподавателя.

## <a name="requirements"></a>Требования

- SDS (school data sync) — вам потребуется добавить связанные контакты, связанные с учащимися, в SDS с помощью CSV-параметра. Дополнительные сведения можно получить в настройках [CSV для SDS](/schooldatasync/set-up-your-sds-flow) и Обновление связанныхконтактов. [](/graph/api/relatedcontact-update)
- В Teams администратора владелец класса должен  включить чат, а **федераированный** чат с учетными Teams, не управленными **организацией.**

Если вам нужно включить федераированный чат для каждого пользователя, с помощью этих действий можно сделать вот что.

## <a name="enabling-federated-chat-on-a-per-user-basis"></a>Включение федератного чата для каждого пользователя

1. Установите последнюю предварительную Microsoft Teams PowerShell.

    ```powershell
    Install-Module -Name PowerShellGet -Force -AllowClobber
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force -AllowClobber
    ```
    
2. Запустите в окне команды с учетными данными, у которых есть права администратора.

    ```powershell
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```
    
3. Отключите и включите настройку глобальной конфигурации на уровне группы или пользователя или на уровне клиента.

    ```powershell
    #Retrieves tenant level configuration
    Get-CsTenantFederationConfiguration
    #Turn OFF tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $false
    #Turn ON tenant level configuration
    Set-CsTenantFederationConfiguration -AllowTeamsConsumer $true
    #Turn OFF Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    #Turn ON Global GROUP/USER level configuration
    Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false
    ```
        
    > [!NOTE]
    > При запуске этой powerShell на внесение изменений может пройти не менее часа.
    
## <a name="more-information"></a>Дополнительные сведения

- [CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)
- [Назначение политики пользователю](/powershell/module/skype/grant-csexternalaccesspolicy)
