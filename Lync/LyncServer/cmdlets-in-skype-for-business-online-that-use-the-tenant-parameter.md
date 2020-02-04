---
title: Командлеты в Skype для бизнеса Online, в которых используется параметр "клиент"
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f325c55415f97822b1e8c9d21a6d2e80e27273
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728019"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="007f8-102">Командлеты в Skype для бизнеса Online, в которых используется параметр "клиент"</span><span class="sxs-lookup"><span data-stu-id="007f8-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="007f8-103">При изменении параметров вашего общедоступного поставщика необходимо всегда предоставлять удостоверение клиента; Это справедливо даже в том случае, если у вас есть только один клиент.</span><span class="sxs-lookup"><span data-stu-id="007f8-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="007f8-104">Например, эта команда задает для Windows Live только общего поставщика, которому разрешено взаимодействовать пользователям:</span><span class="sxs-lookup"><span data-stu-id="007f8-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="007f8-105">К счастью, вам не нужно вводить код клиента (например, bf19b7db-6960-41e5-A139-2aa373474354) каждый раз при запуске одного из этих командлетов.</span><span class="sxs-lookup"><span data-stu-id="007f8-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="007f8-106">Вместо этого вы можете получить идентификатор клиента, выполнив командлет [Get-кстенант](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) , сохранив идентификатор клиента в переменной, а затем используя эту переменную при вызове одного из других командлетов.</span><span class="sxs-lookup"><span data-stu-id="007f8-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="007f8-107">Например:</span><span class="sxs-lookup"><span data-stu-id="007f8-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="007f8-108">Кроме того, вы можете сделать это в одной команде, получая идентификатор клиента, а затем переадресовать это значение командлету Set-Кстенантпубликпровидер:</span><span class="sxs-lookup"><span data-stu-id="007f8-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="007f8-109">При вызове командлета **Get-кстенант** вам не нужно указывать идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="007f8-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="007f8-110">Эта команда возвращает сведения о вашем клиенте:</span><span class="sxs-lookup"><span data-stu-id="007f8-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="007f8-111">Следующие командлеты допускают удостоверение клиента.</span><span class="sxs-lookup"><span data-stu-id="007f8-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="007f8-112">Однако в этих случаях параметр является необязательным и его не нужно вводить при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="007f8-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="007f8-113">Вместо этого Windows PowerShell будет вводить удостоверение клиента на основе клиента Skype для бизнеса Online, с которым вы уже подключены.</span><span class="sxs-lookup"><span data-stu-id="007f8-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="007f8-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="007f8-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="007f8-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="007f8-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="007f8-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="007f8-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="007f8-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="007f8-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="007f8-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="007f8-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="007f8-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="007f8-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="007f8-120">Например, командлет **Get-кстенантфедератионконфигуратион** можно вызвать с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="007f8-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="007f8-121">Хотя это не обязательно, вы можете включить параметр клиента при вызове get-Кстенантфедератионконфигуратион:</span><span class="sxs-lookup"><span data-stu-id="007f8-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="007f8-122">См. также</span><span class="sxs-lookup"><span data-stu-id="007f8-122">See Also</span></span>


[<span data-ttu-id="007f8-123">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="007f8-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="007f8-124">[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="007f8-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

