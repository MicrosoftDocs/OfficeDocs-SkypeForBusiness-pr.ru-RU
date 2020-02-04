---
title: Командлеты в Skype для бизнеса Online, использующие только глобальную область
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use only the global scope
ms:assetid: 0ffd3bc9-a6a1-4c2e-8d52-e599acc49d2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362771(v=OCS.15)
ms:contentKeyID: 56558800
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5610649295fdf4089372d9c59e4ccb51228c1fc2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728109"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-only-the-global-scope"></a><span data-ttu-id="8fe1c-102">Командлеты в Skype для бизнеса Online, использующие только глобальную область</span><span class="sxs-lookup"><span data-stu-id="8fe1c-102">Cmdlets in Skype for Business Online that use only the global scope</span></span>

 


<span data-ttu-id="8fe1c-103">Ряд параметров Skype для бизнеса Online доступен только в *глобальной области*.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-103">A number of Skype for Business Online settings are available only at the *global scope*.</span></span> <span data-ttu-id="8fe1c-104">Это означает, что существует единственная коллекция параметров, которая применяется ко всем пользователям, которые назначены этому клиенту.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-104">This means that there is a single collection of settings that applies to all the users who are assigned to that tenant.</span></span> <span data-ttu-id="8fe1c-105">(У каждого клиента есть своя уникальная коллекция глобальных параметров.) При использовании командлетов, ограниченных глобальной областью, параметр Identity является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-105">(Each tenant has its own unique collection of global settings.) When you are using cmdlets that are limited to the global scope, the Identity parameter is optional.</span></span> <span data-ttu-id="8fe1c-106">Например, чтобы получить параметры конфигурации собрания, можно использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8fe1c-106">For example, to retrieve meeting configuration settings, you can use this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="8fe1c-107">Кроме того, вы можете опустить параметр Identity и использовать эту простую команду вместо этого:</span><span class="sxs-lookup"><span data-stu-id="8fe1c-107">Alternatively, you can omit the Identity parameter and use this simpler command instead:</span></span>

    Get-CsMeetingConfiguration

<span data-ttu-id="8fe1c-108">Так как имеется только одна глобальная коллекция параметров конфигурации собрания, две команды возвращают одни и те же данные.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-108">Because there is only one global collection of meeting configuration settings, the two commands return the exact same information.</span></span> <span data-ttu-id="8fe1c-109">Параметр Identity также можно опустить при использовании одного из командлетов **Set-CS** .</span><span class="sxs-lookup"><span data-stu-id="8fe1c-109">The Identity parameter can also be omitted when using one of the **Set-Cs** cmdlets.</span></span> <span data-ttu-id="8fe1c-110">Эти две команды идентичны:</span><span class="sxs-lookup"><span data-stu-id="8fe1c-110">These two commands are identical:</span></span>

    Set-CsMeetingConfiguration -Identity "global" -AdmitAnonymousUsersByDefault $False
    Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False

<span data-ttu-id="8fe1c-111">Две команды идентичны, так как по умолчанию Windows PowerShell изменит глобальную коллекцию, если не включить параметр Identity.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-111">The two commands are identical because, by default, Windows PowerShell will modify the global collection if you do not include the Identity parameter.</span></span>

