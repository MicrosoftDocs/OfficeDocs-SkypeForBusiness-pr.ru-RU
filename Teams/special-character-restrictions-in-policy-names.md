---
title: Какие существуют ограничения специального символа в политиках групп?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: В разделе проблемы в имена политик и что можно сделать для fix it для есть со специальными знаками.
ms.openlocfilehash: 6aabd3c1d7e373c048ea1d1f723f83ad1108dbe0
ms.sourcegitcommit: e5a54e2ead0edd9e450bbed4b6e50b3cfd2e91c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "21645390"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="4f505-103">Какие существуют ограничения специального символа в политиках групп?</span><span class="sxs-lookup"><span data-stu-id="4f505-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="4f505-104">**Не удается создать или изменить политики (для обмена мгновенными сообщениями, собраний, и т.д.), которые имеют специальных символов в поле имя в группами Майкрософт и Скайп по центру администрирования бизнес.**</span><span class="sxs-lookup"><span data-stu-id="4f505-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams and Skype for Business Admin Center.**</span></span> 

<span data-ttu-id="4f505-105">Если имя политики содержит специальные символы, вам будет ограничен в управлении эти политики в Microsoft групп и Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="4f505-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams and Skype for Business Admin Center.</span></span> <span data-ttu-id="4f505-106">**Таким образом, мы настоятельно рекомендуем, что имена политики не включать специальные символы**.</span><span class="sxs-lookup"><span data-stu-id="4f505-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="4f505-107">Имена политик, которые были созданы с помощью PowerShell для собраний и системы обмена сообщениями в группах может иметь специальные символы такие как @, #, $.</span><span class="sxs-lookup"><span data-stu-id="4f505-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="4f505-108">Тем не менее если которых требуется внести изменения в политике в группами Майкрософт и Скайп по центру администрирования Business, не будут иметь возможность.</span><span class="sxs-lookup"><span data-stu-id="4f505-108">However, if you are wanting to make changes to the policy in the Microsoft Teams and Skype for Business Admin Center,you won't be able to.</span></span> 

<span data-ttu-id="4f505-109">Если у вас есть политики со специальными знаками, необходимо будет либо изменить политику, с помощью Windows PowerShell (всегда), или создать новую политику в группами Майкрософт и Скайп по центру администрирования бизнес с теми же настройками, как старая политика и назначьте его же груп p пользователей.</span><span class="sxs-lookup"><span data-stu-id="4f505-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams and Skype for Business Admin Center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="4f505-110">Для удаления специальных символов</span><span class="sxs-lookup"><span data-stu-id="4f505-110">To remove special characters</span></span>



<span data-ttu-id="4f505-111">**Шаг 1 - удаленного подключения с помощью PowerShell.** 
 [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) , если она еще не установлена.</span><span class="sxs-lookup"><span data-stu-id="4f505-111">**Step 1 - Make a remote connection with PowerShell.**
[Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) if you haven't yet.</span></span>
```
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


<span data-ttu-id="4f505-112">**Шаг 2 — получить параметры для старой политики и записывать выходные данные.**</span><span class="sxs-lookup"><span data-stu-id="4f505-112">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="4f505-113">В этом примере — для политики [системы обмена сообщениями](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="4f505-113">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="4f505-114">Действия будут иметь одинаковые для других типов политики, но необходимо использовать правильный командлета.</span><span class="sxs-lookup"><span data-stu-id="4f505-114">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="4f505-115">**Шаг 3 — Создание новой политики.**</span><span class="sxs-lookup"><span data-stu-id="4f505-115">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="4f505-116">Можно создать новую политику с тот же параметр, с помощью групп Майкрософт и Скайп для бизнеса центра администрирования или PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f505-116">You can either create the new policy with the same setting using the Microsoft Teams and Skype for Business Admin Center or PowerShell.</span></span>

<span data-ttu-id="4f505-117">Выполнение этого можно создать новую политику, но необходимо добавить правильные параметры, ознакомившись [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) и затем запустить его:</span><span class="sxs-lookup"><span data-stu-id="4f505-117">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="4f505-118">**Шаг 4 - назначьте политику.**</span><span class="sxs-lookup"><span data-stu-id="4f505-118">**Step 4 - Assign the policy.**</span></span>
 ```
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="4f505-119">Отображается, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) для получения дополнительных сведений о этот командлет.</span><span class="sxs-lookup"><span data-stu-id="4f505-119">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4f505-120">**Шаг 5 – удаление старой политики.**</span><span class="sxs-lookup"><span data-stu-id="4f505-120">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="4f505-121">Это приведет к удалению старая политика со специальными знаками.</span><span class="sxs-lookup"><span data-stu-id="4f505-121">This will delete the old policy with the special characters.</span></span>
  ```
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="4f505-122">Отображается, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) для получения дополнительных сведений о этот командлет.</span><span class="sxs-lookup"><span data-stu-id="4f505-122">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="4f505-123">Если эта команда выполнена успешно, все готово.</span><span class="sxs-lookup"><span data-stu-id="4f505-123">If this command succeeds, you're done.</span></span> <span data-ttu-id="4f505-124">Приведенная выше команда возвращает ошибку, вызвано тем, что старая политика назначена пользователям, поэтому необходимо запустить для удаления всех для пользователей из политики:</span><span class="sxs-lookup"><span data-stu-id="4f505-124">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4f505-125">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f505-125">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="4f505-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="4f505-p105">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4f505-129">Почему необходимо использовать Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4f505-129">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4f505-130">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f505-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="4f505-p106">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="4f505-p106">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4f505-133">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4f505-133">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="4f505-134">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4f505-134">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4f505-135">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="4f505-135">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="4f505-136">Модуль Windows PowerShell для Скайп для бизнеса в Интернет позволяет создавать удаленного сеанса Windows PowerShell, который подключается к Скайп для бизнеса в Интернет и рабочих групп Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4f505-136">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="4f505-137">Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="4f505-137">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
### <a name="related-topics"></a><span data-ttu-id="4f505-138">See also</span><span class="sxs-lookup"><span data-stu-id="4f505-138">Related topics</span></span>
