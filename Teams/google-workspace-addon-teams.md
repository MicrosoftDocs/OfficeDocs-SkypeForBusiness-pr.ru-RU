---
title: Настройка надстройки собрания Microsoft Teams для Google Workspace
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Узнайте, как настроить надстройка собрания Microsoft Teams для Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e1b7024190ac51b89e09fafced86ffea13f5961
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120700"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Настройка надстройки собрания Microsoft Teams для Google Workspace

Использование надстройки "Собрание Microsoft Teams" позволяет пользователям календаря Google планировать собрания Microsoft Teams и присоединяться к ним прямо из Google Workspace. Пользователи получат доступ к функциям собраний Teams, включая видео- и аудиоконференцию, совместный доступ к экрану, чат собрания, цифровые доски и т. д. Оставайтесь на связи и организованность, чтобы работать вместе на работе, в школе и в жизни.

Чтобы пользователи клиента могли получить доступ к приложению, надстройка "Собрание Microsoft Teams" для Google Workspace должна быть включена администратором Teams.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Включить или отключить надстройку собрания Microsoft Teams для Google Workspace на портале Azure

Как администратор клиента вы можете включить или отключить надстройку собрания Microsoft Teams для Google Workspace из учетной записи администратора своей организации на портале Azure.

По умолчанию надстройка включена.

1. Во sign in to the Azure portal.

2. Выберите **"Корпоративные приложения**  >  **все приложения".**

3. Поиск **надстройки собрания Microsoft Teams для Google Workspace.**

   ![Портал Azure со всеми приложениями](media/aad-add-google-workspace.png)

4. Выберите **"Да".**

   ![Портал Azure со свойствами рабочей области Google](media/google-workspace-properties.png)

5. (Необязательно) Чтобы отключить надстройку, на  шаге 4 вместо "Да" выберите "Нет". 

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Отключение надстройки собрания Microsoft Teams для Google Workspace с помощью PowerShell

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already, disable it
    Set-AzureADServicePrincipal -ObjectId $servicePrincipal.ObjectId -AccountEnabled $false
    Write-Host "Disabled existing Service Principal \n"
} else {
    # Service principal does not yet exist, create it and disable it at the same time
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    $servicePrincipal = New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName -AccountEnabled $false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Дополнительные сведения см. в сведениях о [создании основной службы Azure с помощью Azure PowerShell.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Удаление надстройки собрания Microsoft Teams для Google Workspace

Инструкции см. в [документации Google: удаление приложения Google Workspace Marketplace.](https://support.google.com/a/answer/6216211?hl=en)