<span data-ttu-id="8fe1c-112">Следующие командлеты работают только в глобальной области:</span><span class="sxs-lookup"><span data-stu-id="8fe1c-112">The following cmdlets operate only at the global scope:</span></span>

  - <span data-ttu-id="8fe1c-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-113">[Get-CsImFilterConfiguration](https://technet.microsoft.com/en-us/library/gg398980\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-114">[Get-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg425875\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-115">[Get-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg413002\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-116">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-117">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-118">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-119">[Get-CsTenantPublicProvider](https://technet.microsoft.com/en-us/library/jj994016\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-120">[Remove-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398309\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-121">[Set-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/gg398648\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8fe1c-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-122">[Set-CsPrivacyConfiguration](https://technet.microsoft.com/en-us/library/gg398484\(v=ocs.15\))</span></span>

<span data-ttu-id="8fe1c-123">Обратите внимание, что командлет **Remove-ксвоицеполици** является какой-либо аномалией.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-123">Note that the **Remove-CsVoicePolicy** cmdlet is something of an anomaly.</span></span> <span data-ttu-id="8fe1c-124">Для начала для этого командлета требуется включить параметр Identity:</span><span class="sxs-lookup"><span data-stu-id="8fe1c-124">First, this cmdlet does require you to include the Identity parameter:</span></span>

    Remove-CsVoicePolicy -Identity "global"

<span data-ttu-id="8fe1c-125">Во-вторых, командлет **Remove-ксвоицеполици** фактически не удаляет глобальную политику голосовой связи; В Skype для бизнеса Online запрещено удалять глобальные политики и параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-125">Second, the **Remove-CsVoicePolicy** cmdlet does not actually delete the global voice policy; Skype for Business Online does not allow you to delete global policies or configuration settings.</span></span> <span data-ttu-id="8fe1c-126">Действие командлета — это возможность сброса всех свойств в глобальной политике голосовой связи в значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-126">What the cmdlet does do is enable you to reset all the properties in the global voice policy to their default values.</span></span> <span data-ttu-id="8fe1c-127">Например, по умолчанию для свойства Алловкаллфорвардинг задано значение false.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-127">For example, by default, the AllowCallForwarding property is set to False.</span></span> <span data-ttu-id="8fe1c-128">Тем не менее, Алловкаллфорвардинг может быть изменено, и теперь для него установлено значение true.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-128">However, AllowCallForwarding may have been modified, with the value now set to True.</span></span> <span data-ttu-id="8fe1c-129">При запуске командлета **Remove-ксвоицеполици** свойству алловкаллфорвардинг будет возвращено значение по умолчанию: false.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-129">When you run the **Remove-CsVoicePolicy** cmdlet, the AllowCallForwarding property will revert to its default value: False.</span></span> <span data-ttu-id="8fe1c-130">В приведенной ниже таблице перечислены сценарии.</span><span class="sxs-lookup"><span data-stu-id="8fe1c-130">The following table summarizes this scenario:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fe1c-131">Значение Алловкаллфорвардинг</span><span class="sxs-lookup"><span data-stu-id="8fe1c-131">AllowCallForwarding Value</span></span></th>
<th><span data-ttu-id="8fe1c-132">Сценарий</span><span class="sxs-lookup"><span data-stu-id="8fe1c-132">Scenario</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fe1c-133">False</span><span class="sxs-lookup"><span data-stu-id="8fe1c-133">False</span></span></p></td>
<td><p><span data-ttu-id="8fe1c-134">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8fe1c-134">Default value</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fe1c-135">Верно</span><span class="sxs-lookup"><span data-stu-id="8fe1c-135">True</span></span></p></td>
<td><p><span data-ttu-id="8fe1c-136">После изменения глобальной политики</span><span class="sxs-lookup"><span data-stu-id="8fe1c-136">After the global policy has been modified</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fe1c-137">False</span><span class="sxs-lookup"><span data-stu-id="8fe1c-137">False</span></span></p></td>
<td><p><span data-ttu-id="8fe1c-138">После запуска командлета <strong>Remove-ксвоицеполици</strong></span><span class="sxs-lookup"><span data-stu-id="8fe1c-138">After <strong>Remove-CsVoicePolicy</strong> cmdlet has been run</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="see-also"></a><span data-ttu-id="8fe1c-139">См. также</span><span class="sxs-lookup"><span data-stu-id="8fe1c-139">See Also</span></span>


[<span data-ttu-id="8fe1c-140">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8fe1c-140">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="8fe1c-141">[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8fe1c-141">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

