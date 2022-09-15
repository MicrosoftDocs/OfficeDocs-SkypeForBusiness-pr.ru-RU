---
title: Настройка надстройки для собраний Microsoft Teams для Google Workspace
ms.author: mabond
author: mkbond007
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Узнайте, как настроить надстройку для собраний Microsoft Teams для Google Workspace.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0bd6897b770215af75862438996a365acd463c96
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706646"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a>Настройка надстройки для собраний Microsoft Teams для Google Workspace

Использование надстройки для собраний Microsoft Teams позволяет пользователям Календаря Google планировать и присоединяться к собранию Microsoft Teams непосредственно из Google Workspace. Пользователи получают доступ к функциям собраний Teams, включая видео- и аудиоконференции, демонстрацию экрана, чат собрания, цифровые доски и т. д. Оставайтесь на связи и упорядочиве, чтобы больше работать вместе на работе, в учебном заведении и в жизни.

Надстройка собрания Microsoft Teams для Google Workspace должна быть включена администратором Teams, прежде чем пользователи клиента смогут получить доступ к приложению.

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a>Включение или отключение надстройки для собраний Microsoft Teams для Google Workspace в портал Azure

Администратор клиента может включить или отключить надстройку собрания Microsoft Teams для Google Workspace из учетной записи администратора вашей организации с помощью портал Azure.

Надстройка включена по умолчанию.

1. Войдите в портал Azure.

2. Выберите **корпоративные приложения "** > **Все приложения"**.

3. Найдите **надстройку для собраний Microsoft Teams для Google Workspace**.

   ![портал Azure все приложения.](media/aad-add-google-workspace.png)

4. Выберите **"Да"**.

   ![портал Azure свойств рабочей области Google.](media/google-workspace-properties.png)

5. (Необязательно) Чтобы отключить надстройку, выберите " **Нет** " вместо **"Да** " на шаге 4.

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Отключение надстройки для собраний Microsoft Teams для Google Workspace с помощью PowerShell

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
    Get-AzureADServicePrincipal -Filter "appId eq '$appId'" | Set-AzureADServicePrincipal -AccountEnabled:$false
    Write-Host "Created and disabled the Service Principal \n"
}
```

Дополнительные сведения см. в [статье "Создание субъекта-службы Azure с Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)".

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a>Удаление надстройки собрания Microsoft Teams для Google Workspace

Инструкции см. в документации [Google По удалите приложение Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) .

## <a name="create-the-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a>Создание надстройки для собраний Microsoft Teams для Google Workspace с помощью PowerShell

Если надстройка собрания Microsoft Teams отсутствует в клиенте, ее можно создать с помощью PowerShell: 

```powershell
Connect-AzureAD

$displayName = 'Microsoft Teams meeting add-on for Google Workspace'
$appId = '7969c887-ba98-48bb-8832-6c9239929d7c'

# Check if a service principal already exists for the app
$servicePrincipal = Get-AzureADServicePrincipal -Filter "appId eq '$appId'"
if ($servicePrincipal) {
    # Service principal exists already
    Write-Host "The Service principal already exists"
} else {
    # Service principal does not yet exist, create it
    New-AzureADServicePrincipal -AppId $appId -DisplayName $displayName
    Write-Host "Created the Service Principal"
}
```
