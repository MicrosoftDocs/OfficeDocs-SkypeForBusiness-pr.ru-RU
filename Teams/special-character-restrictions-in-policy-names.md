---
title: Ограничения для специальных знаков в политиках Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Узнайте о проблемах со специальными знаками в именах политик и о том, как их устранить.
ms.openlocfilehash: 15df8b64f423d1ee20df6e230e4a9cdbebcb56db
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116987"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="8ea2f-103">Каковы ограничения для специальных знаков в политиках Teams?</span><span class="sxs-lookup"><span data-stu-id="8ea2f-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="8ea2f-104">**В Центре администрирования Microsoft Teams** нельзя создавать и изменять политики (для сообщений, собраний и т. д.), которые имеют специальный знак в имени.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="8ea2f-105">Если имя политики содержит специальные знаки, управление этими политиками будет ограничено в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8ea2f-106">Поэтому мы настоятельно рекомендуем не использовать специальные **символы.**</span><span class="sxs-lookup"><span data-stu-id="8ea2f-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="8ea2f-107">Имена политик, созданные с помощью PowerShell для собраний и обмена сообщениями в Teams, могут иметь специальные символы, такие как @,#,$.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="8ea2f-108">Однако если вы хотите внести изменения в политику в Центре администрирования Microsoft Teams, вы не сможете этого сделать.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="8ea2f-109">Если у вас есть политика со специальными символами, ее необходимо изменить с помощью Windows PowerShell (навсегда) или создать новую политику в Центре администрирования Microsoft Teams с тем же параметром, что и для старой политики, и назначить ее той же группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="8ea2f-110">Удаление специальных символов</span><span class="sxs-lookup"><span data-stu-id="8ea2f-110">To remove special characters</span></span>

<span data-ttu-id="8ea2f-111">**Шаг 1. Удаленное подключение с помощью PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="8ea2f-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="8ea2f-112">Соединитель Skype для бизнеса Online в настоящее время является частью последнего модуля Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="8ea2f-113">Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="8ea2f-114">**Шаг 2. Просмотр параметров старой политики и создание выходных данных.**</span><span class="sxs-lookup"><span data-stu-id="8ea2f-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="8ea2f-115">Это пример для политики [обмена сообщениями.](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8ea2f-115">This example is for a [Messaging](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="8ea2f-116">Действия будут одинаковыми для других типов политик, но необходимо использовать правильный cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="8ea2f-117">**Шаг 3. Создание политики.**</span><span class="sxs-lookup"><span data-stu-id="8ea2f-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="8ea2f-118">Новую политику с тем же параметром можно создать с помощью Центра администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="8ea2f-119">При запуске этой функции создается новая политика, но вам потребуется добавить правильные параметры, задав [параметры Set-CsTeamsMessagingPolicy,](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) а затем за запуск:</span><span class="sxs-lookup"><span data-stu-id="8ea2f-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="8ea2f-120">**Шаг 4. Назначение политики.**</span><span class="sxs-lookup"><span data-stu-id="8ea2f-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="8ea2f-121">Дополнительные сведения об этом cmdlet см. в подменю [Grant-CsTeamsMessagingPolicy.](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8ea2f-121">See, [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="8ea2f-122">**Шаг 5. Удаление старой политики.**</span><span class="sxs-lookup"><span data-stu-id="8ea2f-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="8ea2f-123">При этом будет удалена старая политика со специальными символами.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="8ea2f-124">Дополнительные сведения об этом cmdlet см. в [remove-CsTeamsMessagingPolicy.](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="8ea2f-124">See, [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="8ea2f-125">Если эта команда будет успешной, все готово.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="8ea2f-126">Если вышеуказанная команда возвращает ошибку, это значит, что пользователям назначена старая политика, поэтому вам нужно выполнить ее, чтобы удалить из нее всех пользователей:</span><span class="sxs-lookup"><span data-stu-id="8ea2f-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8ea2f-127">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8ea2f-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="8ea2f-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="8ea2f-129">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="8ea2f-130">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8ea2f-131">Зачем нужна служба Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8ea2f-131">Why you need to use Office 365 PowerShell?</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="8ea2f-132">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="8ea2f-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="8ea2f-133">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="8ea2f-134">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="8ea2f-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="8ea2f-135">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8ea2f-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [<span data-ttu-id="8ea2f-136">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8ea2f-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="8ea2f-137">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8ea2f-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="8ea2f-138">Модуль Windows PowerShell Skype для бизнеса Online позволяет создавать удаленные сеансы Windows PowerShell подключения к Skype для бизнеса Online и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8ea2f-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="8ea2f-139">Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="8ea2f-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
