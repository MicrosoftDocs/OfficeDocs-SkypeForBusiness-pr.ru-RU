---
title: Перенос данных из Slack в Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- NOCSH
description: Полное руководство по переносу данных из Slack в Microsoft Teams.
ms.openlocfilehash: b1e04a0dc8c829ed938b925e498e2716529356f9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098365"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a><span data-ttu-id="11827-103">Перенос данных из Slack в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="11827-103">Migrate from Slack to Microsoft Teams</span></span>

<span data-ttu-id="11827-104">В этой статье описывается процесс перехода на Microsoft Teams из Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-104">This article walks you through the journey of moving to Microsoft Teams from Slack.</span></span>

<span data-ttu-id="11827-105">При планировании перехода вашей организации на Teams из Slack важно выбрать, будет ли сохраняться какая-то информация, и если да, то какая.</span><span class="sxs-lookup"><span data-stu-id="11827-105">When planning your organization’s move to Teams from Slack, it's important to decide what you need to keep (if anything).</span></span> <span data-ttu-id="11827-106">Сначала мы опишем типы данных, которые можно перенести, а затем поэтапно расскажем, как оценить ваши потребности, спланировать переход и выполнить его.</span><span class="sxs-lookup"><span data-stu-id="11827-106">We'll start off by describing what types of data can be migrated and then walk you through how to assess your needs, plan your move, and then make the move.</span></span>

<span data-ttu-id="11827-107">На следующей схеме показана архитектура Slack в обобщенном виде.</span><span class="sxs-lookup"><span data-stu-id="11827-107">The diagram below shows the Slack architecture at a high level.</span></span>

