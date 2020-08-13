---
title: Использование PowerShell для управления гостевым доступом в команде
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: Узнайте, как с помощью PowerShell разрешить или заблокировать гостевой доступ ко всем командам и определенным командам в Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e2833d1afedb975edf2532fb69c4fdbbdb31d4
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655910"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="5b30c-103">Использование PowerShell для управления гостевым доступом в команде</span><span class="sxs-lookup"><span data-stu-id="5b30c-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="5b30c-104">Кроме того, чтобы использовать центр администрирования Microsoft 365 и портал Azure Active Directory (Azure AD), вы можете управлять гостевым доступом с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5b30c-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="5b30c-105">PowerShell предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="5b30c-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="5b30c-106">Разрешение и блокирование гостевого доступа ко всем группам и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b30c-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="5b30c-107">Разрешение на добавление гостей во все группы и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b30c-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="5b30c-108">Разрешение и блокирование гостевых пользователей для определенной группы или группы Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5b30c-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="5b30c-109">Дополнительные сведения можно найти в разделе "Использование PowerShell для управления гостевым доступом" в [группах Microsoft 365 "Гостевой](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)доступ".</span><span class="sxs-lookup"><span data-stu-id="5b30c-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="5b30c-110">Вы также можете использовать PowerShell, чтобы разрешить или заблокировать гостевого пользователя по его домену.</span><span class="sxs-lookup"><span data-stu-id="5b30c-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="5b30c-111">Например, предположим, что ваша организация (Contoso) сотрудничает с другой организацией (Fabrikam).</span><span class="sxs-lookup"><span data-stu-id="5b30c-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="5b30c-112">Вы можете добавить Fabrikam в список разрешений, чтобы пользователи могли добавлять этих гостей в свои группы.</span><span class="sxs-lookup"><span data-stu-id="5b30c-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="5b30c-113">Дополнительные сведения можно найти [в разделе разрешение и блокирование гостевого доступа для групп Microsoft 365](https://go.microsoft.com/fwlink/?linkid=854001).</span><span class="sxs-lookup"><span data-stu-id="5b30c-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="5b30c-114">Если вы хотите заблокировать гостей в Teams и по-прежнему хотите разрешить им доступ к сайтам SharePoint, можно использовать командлеты Azure AD PowerShell для отключения параметра AllowGuestsToAccessGroups в объекте Company, предполагая, что внешний общий доступ включен для сайтов SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5b30c-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="5b30c-115">Включение и отключение гостевого доступа с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="5b30c-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="5b30c-116">Скачайте модуль PowerShell Skype для бизнеса Online со страницы https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="5b30c-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="5b30c-117">Подключите сеанс PowerShell к конечной точке Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="5b30c-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```powershell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="5b30c-118">Проверьте настройку, и если параметру `AllowGuestUser` присвоено значение `$False`, используйте командлет [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps), чтобы присвоить ему значение `$True`.</span><span class="sxs-lookup"><span data-stu-id="5b30c-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```powershell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="5b30c-119">Теперь у вас есть гостевые пользователи в Teams для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5b30c-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="5b30c-120">Гостевой доступ и внешний доступ</span><span class="sxs-lookup"><span data-stu-id="5b30c-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
