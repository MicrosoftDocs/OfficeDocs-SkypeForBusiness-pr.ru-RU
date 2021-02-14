---
title: Удаление существующей политики архива в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: Сводка. Узнайте, как удалить политику архива для Skype для бизнеса Server.
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817619"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="b2e9d-103">Удаление существующей политики архива в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b2e9d-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="b2e9d-104">**Сводка:** Узнайте, как удалить политику архива для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="b2e9d-105">Можно удалить политику пользователя или политику сайта, но не глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="b2e9d-106">При удалении глобальной политики Skype для бизнеса Server автоматически сбрасывает политику до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="b2e9d-107">Удаление политики с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="b2e9d-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="b2e9d-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b2e9d-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b2e9d-110">В левой панели навигации щелкните **"Мониторинг и** архивации" и выберите "Политика **архивации".**</span><span class="sxs-lookup"><span data-stu-id="b2e9d-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="b2e9d-111">В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="b2e9d-112">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="b2e9d-113">Удаление политики с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2e9d-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="b2e9d-114">Вы также можете удалить политики архива с помощью **cmdlet Remove-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="b2e9d-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="b2e9d-115">Например, следующая команда удаляет политику с идентификатором site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="b2e9d-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="b2e9d-116">При удалении политики, настроенной на уровне сайта, пользователи, которыми ранее управляла политика сайта, будут автоматически управляться глобальной политикой архива:</span><span class="sxs-lookup"><span data-stu-id="b2e9d-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="b2e9d-117">Эта команда удаляет все политики архива, применяемые на уровне пользователя:</span><span class="sxs-lookup"><span data-stu-id="b2e9d-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="b2e9d-118">Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:</span><span class="sxs-lookup"><span data-stu-id="b2e9d-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="b2e9d-119">Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b2e9d-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