![Изображение архитектуры Slack в обобщенном виде](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a><span data-ttu-id="11827-109">Спланируйте перенос данных из Slack</span><span class="sxs-lookup"><span data-stu-id="11827-109">Plan your migration from Slack</span></span>
### <a name="what-you-can-and-cant-migrate"></a><span data-ttu-id="11827-110">Что можно перенести, а что нельзя</span><span class="sxs-lookup"><span data-stu-id="11827-110">What you can and can’t migrate</span></span>
<span data-ttu-id="11827-111">Объем доступных для переноса данных зависит от вашего плана обслуживания Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-111">Your Slack service plan will determine what you can and can’t migrate.</span></span> <span data-ttu-id="11827-112">Например, некоторые планы обслуживания Slack позволяют экспортировать только историю и файлы общедоступных каналов, а другие требуют запроса DocuSign для включения в экспорт закрытых каналов и прямых сообщений.</span><span class="sxs-lookup"><span data-stu-id="11827-112">For example, some Slack service plans only let you export public channels history and files, other require a DocuSign request to include Private Channels and Direct Messages.</span></span> 

<span data-ttu-id="11827-113">Чтобы определить ваш уровень обслуживания рабочей области Slack, войдите в Slack и прочитайте тип плана на странице **Об этой рабочей области**.</span><span class="sxs-lookup"><span data-stu-id="11827-113">To determine your Slack Workspace service level, log into Slack and note your plan type on the **About this Workspace** page.</span></span>

<span data-ttu-id="11827-114">Дополнительные сведения о возможностях экспорта Slack можно найти на веб-сайте Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="11827-114">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

<span data-ttu-id="11827-115">На приведенной ниже схеме в обобщенном видео показан процесс переноса данных из Slack, который будет описан в этой статье.</span><span class="sxs-lookup"><span data-stu-id="11827-115">The diagram below gives you a high-level look at the Slack migration landscape that we’ll cover in this article.</span></span> 

![Схема экспорта из Slack с альбомной ориентацией.](media/migrate-slack-to-teams-image2.png)

<span data-ttu-id="11827-117">Закончив чтение этого раздела, вы будете знать:</span><span class="sxs-lookup"><span data-stu-id="11827-117">When you're done with this section, you should understand:</span></span>
- <span data-ttu-id="11827-118">уровень обслуживания ваших рабочих областей Slack;</span><span class="sxs-lookup"><span data-stu-id="11827-118">The service level of your Slack Workspaces</span></span>
- <span data-ttu-id="11827-119">что можно и нельзя экспортировать;</span><span class="sxs-lookup"><span data-stu-id="11827-119">What can and can't be exported</span></span>
- <span data-ttu-id="11827-120">общие подходы к экспорту;</span><span class="sxs-lookup"><span data-stu-id="11827-120">Common approaches to exporting</span></span>

### <a name="assess-your-slack-workspaces"></a><span data-ttu-id="11827-121">как получить доступ к рабочим областям Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-121">Assess your Slack workspaces</span></span>
<span data-ttu-id="11827-122">Прежде чем составлять план переноса данных для вашей организации, необходимо собрать сведения о ваших рабочих областях Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-122">Before you can plan your organization’s migration plan, you need to pull together some information about your Slack workspaces.</span></span> <span data-ttu-id="11827-123">Поняв, как используются рабочие области Slack, вы сможете лучше определить объем переносимых данных.</span><span class="sxs-lookup"><span data-stu-id="11827-123">Understanding how your Slack workspaces are being used helps you determine the scope of your migration.</span></span> <span data-ttu-id="11827-124">Например, сколько рабочих областей перемещается?</span><span class="sxs-lookup"><span data-stu-id="11827-124">For example, how many workspaces are being moved?</span></span> <span data-ttu-id="11827-125">Используются ли они определенным отделом, несколькими отделами или всей организацией?</span><span class="sxs-lookup"><span data-stu-id="11827-125">Are they used by a specific department, many, or in use by an entire organization?</span></span>

<span data-ttu-id="11827-126">Если вы являетесь участником рабочих областей Slack, которые хотите перенести, вы можете оценить их использование самостоятельно, перейдя на страницу *<your Slack workspace>. slack.com/stats*. Просмотрите вкладки "Каналы" и "Участники", чтобы найти закономерности в использовании.</span><span class="sxs-lookup"><span data-stu-id="11827-126">If you’re a member of the Slack Workspaces you want to migrate, you can analyze the usage yourself by going to *<your Slack workspace>.slack.com/stats*. Review the Channels and Members tabs to look for usage patterns.</span></span> <span data-ttu-id="11827-127">Определите, какие рабочие области следует перенести (а какие оставить на прежнем месте).</span><span class="sxs-lookup"><span data-stu-id="11827-127">Decide which workspaces you want to migrate (and which ones you want to leave behind).</span></span> 

> [!NOTE]
> <span data-ttu-id="11827-128">Если у вас нет доступа к странице статистики, вы не являетесь администратором или владельцем.</span><span class="sxs-lookup"><span data-stu-id="11827-128">If you don’t have access to the stats page, you’re not an admin or owner.</span></span> 

### <a name="export-channels"></a><span data-ttu-id="11827-129">Экспорт каналов</span><span class="sxs-lookup"><span data-stu-id="11827-129">Export Channels</span></span>

<span data-ttu-id="11827-130">В Slack пользователи присоединяются к каналу, который входит в состав рабочей области Slack, тогда как в Teams пользователи присоединяются к группе, которая представляет собой набор каналов.</span><span class="sxs-lookup"><span data-stu-id="11827-130">In Slack, users join a channel which is part of a Slack Workspace, whereas in Teams users join a team which is a collection of channels.</span></span> <span data-ttu-id="11827-131">Мы рекомендуем исходя из аналитики Slack определить, насколько активно ведется работа в каждом из каналов, и на основании этого выбрать каналы для переноса.</span><span class="sxs-lookup"><span data-stu-id="11827-131">We recommend that you use Slack analytics to see how much activity happens in each channel to help you decide which channels to move.</span></span> <span data-ttu-id="11827-132">Вы установите, как объединить каналы Slack в группы Teams, а также кого следует включить в каждую группу.</span><span class="sxs-lookup"><span data-stu-id="11827-132">You’ll use the resulting list to figure out how to group your Slack channels into teams in Teams as well as who should be members of each team.</span></span>

<span data-ttu-id="11827-133">Если у вас платный план обслуживания Slack (то есть любой, кроме бесплатного), аналитика Slack (<your Slack workspace>.slack.com/admin/stats#channels) позволяет определить, насколько активен канал, когда он в последний раз использовался и сколько в нем участников.</span><span class="sxs-lookup"><span data-stu-id="11827-133">If you have a paid Slack service plan (anything other than Free), you can use Slack’s analytics (<your Slack workspace>.slack.com/admin/stats#channels) to see how active a channel is, when it was last used, and how many people are members.</span></span> <span data-ttu-id="11827-134">Это позволит вам решить, нужно ли переносить канал.</span><span class="sxs-lookup"><span data-stu-id="11827-134">This can help you decide whether to migrate the channel.</span></span> <span data-ttu-id="11827-135">По умолчанию можно экспортировать содержимое общедоступных каналов (сообщения и файлы).</span><span class="sxs-lookup"><span data-stu-id="11827-135">By default, public channels content (messages and files) can be exported.</span></span> <span data-ttu-id="11827-136">В зависимости от вашего плана обслуживания Slack и от того, запрашивали ли вы в Slack закрытые каналы и прямые сообщения, их также можно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="11827-136">Depending on your Slack service plan and whether you’ve requested Private Channels and Direct Messages from Slack, those can be exported.</span></span>

<span data-ttu-id="11827-137">Дополнительные сведения о возможностях экспорта Slack можно найти на веб-сайте Slack: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="11827-137">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="11827-138">Ознакомьтесь с требованиями конфиденциальности и другими нормами вашей организации в отношении данных каналов.</span><span class="sxs-lookup"><span data-stu-id="11827-138">Check your organization’s privacy and compliance requirements around channel data.</span></span> <span data-ttu-id="11827-139">В вашей организации могут быть установлены обязательные правила обращения с этими данными, их хранения и обработки, в дополнение к правилам жизненного цикла для данных, идентифицирующих конечного пользователя (EUII).</span><span class="sxs-lookup"><span data-stu-id="11827-139">Your organization may have compliance requirements around the handling, storage, and processing of this data, in addition to complying with the lifecycle of end-user identifiable content (EUII).</span></span>

### <a name="export-direct-messages"></a><span data-ttu-id="11827-140">Экспорт прямых сообщений</span><span class="sxs-lookup"><span data-stu-id="11827-140">Export Direct Messages</span></span>
<span data-ttu-id="11827-141">Прямые сообщения — то же самое, что и чат в Teams, который представляет собой не связанные с каналами беседы один на один или одного пользователя со многими.</span><span class="sxs-lookup"><span data-stu-id="11827-141">Direct Messages are the same as chats in Teams, which are 1:1 or 1-to-many non-channel conversations.</span></span> <span data-ttu-id="11827-142">Возможность экспорта зависит от вашего плана обслуживания Slack, а также от того, запрашивали ли вы включение прямых сообщений в экспорт Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-142">Export-ability depends on your Slack service plan and if you’ve requested Direct Messages to be included in your Slack Export.</span></span> <span data-ttu-id="11827-143">В настоящий момент Teams не поддерживает импорт прямых сообщений.</span><span class="sxs-lookup"><span data-stu-id="11827-143">Teams doesn’t support importing Direct messages currently.</span></span> <span data-ttu-id="11827-144">Обратитесь к партнеру Майкрософт, чтобы узнать о сторонних решениях, которые помогают переносить содержимое прямых сообщений в Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-144">Consult a Microsoft partner to learn about third-party solutions you can explore that bring Direct Messages content into Teams.</span></span>

<span data-ttu-id="11827-145">Поищите инструменты для экспорта прямых сообщений, например Export, в магазине приложений Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-145">For exporting Direct Messages, check out tools, such as Export, in the Slack App Store.</span></span>

### <a name="apps-and-custom-integrations"></a><span data-ttu-id="11827-146">Приложения и настраиваемые интеграции</span><span class="sxs-lookup"><span data-stu-id="11827-146">Apps and custom integrations</span></span>

<span data-ttu-id="11827-147">Приложения в Slack подобны приложениям в Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-147">Apps in Slack are like apps in Teams.</span></span> <span data-ttu-id="11827-148">Если у вас есть список приложений и их конфигураций в рабочей области, вы можете поискать их в магазине приложений Teams и узнать, доступны ли они для Teams\*.</span><span class="sxs-lookup"><span data-stu-id="11827-148">Once you have a list of apps and their configurations in the Workspace, you can search in the Teams App store to see if they’re available for Teams\*.</span></span> 

<span data-ttu-id="11827-149">Список приложений и настраиваемых интеграций можно найти на странице <your Slack workspace>.slack.com/apps/manage.</span><span class="sxs-lookup"><span data-stu-id="11827-149">Go to <your Slack workspace>.slack.com/apps/manage to get a list of Apps and Custom Integrations.</span></span> <span data-ttu-id="11827-150">На этой странице также показано количество конфигураций, в которых используется каждое приложение.</span><span class="sxs-lookup"><span data-stu-id="11827-150">This page also shows you the number of configurations where each app is in use.</span></span> <span data-ttu-id="11827-151">Настраиваемые интеграции различаются по возможностям переноса.</span><span class="sxs-lookup"><span data-stu-id="11827-151">Custom Integrations vary in their “migrate-ability.”</span></span> <span data-ttu-id="11827-152">Если это веб-перехватчик, обычно его можно отправить в соединитель Microsoft 365 или Office 365 для перевода рабочего процесса в Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-152">If it’s a Web Hook, you can usually send it to a Microsoft 365 or Office 365 Connector to shift the workflow into Teams.</span></span> <span data-ttu-id="11827-153">Для ботов и других приложений возможность переноса в Teams оценивается в индивидуальном порядке.</span><span class="sxs-lookup"><span data-stu-id="11827-153">Assess bots and other apps on a case-by-case basis to plan for moving them to Teams.</span></span>

<span data-ttu-id="11827-154">\* Если ваш администратор ограничил использование приложений, полный список доступных приложений может не отображаться.</span><span class="sxs-lookup"><span data-stu-id="11827-154">\* If your administrator has restricted apps usage, you may not be looking at the full list of available apps.</span></span>

### <a name="users"></a><span data-ttu-id="11827-155">Пользователи</span><span class="sxs-lookup"><span data-stu-id="11827-155">Users</span></span>
<span data-ttu-id="11827-156">Схемы удостоверений, используемые в Slack, не всегда могут быть прямо воспроизведены в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="11827-156">The identity schemes you used in Slack might not map directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="11827-157">Например, адреса электронной почты пользователей Slack могут на соответствовать рабочим или учебным учетным записям Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="11827-157">For example, the email addresses of your Slack users may not map to Microsoft 365 or Office 365 work or school accounts.</span></span> <span data-ttu-id="11827-158">Прежде чем планировать развертывание Team, необходимо составить карту соответствий пользователей и идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="11827-158">You should create a user-ID map before you start planning your Teams rollout.</span></span>

<span data-ttu-id="11827-159">Пользователи платных планов обслуживания могут найти на странице *<your Slack workspace>. slack.com/admin/stats#members* сведения об участниках, такие как адрес электронной почты и тип учетной записи для каждого пользователя (например, записан ли он в один канал или в несколько).</span><span class="sxs-lookup"><span data-stu-id="11827-159">If you’re on a paid Slack service plan, you can go to *<your Slack workspace>.slack.com/admin/stats#members* to get member details such as email address and account type for each user (for example, single vs. multi-channel guest).</span></span>

<span data-ttu-id="11827-160">Приводим сценарий, который можно использовать для сравнения адресов электронной почты из экспорта Slack и из Microsoft Azure Active Directory и устранения неоднозначности имен.</span><span class="sxs-lookup"><span data-stu-id="11827-160">Here’s a script you can use to compare email addresses from a Slack export against Azure AD to help solve for name ambiguity.</span></span> <span data-ttu-id="11827-161">Кроме того, в нем сообщается, можно ли перенести пользователя в Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-161">It’ll also report if the user is enabled for Teams.</span></span> <span data-ttu-id="11827-162">Если вам нужна помощь по использованию PowerShell, прочтите статью [Начало работы с Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="11827-162">If you need help with PowerShell, read [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span>

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

<span data-ttu-id="11827-163">По окончании этого раздела у вас будет:</span><span class="sxs-lookup"><span data-stu-id="11827-163">When you’re done with this section, you should have:</span></span>
- <span data-ttu-id="11827-164">список каналов в рабочей области со статистикой использования;</span><span class="sxs-lookup"><span data-stu-id="11827-164">A list of Channels per Workspace with usage statistics.</span></span>
- <span data-ttu-id="11827-165">список приложений Slack с конфигурациями в каждом канале;</span><span class="sxs-lookup"><span data-stu-id="11827-165">A list of Slack Apps with configurations per channel.</span></span>
- <span data-ttu-id="11827-166">определен тип экспортируемой истории сообщений Slack (если это предполагается делать);</span><span class="sxs-lookup"><span data-stu-id="11827-166">Determined what type of Slack message history you want to export (if any).</span></span>
- <span data-ttu-id="11827-167">список пользователей, учетные записи Slack которых сопоставлены с рабочими или учебными учетными записями Майкрософт, и их лицензий на Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-167">A list of users whose Slack accounts map to Microsoft work or school accounts and which Teams license they have.</span></span>

## <a name="plan-your-teams-deployment"></a><span data-ttu-id="11827-168">Планирование развертывания Teams</span><span class="sxs-lookup"><span data-stu-id="11827-168">Plan your Teams deployment</span></span>
<span data-ttu-id="11827-169">Вы экспортировали необходимые данные из Slack (и отбросили все, что не нужно).</span><span class="sxs-lookup"><span data-stu-id="11827-169">You’ve exported what you need from Slack (and left behind anything you don’t need).</span></span> <span data-ttu-id="11827-170">Теперь пора спланировать развертывание Teams и импорт ваших данных Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-170">Now it’s time to plan how you’ll roll out Teams and import your Slack data.</span></span> <span data-ttu-id="11827-171">Это отличная возможность на базе использования определить, какие элементы хорошо подходят для группы, и включить их в план развертывания Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-171">This is a great opportunity to assess what's worked well for the team based on usage and include those elements in your Teams deployment plan.</span></span> <span data-ttu-id="11827-172">В конце этого раздела у вас будет план действий для ваших пользователей, каналов и приложений Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-172">At the end of this section, you’ll have a blueprint for your Teams users, channels, and apps.</span></span> 

<span data-ttu-id="11827-173">На следующей схеме в обобщенном виде показаны проблемы, которые будут решены при развертывании Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-173">The diagram below gives you a high-level outline of the things you’ll address in your Teams deployment.</span></span>

:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="Обобщенная схема планирования развертывания Teams из Slack.":::

### <a name="team-and-channel-structure"></a><span data-ttu-id="11827-175">Структура групп и каналов</span><span class="sxs-lookup"><span data-stu-id="11827-175">Team and channel structure</span></span>

<span data-ttu-id="11827-176">Рабочая область Slack может представлять одну группу, несколько групп или всю организацию.</span><span class="sxs-lookup"><span data-stu-id="11827-176">A Slack Workspace may represent a single team, multiple teams or an entire organization.</span></span> <span data-ttu-id="11827-177">Определяя структуру, важно понимать размеры рабочих областей.</span><span class="sxs-lookup"><span data-stu-id="11827-177">It’s important to understand the scope of the Workspaces as you determine the structure.</span></span> <span data-ttu-id="11827-178">Наиболее близкое отношение к группе Teams в Slack имеет рабочая область, которая содержит набор каналов.</span><span class="sxs-lookup"><span data-stu-id="11827-178">The closest relationship to a Teams team in Slack is the Workspace, which contains a collection of channels.</span></span> <span data-ttu-id="11827-179">На следующей схема показаны 3 различных типа соответствий между Slack и Teams, а также рекомендации по выбору правильного типа соответствия для каждой рабочей области.</span><span class="sxs-lookup"><span data-stu-id="11827-179">The diagram below demonstrates 3 different Slack-to-Teams mappings, and guidance for picking the right one for each Workspace.</span></span>


|<span data-ttu-id="11827-180">Соответствие между Slack и Teams</span><span class="sxs-lookup"><span data-stu-id="11827-180">Slack-to-Teams mapping</span></span> |  |
|---------|---------|
|<span data-ttu-id="11827-181">1 рабочая область Slack :arrow_right: 1 группа</span><span class="sxs-lookup"><span data-stu-id="11827-181">1 Slack Workspace :arrow_right: 1 team</span></span>   | <span data-ttu-id="11827-182">Для небольших рабочих областей Slack, которым требуется менее 200 каналов</span><span class="sxs-lookup"><span data-stu-id="11827-182">For smaller Slack workspaces that need fewer than 200 channels</span></span><br><span data-ttu-id="11827-183">Добавьте буфер как резерв роста и для планирования закрытых каналов</span><span class="sxs-lookup"><span data-stu-id="11827-183">Include a buffer for growth and private channel planning</span></span>  |
|<span data-ttu-id="11827-184">1 рабочая область Slack :arrow_right: несколько групп</span><span class="sxs-lookup"><span data-stu-id="11827-184">1 Slack Workspace :arrow_right: multiple teams</span></span>     | <span data-ttu-id="11827-185">Используйте данные анализа рабочей области Slack для создания логических объединений каналов, которые станут основой групп</span><span class="sxs-lookup"><span data-stu-id="11827-185">Use your Slack Workspace analytics data to create logical channel groupings, which become the basis of your teams</span></span>        |
|<span data-ttu-id="11827-186">2 и более рабочих областей Slack :arrow_right: несколько групп</span><span class="sxs-lookup"><span data-stu-id="11827-186">2+ Slack Workspaces :arrow_right: multiple teams</span></span>     | <span data-ttu-id="11827-187">Используйте данные анализа рабочей области Slack для создания логических объединений групп и каналов, которые станут основой групп</span><span class="sxs-lookup"><span data-stu-id="11827-187">Use your Slack Workspace analytics data to create logical team and channel groupings, which become the basis of your teams</span></span>        |

<span data-ttu-id="11827-188">В решениях сторонних разработчиков есть статистика использования, с помощью которой можно оценить, насколько активен канал и сколько в нем публикаций.</span><span class="sxs-lookup"><span data-stu-id="11827-188">Third-party solutions have usage statistics to help you assess how active the channel is and how many posts there are.</span></span> <span data-ttu-id="11827-189">Как правило, часто используемые каналы целесообразно включать в планирование групп.</span><span class="sxs-lookup"><span data-stu-id="11827-189">Typically, channels that are frequently used would be candidates to include in your team planning.</span></span>

> [!TIP]
> <span data-ttu-id="11827-190">Выбирая каналы, которые будут воссозданы в Teams, сохраняйте только то, что нужно для вашего подхода.</span><span class="sxs-lookup"><span data-stu-id="11827-190">Retain only what is required in your approach to determine which channels to recreate in Teams.</span></span> <span data-ttu-id="11827-191">Подробнее об этом можно прочитать в статье [Обзор групп и каналов](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="11827-191">To learn more, read [Overview of teams and channels](teams-channels-overview.md).</span></span> 

#### <a name="team-planning"></a><span data-ttu-id="11827-192">Планирование групп</span><span class="sxs-lookup"><span data-stu-id="11827-192">Team Planning</span></span>
<span data-ttu-id="11827-193">Используя перечень каналов, составленный в предыдущем разделе "Планирование", совместно с владельцами и администраторами Slack выясните, какие каналы следует сделать группами, а какие — каналами в группе.</span><span class="sxs-lookup"><span data-stu-id="11827-193">Using the Channel inventory you compiled in the Planning section above, work with your Slack owners and admins to figure out which channels should become teams and which ones should become channels in a team.</span></span> <span data-ttu-id="11827-194">Для проведения этого анализа используйте Excel или PowerBI: обе эти программы могут дать дополнительную информацию для обсуждения каналов, которые следует сохранить.</span><span class="sxs-lookup"><span data-stu-id="11827-194">Use either Excel or PowerBI to help with this analysis - both can provide additional insights to help drive these discussions on which channels to retain.</span></span>

> [!TIP]
> <span data-ttu-id="11827-195">В настоящий момент каждая группа в Teams может иметь не более 200 каналов.</span><span class="sxs-lookup"><span data-stu-id="11827-195">Teams currently has a 200-channel limit per team.</span></span> <span data-ttu-id="11827-196">Если ваш список каналов приближается к этому пределу, попробуйте разделить его на две отдельные группы.</span><span class="sxs-lookup"><span data-stu-id="11827-196">If your list of channels is getting close to that limit, you should figure out a way to split them into two separate teams.</span></span>

### <a name="channel-history"></a><span data-ttu-id="11827-197">История каналов</span><span class="sxs-lookup"><span data-stu-id="11827-197">Channel History</span></span>

<span data-ttu-id="11827-198">Для переноса истории каналов можно использовать как бесплатные инструменты из GitHub, так и платные решения, в зависимости от требований вашей организации по сохранению истории общедоступных и закрытых каналов.</span><span class="sxs-lookup"><span data-stu-id="11827-198">There are both free solutions on GitHub and paid solutions you can use, depending on your organization’s requirements to retain Channel History of Public and Private channels.</span></span> <span data-ttu-id="11827-199">Кроме того, перенос каналов можно реализовать в виде сценария в Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-199">Additionally, this could be scripted into Teams.</span></span>

<span data-ttu-id="11827-200">Когда в Teams будет сформирована структура новых групп и каналов, можно будет скопировать экспортированные файлы в соответствующие библиотеки документов в каналах Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-200">Once you’ve set up your new team and channel structure in Teams, you can copy the exported files into the appropriate document libraries in your Teams channels.</span></span>

<span data-ttu-id="11827-201">Для автоматизации импорта контента можно использовать несколько подходов.</span><span class="sxs-lookup"><span data-stu-id="11827-201">To automate the importing of your content, there are several approaches you can consider.</span></span> <span data-ttu-id="11827-202">Существуют бесплатные решения в GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) или [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) и партнерские решения.</span><span class="sxs-lookup"><span data-stu-id="11827-202">There are  free solutions on GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) or [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) and partner solutions.</span></span> <span data-ttu-id="11827-203">Выберите решение в соответствии с потребностями вашей организации.</span><span class="sxs-lookup"><span data-stu-id="11827-203">Choose a solution based on your organization’s needs.</span></span> 

### <a name="channel-files"></a><span data-ttu-id="11827-204">Файлы каналов</span><span class="sxs-lookup"><span data-stu-id="11827-204">Channel Files</span></span>

<span data-ttu-id="11827-205">Большинство решений экспортируют файлы.</span><span class="sxs-lookup"><span data-stu-id="11827-205">Most solutions will export files.</span></span> <span data-ttu-id="11827-206">Однако эти файлы обычно представлены в виде ссылок в истории канала, и для их программного извлечения требуется ключ API.</span><span class="sxs-lookup"><span data-stu-id="11827-206">However, they’re typically provided as links in the Channel History that require an API key to programmatically retrieve.</span></span>

<span data-ttu-id="11827-207">Если файлы хранятся в Slack, после формирования групп и каналов в Teams можно программным путем скопировать их из Slack в целевой канал Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-207">For files stored in Slack, once you’ve set up your teams and channels in Teams, you can programmatically copy them from Slack into the target Teams channel.</span></span>

<span data-ttu-id="11827-208">Следующий сценарий извлекает файлы из Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-208">The following script retrieves files from Slack.</span></span> <span data-ttu-id="11827-209">Он ищет указанные данные экспорта Slack на вашем компьютере, создает папку в каждом целевом канале и загружает все файлы в эту папку.</span><span class="sxs-lookup"><span data-stu-id="11827-209">It searches the specified Slack export on your computer, creates a folder in each target channel, and downloads all of the files to that location.</span></span> <span data-ttu-id="11827-210">Существуют также решения сторонних разработчиков, которые могут извлекать данные.</span><span class="sxs-lookup"><span data-stu-id="11827-210">Third-party solutions exist that can extract data.</span></span> <span data-ttu-id="11827-211">Если вам нужна помощь по использованию PowerShell, прочтите статью [Начало работы с Azure PowerShell](/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="11827-211">If you need help with PowerShell, read [Get started with Azure PowerShell](/powershell/azure/get-started-azureps).</span></span>



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a><span data-ttu-id="11827-212">Приложения и настраиваемые интеграции</span><span class="sxs-lookup"><span data-stu-id="11827-212">Apps and Custom Integrations</span></span>
<span data-ttu-id="11827-213">Просмотрите список приложений и пользовательских интеграций Slack (с конфигурациями) и решите, какие из них необходимо перенести в Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-213">Review your list of Slack apps and custom integrations (with configurations) and decide which ones you want to move to Teams.</span></span> <span data-ttu-id="11827-214">В магазине приложений Teams узнайте, доступно ли приложение.</span><span class="sxs-lookup"><span data-stu-id="11827-214">Check the Teams Marketplace to see if an app is available.</span></span> <span data-ttu-id="11827-215">Если нет, скорее всего, есть альтернативные варианты.</span><span class="sxs-lookup"><span data-stu-id="11827-215">If not, there are likely alternatives.</span></span> 

<span data-ttu-id="11827-216">Чтобы выяснить, какие приложения следует добавить в Teams, важно понять, как используется каждое приложение.</span><span class="sxs-lookup"><span data-stu-id="11827-216">To figure out which apps to add to Teams, it’s important to understand how the app is being used.</span></span> <span data-ttu-id="11827-217">Задайте себе вопрос "какую функциональность для этого канала обеспечивает приложение?", и вы поймете, какой результат дает это приложение.</span><span class="sxs-lookup"><span data-stu-id="11827-217">By asking the question "what functionality is the app providing to this channel?", you'll learn about the outcome the app is delivering.</span></span> 

<span data-ttu-id="11827-218">Во многих случаях приложения, как правило, получают вызванные событиями данные из внешней службы (например, системы мониторинга) и отправляют сообщение в Slack.</span><span class="sxs-lookup"><span data-stu-id="11827-218">In many cases, apps primarily receive event-driven data from an external service (for example, monitoring system) and push a message into Slack.</span></span> <span data-ttu-id="11827-219">Такого же результата можно добиться, используя соединитель Microsoft 365, который может отправлять сообщения в Teams, реагируя на события.</span><span class="sxs-lookup"><span data-stu-id="11827-219">You can achieve the same outcome by using a Microsoft 365 Connector that can push messages into Teams based on events.</span></span>

<span data-ttu-id="11827-220">Ниже приведены примеры решений Slack, в которых соединитель Microsoft 365 использовался в Teams для интеграции.</span><span class="sxs-lookup"><span data-stu-id="11827-220">Below are examples of Slack solutions where a Microsoft 365 Connector was used in Teams for integration.</span></span>
- <span data-ttu-id="11827-221">Ansible</span><span class="sxs-lookup"><span data-stu-id="11827-221">Ansible</span></span>
  - <span data-ttu-id="11827-222">Оповещения можно отправлять в Teams через [веб-перехватчик Ansible](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span><span class="sxs-lookup"><span data-stu-id="11827-222">Alerts can be sent to Teams via [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span></span>
- <span data-ttu-id="11827-223">New Relic</span><span class="sxs-lookup"><span data-stu-id="11827-223">New Relic</span></span>
  - <span data-ttu-id="11827-224">Ознакомьтесь с этим пользовательским решением для [отправки оповещений New Relic в Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span><span class="sxs-lookup"><span data-stu-id="11827-224">Check out this user solution for [sending New Relic alerts to Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span></span>
- <span data-ttu-id="11827-225">Nagios</span><span class="sxs-lookup"><span data-stu-id="11827-225">Nagios</span></span>
  - <span data-ttu-id="11827-226">Оповещения можно интегрировать с помощью соединителей.</span><span class="sxs-lookup"><span data-stu-id="11827-226">Alerts can be integrated today via Connectors.</span></span> <span data-ttu-id="11827-227">https://github.com/isaac-galvan/nagios-teams-notify</span><span class="sxs-lookup"><span data-stu-id="11827-227">https://github.com/isaac-galvan/nagios-teams-notify</span></span>
- <span data-ttu-id="11827-228">ZenDesk</span><span class="sxs-lookup"><span data-stu-id="11827-228">ZenDesk</span></span>
  - <span data-ttu-id="11827-229">Приложение имеется в магазине приложений Teams</span><span class="sxs-lookup"><span data-stu-id="11827-229">App exists in Teams Store</span></span>
- <span data-ttu-id="11827-230">Jenkins</span><span class="sxs-lookup"><span data-stu-id="11827-230">Jenkins</span></span>
  - <span data-ttu-id="11827-231">Оповещения можно отправлять в Teams, используя соединитель [Jenkins для Office 365](https://plugins.jenkins.io/Office-365-Connector)</span><span class="sxs-lookup"><span data-stu-id="11827-231">Alerts can be sent to Teams using [Jenkins’s Office 365 Connector](https://plugins.jenkins.io/Office-365-Connector)</span></span>


### <a name="user-readiness-and-adoption-plan"></a><span data-ttu-id="11827-232">План информирования и подготовки пользователей</span><span class="sxs-lookup"><span data-stu-id="11827-232">User readiness and adoption plan</span></span>
<span data-ttu-id="11827-233">Успех развертывания любого программного обеспечения зависит от того, насколько пользователи подготовлены к изменению.</span><span class="sxs-lookup"><span data-stu-id="11827-233">The cornerstone of any successful software deployment hinges on how prepared users are for the change.</span></span> <span data-ttu-id="11827-234">Пользователи Slack в вашей организации легко смогут понять, как работает Teams, однако чтобы переход прошел без затруднений, им требуется обучение.</span><span class="sxs-lookup"><span data-stu-id="11827-234">Users in your organization using Slack will easily understand Teams concepts, but training is still needed to help them make a smooth transition.</span></span> <span data-ttu-id="11827-235">Полный набор ресурсов по внедрению Teams можно найти в [Центре внедрения Teams](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="11827-235">For a comprehensive set of Teams adoption resources, go to the [Teams adoption hub](adopt-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="11827-236">Например, в обоих продуктах имеются каналы, но используются они по-разному.</span><span class="sxs-lookup"><span data-stu-id="11827-236">For example, both products feature channels, but they’re used differently in each product.</span></span> <span data-ttu-id="11827-237">Например, в Slack канал часто играет роль чата в Teams для кратковременных деловых сообщений.</span><span class="sxs-lookup"><span data-stu-id="11827-237">For example, often a Channel in Slack is used like a chat in Teams for short-term, transactional conversations.</span></span> <span data-ttu-id="11827-238">Другие существенные различия лежат в области бесед с ветками и без веток сообщений и точной настройки уведомлений.</span><span class="sxs-lookup"><span data-stu-id="11827-238">Other notable differences are around threaded/non-threaded conversations and tuning notification settings.</span></span>

<span data-ttu-id="11827-239">Приглашаем ознакомиться с нашей богатой библиотекой [учебных видеокурсов для конечных пользователей Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7).</span><span class="sxs-lookup"><span data-stu-id="11827-239">Check out our rich library of [End-user Teams video training](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7).</span></span> 

## <a name="move-to-teams"></a><span data-ttu-id="11827-240">Переход на Teams</span><span class="sxs-lookup"><span data-stu-id="11827-240">Move to Teams</span></span> 
<span data-ttu-id="11827-241">Теперь, когда план перехода готов, можно приступать к созданию групп и каналов в Teams.</span><span class="sxs-lookup"><span data-stu-id="11827-241">Now that your transition plan is defined, you can begin creating your teams and channels in Teams.</span></span> 

<span data-ttu-id="11827-242">Создав группы и каналы, начинайте копирование файлов из каналов Slack в Teams и настройку приложений.</span><span class="sxs-lookup"><span data-stu-id="11827-242">Once you’ve created your teams & channels, begin copying files from Slack channels into Teams and configuring your apps.</span></span> <span data-ttu-id="11827-243">Если вы используете решение для переноса истории, сейчас также можно настроить его.</span><span class="sxs-lookup"><span data-stu-id="11827-243">If you’re using a solution to retain history, that can be configured now as well.</span></span> <span data-ttu-id="11827-244">После этого вы будете готовы к лицензированию пользователей (если у них еще нет лицензий) и включению их в соответствующие группы.</span><span class="sxs-lookup"><span data-stu-id="11827-244">Then you’re ready to start licensing users (if they aren’t licensed already) and adding them to the appropriate teams.</span></span> <span data-ttu-id="11827-245">Чтобы уменьшить потребность в дополнительном экспорте и копировании файлов, рекомендуется закрыть доступ к Slack в заранее согласованный момент, соответствующий включению каждого пользователя в группу.</span><span class="sxs-lookup"><span data-stu-id="11827-245">To reduce the need for additional exports and file copies, consider removing Slack access at an agreed-upon date that coincides with each user’s addition to the team.</span></span> <span data-ttu-id="11827-246">Это устраняет необходимость повторно экспортировать и импортировать мелкие изменения файлов и журнала.</span><span class="sxs-lookup"><span data-stu-id="11827-246">This avoids needing to re-export and import delta changes on files and history.</span></span>

<span data-ttu-id="11827-247">Этапы развертывания Teams в вашей организации приведены на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="11827-247">Follow the steps in the diagram below to roll out Teams in your organization.</span></span> <span data-ttu-id="11827-248">Дополнительные сведения см. в статье [Способ развертывания Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="11827-248">For more information, check out [How to roll out Teams](./deploy-overview.md).</span></span>


:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="Схема с указанием этапов перехода в Teams из Slack.":::