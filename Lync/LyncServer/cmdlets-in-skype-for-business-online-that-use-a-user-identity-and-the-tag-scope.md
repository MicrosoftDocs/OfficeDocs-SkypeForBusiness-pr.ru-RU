---
title: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: 9adf86a6ec6d2bd859411005dcc67b0dcbe09c7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755121"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="e90a0-102">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов</span><span class="sxs-lookup"><span data-stu-id="e90a0-102">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="e90a0-103">Командлетам **Grant-CS** (которые используются для назначения политик пользователям) требуются два идентификатора: удостоверение пользователя (параметр Identity) и идентификатор политики на уровне пользователя (параметр PolicyName).</span><span class="sxs-lookup"><span data-stu-id="e90a0-103">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="e90a0-104">Например, чтобы назначить политику голосовой связи RedmondVoicePolicy пользователю Ken Myer, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e90a0-104">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="e90a0-105">При назначении политик пользователям следует иметь в виду две вещи.</span><span class="sxs-lookup"><span data-stu-id="e90a0-105">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="e90a0-106">Для начала можно назначать только политики на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="e90a0-106">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="e90a0-107">Невозможно назначить пользователю глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="e90a0-107">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="e90a0-108">Например, эта команда завершится с ошибками:</span><span class="sxs-lookup"><span data-stu-id="e90a0-108">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="e90a0-109">Эта команда завершается с ошибкой, так как не требуется назначать глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="e90a0-109">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="e90a0-110">Если вы хотите управлять пользователем с помощью глобальной политики, убедитесь, что вы не назначите этому пользователю политику на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="e90a0-110">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="e90a0-111">Если пользователю не назначена политика "на пользователя", он будет автоматически управляться с помощью глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="e90a0-111">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="e90a0-112">Что делать, если пользователю ранее была назначена политика на уровне пользователя, и вы хотите отменить назначение этой политики и присвоить ей пользователя глобальную политику?</span><span class="sxs-lookup"><span data-stu-id="e90a0-112">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="e90a0-113">В этом случае сначала необходимо использовать следующий синтаксис, который отменяет политику на уровне пользователя, предоставляя этому пользователю политику NULL:</span><span class="sxs-lookup"><span data-stu-id="e90a0-113">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="e90a0-114">Grant-CsVoicePolicy – Identity "Кен Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="e90a0-114">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="e90a0-115">Во вторых, помните, что политики на уровне пользователей создаются в области тегов.</span><span class="sxs-lookup"><span data-stu-id="e90a0-115">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="e90a0-116">Тем не менее **префикс** тега можно опустить при указании имени политики.</span><span class="sxs-lookup"><span data-stu-id="e90a0-116">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="e90a0-117">Эти две команды идентичны:</span><span class="sxs-lookup"><span data-stu-id="e90a0-117">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="e90a0-118">Если вы хотите вернуть удостоверения для всех политик на уровне пользователя (или, по крайней мере, для всех политик на уровне пользователя, таких как политики голосовой связи), используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="e90a0-118">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="e90a0-119">Следующие командлеты используют как удостоверение пользователей, так и область тегов.</span><span class="sxs-lookup"><span data-stu-id="e90a0-119">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="e90a0-120">[Granting — CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e90a0-120">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e90a0-121">[Granting — CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e90a0-121">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e90a0-122">[Granting — CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e90a0-122">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e90a0-123">[Granting — CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e90a0-123">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e90a0-124">[Granting — CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e90a0-124">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="e90a0-125">[Granting — CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e90a0-125">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="e90a0-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e90a0-126">See Also</span></span>


[<span data-ttu-id="e90a0-127">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e90a0-127">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="e90a0-128">[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="e90a0-128">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

