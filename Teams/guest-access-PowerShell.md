---
title: "Использование PowerShell для управления гостевым доступом в команде"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Используйте PowerShell, чтобы разрешить или блокировать гостевой доступ к командам в Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 563a1a56449be289572020dc226df69795596d1c
ms.sourcegitcommit: 4a396557d51c7fb246144cd682bcf5e6a2c823be
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2017
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="07b1b-103">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="07b1b-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="07b1b-104">Кроме Центра администрирования Office 365 и портала Azure Active Directory, для управления гостевым доступом вы можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07b1b-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="07b1b-105">PowerShell предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="07b1b-105">With PowerShell, you can do the following:</span></span>
  
  
   

- <span data-ttu-id="07b1b-106">Разрешение или запрет гостевого доступа для всех команд и групп Office 365</span><span class="sxs-lookup"><span data-stu-id="07b1b-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="07b1b-107">Разрешение добавления гостей во все команды и группы Office 365</span><span class="sxs-lookup"><span data-stu-id="07b1b-107">Allow guests to be added to all teams and Office 365 groups</span></span>
    
  
- <span data-ttu-id="07b1b-108">Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365</span><span class="sxs-lookup"><span data-stu-id="07b1b-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
  
<span data-ttu-id="07b1b-109">Дополнительные сведения см. в статье об [использовании PowerShell для управления гостевым доступом](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="07b1b-109">For more details, see [Use PowerShell to control guest access](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
    
    
<span data-ttu-id="07b1b-110">Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену.</span><span class="sxs-lookup"><span data-stu-id="07b1b-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="07b1b-111">Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="07b1b-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="07b1b-112">Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="07b1b-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="07b1b-113">Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="07b1b-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
 
<span data-ttu-id="07b1b-114">Если вы хотите блокировать гостей в командах, разрешив им при этом доступ к сайтам SharePoint, можете воспользоваться командлетами Powershell Azure Active Directory, чтобы отключить параметр AllowGuestAccessToGroups объекта "Company", при условии, что для сайтов SharePoint включен внешний общий доступ.</span><span class="sxs-lookup"><span data-stu-id="07b1b-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   