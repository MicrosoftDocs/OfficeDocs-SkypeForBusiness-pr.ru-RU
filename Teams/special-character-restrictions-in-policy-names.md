---
title: Каковы ограничения для специальных знаков в политиках Teams?
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
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: Посмотрите, какие проблемы имеют специальные символы в именах политик и что можно сделать для их исправления.
ms.openlocfilehash: 169f427cc0efc444adfbc7e0f8056337e615f733
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568660"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="285e8-103">Каковы ограничения для специальных знаков в политиках Teams?</span><span class="sxs-lookup"><span data-stu-id="285e8-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="285e8-104">**Вы не можете создавать и изменять политики (для сообщений, собраний и т. д.), у которых есть специальный символ в имени в центре администрирования Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="285e8-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="285e8-105">Если имя политики содержат специальные символы, вы будете ограничиваться управлением этими политиками в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="285e8-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="285e8-106">Поэтому **мы настоятельно рекомендуем использовать в именах политик специальные символы**.</span><span class="sxs-lookup"><span data-stu-id="285e8-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="285e8-107">Имена политик, созданные с помощью PowerShell для собраний и обмена сообщениями в Teams, могут содержать специальные символы, такие как @, #, $.</span><span class="sxs-lookup"><span data-stu-id="285e8-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="285e8-108">Тем не менее, если вы хотите внести изменения в политику в центре администрирования Microsoft Teams, вам не удастся.</span><span class="sxs-lookup"><span data-stu-id="285e8-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="285e8-109">Если у вас есть политика со специальными символами, вам нужно либо изменить политику с помощью Windows PowerShell (бессрочно), либо создать новую политику в центре администрирования Microsoft Teams с теми же параметрами, что и у старой политики, и назначить ее той же группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="285e8-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="285e8-110">Удаление специальных знаков</span><span class="sxs-lookup"><span data-stu-id="285e8-110">To remove special characters</span></span>

<span data-ttu-id="285e8-111">**Шаг 1: Создание удаленного подключения с помощью PowerShell.** 
 [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , если вы еще не сделали этого.</span><span class="sxs-lookup"><span data-stu-id="285e8-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="285e8-112">**Шаг 2: получение параметров для старой политики и запись выходных данных.**</span><span class="sxs-lookup"><span data-stu-id="285e8-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="285e8-113">Этот пример предназначен для политики [обмена сообщениями](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="285e8-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="285e8-114">Эти шаги будут одинаковыми для других типов политик, но необходимо использовать правильный командлет.</span><span class="sxs-lookup"><span data-stu-id="285e8-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="285e8-115">**Шаг 3: создание новой политики.**</span><span class="sxs-lookup"><span data-stu-id="285e8-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="285e8-116">Вы можете создать новую политику с тем же параметром, используя центр администрирования Microsoft Teams или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="285e8-116">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="285e8-117">При выполнении этой команды будет создана новая политика, но вам потребуется добавить правильные параметры, просмотрев параметр [Set-кстеамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) , а затем запустить его:</span><span class="sxs-lookup"><span data-stu-id="285e8-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="285e8-118">**Шаг 4: назначение политики.**</span><span class="sxs-lookup"><span data-stu-id="285e8-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="285e8-119">Дополнительные сведения об этом командлете: [Grant-кстеамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="285e8-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="285e8-120">**Шаг 5 — Удаление старой политики.**</span><span class="sxs-lookup"><span data-stu-id="285e8-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="285e8-121">Старая политика будет удалена с использованием специальных символов.</span><span class="sxs-lookup"><span data-stu-id="285e8-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="285e8-122">Для получения дополнительных сведений о данном командлете, щелкните ссылку [Remove-кстеамсмессагингполици](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="285e8-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="285e8-123">Если эта команда выполнена успешно, все готово.</span><span class="sxs-lookup"><span data-stu-id="285e8-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="285e8-124">Если команда выше возвращает сообщение об ошибке, это связано с тем, что старая политика назначается пользователям, поэтому для удаления всех назначенных пользователей из политики необходимо выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="285e8-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="285e8-125">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="285e8-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="285e8-p105">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="285e8-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="285e8-129">Зачем использовать Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="285e8-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="285e8-130">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="285e8-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="285e8-131">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности при использовании только в центре администрирования Microsoft 365, например при изменении параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="285e8-131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="285e8-132">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="285e8-132">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="285e8-133">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="285e8-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="285e8-134">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="285e8-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="285e8-135">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="285e8-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="285e8-136">Модуль Windows PowerShell для Skype для бизнеса Online позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online и Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="285e8-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="285e8-137">Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="285e8-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

