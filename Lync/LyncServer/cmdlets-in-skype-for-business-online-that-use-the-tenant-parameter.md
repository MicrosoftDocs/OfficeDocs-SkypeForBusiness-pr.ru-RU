---
title: Командлеты в Skype для бизнеса Online, использующие параметр клиента
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
ms.openlocfilehash: 121133ce163b73bd0ddf49faa1db03ae352056d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42000934"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="e1dbf-102">Командлеты в Skype для бизнеса Online, использующие параметр клиента</span><span class="sxs-lookup"><span data-stu-id="e1dbf-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="e1dbf-103">При изменении параметров общедоступного поставщика необходимо всегда указывать идентификатор клиента; Это справедливо даже в том случае, если у вас только один клиент.</span><span class="sxs-lookup"><span data-stu-id="e1dbf-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="e1dbf-104">Например, эта команда устанавливает Windows Live как единственный общедоступный поставщик, с которым пользователям разрешено связываться:</span><span class="sxs-lookup"><span data-stu-id="e1dbf-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="e1dbf-105">К счастью, вам не нужно вводить идентификатор клиента (например, bf19b7db-6960-41e5-A139-2aa373474354) каждый раз при запуске одного из этих командлетов.</span><span class="sxs-lookup"><span data-stu-id="e1dbf-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="e1dbf-106">Вместо этого можно получить идентификатор клиента, выполнив командлет [Get – CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) , сохранив идентификатор клиента в переменной, а затем используя эту переменную при вызове одного из других командлетов.</span><span class="sxs-lookup"><span data-stu-id="e1dbf-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="e1dbf-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="e1dbf-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="e1dbf-108">Кроме того, это можно сделать в одной команде, получая идентификатор клиента, а затем переконвейеровать это значение в командлет Set – Кстенантпубликпровидер:</span><span class="sxs-lookup"><span data-stu-id="e1dbf-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="e1dbf-109">При вызове командлета **Get – CsTenant** не требуется указывать идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="e1dbf-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="e1dbf-110">Эта команда возвращает сведения о клиенте:</span><span class="sxs-lookup"><span data-stu-id="e1dbf-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="e1dbf-111">С помощью следующих командлетов вы принимаете удостоверение клиента.</span><span class="sxs-lookup"><span data-stu-id="e1dbf-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="e1dbf-112">Однако в таких случаях параметр является необязательным и его не нужно вводить при вызове командлета.</span><span class="sxs-lookup"><span data-stu-id="e1dbf-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="e1dbf-113">Вместо этого Windows PowerShell будет эффективно вводить удостоверение клиента на основе клиента Skype для бизнеса Online, к которому вы подключены:</span><span class="sxs-lookup"><span data-stu-id="e1dbf-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="e1dbf-114">[Get — CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e1dbf-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e1dbf-115">[Set — Кстенантфедератионконфигуратион](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e1dbf-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e1dbf-116">[Set — Кстенансибридконфигуратион](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e1dbf-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e1dbf-117">[Get — Кстенантфедератионконфигуратион](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e1dbf-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e1dbf-118">[Get — Кстенансибридконфигуратион](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e1dbf-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e1dbf-119">[Get — CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e1dbf-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="e1dbf-120">Например, командлет **Get – кстенантфедератионконфигуратион** можно вызвать с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="e1dbf-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="e1dbf-121">Хотя это необязательно, вы можете включить параметр клиента при вызове get — Кстенантфедератионконфигуратион:</span><span class="sxs-lookup"><span data-stu-id="e1dbf-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="e1dbf-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e1dbf-122">See Also</span></span>


[<span data-ttu-id="e1dbf-123">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e1dbf-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e1dbf-124">[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e1dbf-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

