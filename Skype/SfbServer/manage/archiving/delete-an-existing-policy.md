---
title: Удаление существующей политики архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Сводка: Удаление политики архивации в Skype для бизнеса Server.'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278414"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="d6271-103">Удаление существующей политики архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d6271-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="d6271-104">**Сводка:** Сведения о том, как удалить политику архивации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d6271-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="d6271-105">Можно удалить политику пользователей или сайта, но не глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="d6271-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="d6271-106">Если вы удалите глобальную политику, в Skype для бизнеса Server автоматически восстанавливаются значения по умолчанию для этой политики.</span><span class="sxs-lookup"><span data-stu-id="d6271-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="d6271-107">Удаление политику архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="d6271-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="d6271-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d6271-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d6271-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d6271-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d6271-110">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="d6271-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="d6271-111">В списке политик архивации щелкните политику пользователей или сайта, которую следует удалить, щелкните **Изменить**, затем **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="d6271-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="d6271-112">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d6271-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="d6271-113">Удаление политики с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d6271-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="d6271-114">Политики архивации также можно удалить с помощью командлета **Remove-CsArchivingPolicy**.</span><span class="sxs-lookup"><span data-stu-id="d6271-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="d6271-p102">Например, следующая команда удаляет политику с идентификатором site:Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования.</span><span class="sxs-lookup"><span data-stu-id="d6271-p102">For example, the following command deletes the policy with the Identity site:Redmond. When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="d6271-117">Данная команда удаляет все политики архивации, примененные на уровне пользователей:</span><span class="sxs-lookup"><span data-stu-id="d6271-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="d6271-118">Данная команда удаляет все политики архивации, в которых отключена внутренняя архивация:</span><span class="sxs-lookup"><span data-stu-id="d6271-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="d6271-119">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксарчивингполици](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="d6271-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
