---
title: Настройка надстройки Microsoft Teams собрания для Google Workspace
author: cichur
ms.author: v-mahoffman
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Узнайте, как настроить Microsoft Teams собрания в Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 05f3c4553e20bb9c02ff99dcf8ad452af05f054e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777209"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Настройка надстройки Microsoft Teams собрания для Google Workspace

Использование надстройки Microsoft Teams собрания позволяет пользователям календаря Google планировать собрания и присоединяться к ним Microsoft Teams непосредственно из Google Workspace. Пользователи получат доступ к Teams собраниям, включая видео- и аудиоконференцию, общий доступ к экрану, чат собрания, цифровые доски и т. д. Оставайтесь на связи и организовывайтесь для более тесной совместной работы, учебного заведения и жизни.

Надстройка Microsoft Teams собрания для Google Workspace должна быть включена администратором Teams, чтобы пользователи клиента могли получить доступ к приложению.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal

Администратор клиента может включить или отключить надстройку Microsoft Teams собрания для Google Workspace из учетной записи администратора организации на портале Azure.

Надстройка включена по умолчанию.

1. Во войти на портал Azure.

2. Выберите **Enterprise все**  >  **приложения**.

3. Поиск **надстройки Microsoft Teams собрания для Google Workspace.**

   ![Портал Azure со всеми приложениями.](media/aad-add-google-workspace.png)

4. Выберите **Да**.

   ![Портал Azure со свойствами рабочей области Google.](media/google-workspace-properties.png)

5. (Необязательно) Чтобы отключить надстройку, в шаге 4 выберите **Нет** вместо **Да.**

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Отключение Microsoft Teams собрания в Google Workspace с помощью PowerShell

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

Дополнительные сведения см. в [этой](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)Azure PowerShell.

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Удаление надстройки Microsoft Teams собрания Google Workspace

Инструкции см. в документации Google Удаление [приложения Google Workspace Marketplace.](https://support.google.com/a/answer/6216211?hl=en)