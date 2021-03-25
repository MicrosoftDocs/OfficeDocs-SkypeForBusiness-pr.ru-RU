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
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="44f5c-103">Настройка надстройки собрания Microsoft Teams для Google Workspace</span><span class="sxs-lookup"><span data-stu-id="44f5c-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="44f5c-104">Использование надстройки "Собрание Microsoft Teams" позволяет пользователям календаря Google планировать собрания Microsoft Teams и присоединяться к ним прямо из Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="44f5c-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="44f5c-105">Пользователи получат доступ к функциям собраний Teams, включая видео- и аудиоконференцию, совместный доступ к экрану, чат собрания, цифровые доски и т. д.</span><span class="sxs-lookup"><span data-stu-id="44f5c-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="44f5c-106">Оставайтесь на связи и организованность, чтобы работать вместе на работе, в школе и в жизни.</span><span class="sxs-lookup"><span data-stu-id="44f5c-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="44f5c-107">Чтобы пользователи клиента могли получить доступ к приложению, надстройка "Собрание Microsoft Teams" для Google Workspace должна быть включена администратором Teams.</span><span class="sxs-lookup"><span data-stu-id="44f5c-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="44f5c-108">Включить или отключить надстройку собрания Microsoft Teams для Google Workspace на портале Azure</span><span class="sxs-lookup"><span data-stu-id="44f5c-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="44f5c-109">Как администратор клиента вы можете включить или отключить надстройку собрания Microsoft Teams для Google Workspace из учетной записи администратора своей организации на портале Azure.</span><span class="sxs-lookup"><span data-stu-id="44f5c-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="44f5c-110">По умолчанию надстройка включена.</span><span class="sxs-lookup"><span data-stu-id="44f5c-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="44f5c-111">Во sign in to the Azure portal.</span><span class="sxs-lookup"><span data-stu-id="44f5c-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="44f5c-112">Выберите **"Корпоративные приложения**  >  **все приложения".**</span><span class="sxs-lookup"><span data-stu-id="44f5c-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="44f5c-113">Поиск **надстройки собрания Microsoft Teams для Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="44f5c-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Портал Azure со всеми приложениями](media/aad-add-google-workspace.png)

4. <span data-ttu-id="44f5c-115">Выберите **"Да".**</span><span class="sxs-lookup"><span data-stu-id="44f5c-115">Select **Yes**.</span></span>

   ![Портал Azure со свойствами рабочей области Google](media/google-workspace-properties.png)

5. <span data-ttu-id="44f5c-117">(Необязательно) Чтобы отключить надстройку, на  шаге 4 вместо "Да" выберите "Нет". </span><span class="sxs-lookup"><span data-stu-id="44f5c-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="44f5c-118">Отключение надстройки собрания Microsoft Teams для Google Workspace с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="44f5c-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="44f5c-119">Дополнительные сведения см. в сведениях о [создании основной службы Azure с помощью Azure PowerShell.](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0)</span><span class="sxs-lookup"><span data-stu-id="44f5c-119">For more information, see [Create an Azure service principal with Azure PowerShell](/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="44f5c-120">Удаление надстройки собрания Microsoft Teams для Google Workspace</span><span class="sxs-lookup"><span data-stu-id="44f5c-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="44f5c-121">Инструкции см. в [документации Google: удаление приложения Google Workspace Marketplace.](https://support.google.com/a/answer/6216211?hl=en)</span><span class="sxs-lookup"><span data-stu-id="44f5c-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>