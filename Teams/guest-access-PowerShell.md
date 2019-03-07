---
title: Использование PowerShell для управления гостевым доступом в команде
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/09/17
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: Используйте PowerShell, чтобы разрешить или блокировать гостевой доступ к командам в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9215cdbc360f1bda1d9d0ea75c1a9fe6ab0f458
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464590"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="ea17e-103">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="ea17e-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="ea17e-104">Кроме Центра администрирования Office 365 и портала Azure Active Directory, для управления гостевым доступом вы можете использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ea17e-104">In addition to using the Office 365 admin center and the Azure Active Directory portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="ea17e-105">PowerShell предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="ea17e-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="ea17e-106">Разрешение или запрет гостевого доступа для всех команд и групп Office 365</span><span class="sxs-lookup"><span data-stu-id="ea17e-106">Allow or block guest access to all teams and Office 365 groups</span></span>
    
- <span data-ttu-id="ea17e-107">Разрешение добавления гостей во все команды и группы Office 365</span><span class="sxs-lookup"><span data-stu-id="ea17e-107">Allow guests to be added to all teams and Office 365 groups</span></span>
      
- <span data-ttu-id="ea17e-108">Разрешение или блокировка гостевых пользователей из определенной команды или группы Office 365</span><span class="sxs-lookup"><span data-stu-id="ea17e-108">Allow or block guest users from a specific team or Office 365 group</span></span>
    
<span data-ttu-id="ea17e-109">Для получения дополнительных сведений обратитесь к разделу «Использование PowerShell для управления доступом Гость» на вкладке Управление [гостевого доступа в Office 365 групп](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span><span class="sxs-lookup"><span data-stu-id="ea17e-109">For details, see the section "Use PowerShell to control guest access" on the Manage tab of [Guest access in Office 365 Groups](https://support.office.com/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell).</span></span>
  
<span data-ttu-id="ea17e-110">Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену.</span><span class="sxs-lookup"><span data-stu-id="ea17e-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="ea17e-111">Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="ea17e-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="ea17e-112">Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="ea17e-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="ea17e-113">Дополнительные сведения см. в статье [Разрешение и блокировка гостевого доступа к группам Office 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="ea17e-113">For more information, see [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="ea17e-114">Если вы хотите блокировать гостей в командах, разрешив им при этом доступ к сайтам SharePoint, можете воспользоваться командлетами Powershell Azure Active Directory, чтобы отключить параметр AllowGuestAccessToGroups объекта "Company", при условии, что для сайтов SharePoint включен внешний общий доступ.</span><span class="sxs-lookup"><span data-stu-id="ea17e-114">If you want to block guests in teams and still allow guests to access SharePoint sites, you can use Azure Active Directory Powershell cmdlets to disable the AllowGuestAccessToGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>   

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="ea17e-115">Доступ в качестве гостя и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="ea17e-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]