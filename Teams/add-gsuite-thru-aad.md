---
title: Настройка надстройки для собраний Microsoft Teams в Google Workspace
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
description: Сведения о том, как настроить надстройку для собраний Microsoft Teams для Google Workspace.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c86d707a4298d88d3ae0cff389bda73490390e4
ms.sourcegitcommit: 882ed439f8bba27b1cf0c14056c146267cacd359
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "49387310"
---
# <a name="set-up-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="16725-103">Настройка надстройки для собраний Microsoft Teams в Google Workspace</span><span class="sxs-lookup"><span data-stu-id="16725-103">Set up Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="16725-104">С помощью надстройки для собраний Microsoft Teams можно планировать пользователей Google календаря и присоединяться к собранию Microsoft Teams прямо из Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="16725-104">Using the Microsoft Teams meeting add-on lets Google calendar users schedule and join a Microsoft Teams meeting directly from Google Workspace.</span></span> <span data-ttu-id="16725-105">Пользователи получают доступ к функциям собраний Teams, в том числе к видеоконференциям и голосовой связи, демонстрации экрана, чат для собраний, цифровых досках и т. д.</span><span class="sxs-lookup"><span data-stu-id="16725-105">Users will get access to Teams meetings features including video and audio conferencing, screen sharing, meeting chat, digital whiteboards, and more.</span></span> <span data-ttu-id="16725-106">Оставайтесь на связи и работайте над ними, чтобы больше узнать о работе в рамках работы, учебного заведения и жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="16725-106">Stay connected and organized to get more done together across work, school, and life.</span></span>

<span data-ttu-id="16725-107">Надстройка для собраний Microsoft Teams для Google Workspace должна быть включена администратором Teams, прежде чем пользователи клиента смогут получить доступ к приложению.</span><span class="sxs-lookup"><span data-stu-id="16725-107">The Microsoft Teams meeting add-on for Google Workspace must be enabled by a Teams admin before tenant users can access the app.</span></span>

## <a name="enable-or-disable-microsoft-teams-meeting-add-on-for-google-workspace-in-the-azure-portal"></a><span data-ttu-id="16725-108">Включение и отключение надстройки Microsoft Teams для собрания в Google Workspace на портале Azure</span><span class="sxs-lookup"><span data-stu-id="16725-108">Enable or disable Microsoft Teams meeting add-on for Google Workspace in the Azure portal</span></span>

<span data-ttu-id="16725-109">Как администратор клиента вы можете включить или отключить надстройку собрания Microsoft Teams для рабочей области Google из учетной записи администратора организации с помощью портала Azure.</span><span class="sxs-lookup"><span data-stu-id="16725-109">As a tenant administrator, you can enable or disable a Microsoft Teams meeting add-on for Google Workspace from your organization's admin account using the Azure portal.</span></span>

<span data-ttu-id="16725-110">Надстройка включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16725-110">The add-on is enabled by default.</span></span>

1. <span data-ttu-id="16725-111">Войдите на портал Azure.</span><span class="sxs-lookup"><span data-stu-id="16725-111">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="16725-112">Выберите **корпоративное приложение**  >  **все приложения**.</span><span class="sxs-lookup"><span data-stu-id="16725-112">Select **Enterprise applications** > **All applications**.</span></span>

3. <span data-ttu-id="16725-113">Поиск **надстройки Microsoft Teams для собраний в Google Workspace**.</span><span class="sxs-lookup"><span data-stu-id="16725-113">Search for **Microsoft Teams meeting add-on for Google Workspace**.</span></span>

   ![Портал Azure, отображающий все приложения](media/aad-add-google-workspace.png)

4. <span data-ttu-id="16725-115">Нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="16725-115">Select **Yes**.</span></span>

   ![Портал Azure, отображающий свойства Google Workspace](media/google-workspace-properties.png)

5. <span data-ttu-id="16725-117">Необязательно Чтобы отключить надстройку, выберите пункт **нет** , а не **Да** в действии 4.</span><span class="sxs-lookup"><span data-stu-id="16725-117">(Optional) To disable the add-on, select **No** instead of **Yes** in Step 4.</span></span>

## <a name="disable-microsoft-teams-meeting-add-on-for-google-workspace-using-powershell"></a><span data-ttu-id="16725-118">Отключение надстройки Microsoft Teams для собрания в Google Workspace с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="16725-118">Disable Microsoft Teams meeting add-on for Google Workspace using PowerShell</span></span>

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

<span data-ttu-id="16725-119">Дополнительные сведения можно найти [в разделе Создание субъекта-службы Azure с помощью Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span><span class="sxs-lookup"><span data-stu-id="16725-119">For more information, see [Create an Azure service principal with Azure PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-5.0.0).</span></span>

## <a name="delete-the-microsoft-teams-meeting-add-on-for-google-workspace"></a><span data-ttu-id="16725-120">Удаление надстройки Microsoft Teams для собрания в Google Workspace</span><span class="sxs-lookup"><span data-stu-id="16725-120">Delete the Microsoft Teams meeting add-on for Google Workspace</span></span>

<span data-ttu-id="16725-121">Инструкции по [удалению приложения Google Workspace Marketplace](https://support.google.com/a/answer/6216211?hl=en) вы видите в документации Google.</span><span class="sxs-lookup"><span data-stu-id="16725-121">See the Google documentation [Delete a Google Workspace Marketplace app](https://support.google.com/a/answer/6216211?hl=en) for instructions.</span></span>
