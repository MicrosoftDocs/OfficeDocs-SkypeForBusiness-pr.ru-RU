---
title: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24c197934705a86d91e0492949aa2a9e6484f903
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727569"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="31c56-102">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов</span><span class="sxs-lookup"><span data-stu-id="31c56-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="31c56-103">Командлеты **Grant-CS** (используемые для назначения политик пользователям) необходимы два идентификатора: удостоверение пользователя (параметр Identity) и удостоверение политики для пользователя (параметр полицинаме).</span><span class="sxs-lookup"><span data-stu-id="31c56-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="31c56-104">Например, чтобы назначить политику голосовой связи, Редмондвоицеполици, пользователю Кен мер, вы можете использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="31c56-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="31c56-105">При назначении политик пользователям следует помнить о двух вещах.</span><span class="sxs-lookup"><span data-stu-id="31c56-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="31c56-106">Во-первых, можно назначить только политики для пользователей.</span><span class="sxs-lookup"><span data-stu-id="31c56-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="31c56-107">Пользователю нельзя назначить глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="31c56-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="31c56-108">Например, эта команда завершится сбоем:</span><span class="sxs-lookup"><span data-stu-id="31c56-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="31c56-109">Эта команда завершается сбоем, так как не требуется назначать глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="31c56-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="31c56-110">Если вы хотите управлять пользователем с помощью глобальной политики, просто убедитесь в том, что вы не назначаете этот пользователь политике для пользователей.</span><span class="sxs-lookup"><span data-stu-id="31c56-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="31c56-111">Если пользователю назначена политика "на пользователя", пользователь будет автоматически управлять с помощью глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="31c56-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="31c56-112">Что делать, если пользователю ранее был назначен параметр политики для пользователя, и вы хотите отменить назначение этой политики, а вместо этого использовать ее с помощью глобальной политики?</span><span class="sxs-lookup"><span data-stu-id="31c56-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="31c56-113">В этом случае сначала используется следующий синтаксис, который отменяет политику для пользователя, предоставляя пользователю политику NULL:</span><span class="sxs-lookup"><span data-stu-id="31c56-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="31c56-114">Grant-Ксвоицеполици – Identity "Кен мер" – Полицинаме $Null</span><span class="sxs-lookup"><span data-stu-id="31c56-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="31c56-115">Во-вторых, имейте в виду, что политики для каждого пользователя создаются в области тега.</span><span class="sxs-lookup"><span data-stu-id="31c56-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="31c56-116">Тем не менее **префикс** тега можно опустить при указании имени политики.</span><span class="sxs-lookup"><span data-stu-id="31c56-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="31c56-117">Эти две команды идентичны:</span><span class="sxs-lookup"><span data-stu-id="31c56-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="31c56-118">Если вы хотите вернуть удостоверения для всех политик пользователей (или, по крайней мере, все политики для определенного типа, например политики голосовой связи), используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="31c56-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="31c56-119">Следующие командлеты используют как удостоверение пользователя, так и область тегов.</span><span class="sxs-lookup"><span data-stu-id="31c56-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="31c56-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="31c56-120">[Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="31c56-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="31c56-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="31c56-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="31c56-122">[Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="31c56-123">[Grant-Ксекстерналакцессполици](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="31c56-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="31c56-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="31c56-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="31c56-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="31c56-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="31c56-126">См. также</span><span class="sxs-lookup"><span data-stu-id="31c56-126">See Also</span></span>


[<span data-ttu-id="31c56-127">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="31c56-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="31c56-128">[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="31c56-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

