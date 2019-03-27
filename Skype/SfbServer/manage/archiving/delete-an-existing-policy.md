---
title: Удаление существующей политики в Скайп архивации для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Сводка: Узнайте, как для удаления политики архивации для Скайп для Business Server.'
ms.openlocfilehash: 1210dacc85ea28d2968d602431d5a9bdf7bcc4b9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878430"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="c594b-103">Удаление существующей политики в Скайп архивации для Business Server</span><span class="sxs-lookup"><span data-stu-id="c594b-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="c594b-104">**Сводка:** Узнайте, как для удаления политики архивации для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c594b-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="c594b-105">Можно удалить политику пользователей или сайта, но не глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="c594b-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="c594b-106">Если удалить глобальную политику, Скайп для Business Server автоматически устанавливает политики значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c594b-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="c594b-107">Удаление политику архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="c594b-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="c594b-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c594b-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c594b-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c594b-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c594b-110">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="c594b-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="c594b-111">В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c594b-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="c594b-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c594b-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="c594b-113">Удаление политики с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c594b-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="c594b-114">Политики архивации также можно удалить с помощью командлета **Remove-CsArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="c594b-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="c594b-p102">Например, следующая команда удаляет политику с идентификатором site:Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования.</span><span class="sxs-lookup"><span data-stu-id="c594b-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="c594b-117">Данная команда удаляет все политики архивации, примененные на уровне пользователей:</span><span class="sxs-lookup"><span data-stu-id="c594b-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="c594b-118">Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:</span><span class="sxs-lookup"><span data-stu-id="c594b-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="c594b-119">Для получения дополнительных сведений см раздел справки по командлет [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="c594b-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
