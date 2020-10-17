---
title: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов
description: Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов.
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
ms.openlocfilehash: 3e2ddbcc9c90096cea5fad4cb680f4ea1797ce48
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545615"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a><span data-ttu-id="1e9a8-103">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов</span><span class="sxs-lookup"><span data-stu-id="1e9a8-103">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>

 


<span data-ttu-id="1e9a8-104">Командлетам **Grant-CS** (которые используются для назначения политик пользователям) требуются два идентификатора: удостоверение пользователя (параметр Identity) и идентификатор политики на уровне пользователя (параметр PolicyName).</span><span class="sxs-lookup"><span data-stu-id="1e9a8-104">The **Grant-Cs** cmdlets (used for assigning policies to users) require two identifiers: a user identity (the Identity parameter) and the identity of a per-user policy (the PolicyName parameter).</span></span> <span data-ttu-id="1e9a8-105">Например, чтобы назначить политику голосовой связи RedmondVoicePolicy пользователю Ken Myer, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1e9a8-105">For example, to assign the voice policy, RedmondVoicePolicy, to the user Ken Myer, you use the following command:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="1e9a8-106">При назначении политик пользователям следует иметь в виду две вещи.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-106">There are two things to keep in mind when assigning policies to users.</span></span> <span data-ttu-id="1e9a8-107">Для начала можно назначать только политики на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-107">First, only per-user policies can be assigned.</span></span> <span data-ttu-id="1e9a8-108">Невозможно назначить пользователю глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-108">You cannot assign the global policy to a user.</span></span> <span data-ttu-id="1e9a8-109">Например, эта команда завершится с ошибками:</span><span class="sxs-lookup"><span data-stu-id="1e9a8-109">For example, this command will fail:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

<span data-ttu-id="1e9a8-110">Эта команда завершается с ошибкой, так как не требуется назначать глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-110">This command fails because there is no need to assign the global policy.</span></span> <span data-ttu-id="1e9a8-111">Если вы хотите управлять пользователем с помощью глобальной политики, убедитесь, что вы не назначите этому пользователю политику на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-111">If you want to manage a user by using the global policy, just be sure that you do not assign that user a per-user policy.</span></span> <span data-ttu-id="1e9a8-112">Если пользователю не назначена политика "на пользователя", он будет автоматически управляться с помощью глобальной политики.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-112">If no per-user policy has been assigned to a user, the user will automatically be managed by using the global policy.</span></span>


> [!NOTE]  
> <span data-ttu-id="1e9a8-113">Что делать, если пользователю ранее была назначена политика на уровне пользователя, и вы хотите отменить назначение этой политики и присвоить ей пользователя глобальную политику?</span><span class="sxs-lookup"><span data-stu-id="1e9a8-113">What if the user has previously been assigned a per-user policy, and you want to unassign that policy and have the user managed by the global policy instead?</span></span> <span data-ttu-id="1e9a8-114">В этом случае сначала необходимо использовать следующий синтаксис, который отменяет политику на уровне пользователя, предоставляя этому пользователю политику NULL:</span><span class="sxs-lookup"><span data-stu-id="1e9a8-114">In that case, you’ll first use the following syntax, which unassigns a per-user policy by granting that user a null policy:</span></span><BR><span data-ttu-id="1e9a8-115">Grant-CsVoicePolicy — Identity "Ken Myer" – PolicyName $Null</span><span class="sxs-lookup"><span data-stu-id="1e9a8-115">Grant-CsVoicePolicy –Identity "Ken Myer" –PolicyName $Null</span></span>



<span data-ttu-id="1e9a8-116">Во вторых, помните, что политики на уровне пользователей создаются в области тегов.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-116">Second, keep in mind that per-user policies are created at the tag scope.</span></span> <span data-ttu-id="1e9a8-117">Тем не менее **префикс** тега можно опустить при указании имени политики.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-117">However, you can omit the tag **prefix** when specifying a policy name.</span></span> <span data-ttu-id="1e9a8-118">Эти две команды идентичны:</span><span class="sxs-lookup"><span data-stu-id="1e9a8-118">These two commands are identical:</span></span>

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

<span data-ttu-id="1e9a8-119">Если вы хотите вернуть удостоверения для всех политик на уровне пользователя (или, по крайней мере, для всех политик на уровне пользователя, таких как политики голосовой связи), используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="1e9a8-119">If you would like to return the identities for all your per-user policies (or, at least, all the per-user policies of specified type, such as voice policies), use a command similar to this:</span></span>

    Get-CsVoicePolicy -Filter "tag:*"

<span data-ttu-id="1e9a8-120">Следующие командлеты используют как удостоверение пользователей, так и область тегов.</span><span class="sxs-lookup"><span data-stu-id="1e9a8-120">The following cmdlets make use of both a user Identity and the tag scope:</span></span>

  - <span data-ttu-id="1e9a8-121">[Granting — CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1e9a8-121">[Grant-CsClientPolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1e9a8-122">[Granting — CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1e9a8-122">[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1e9a8-123">[Granting — CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1e9a8-123">[Grant-CsDialPlan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1e9a8-124">[Granting — CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1e9a8-124">[Grant-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1e9a8-125">[Granting — CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1e9a8-125">[Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))</span></span>

  - <span data-ttu-id="1e9a8-126">[Granting — CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1e9a8-126">[Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))</span></span>

## <a name="see-also"></a><span data-ttu-id="1e9a8-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1e9a8-127">See Also</span></span>


[<span data-ttu-id="1e9a8-128">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1e9a8-128">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="1e9a8-129">[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="1e9a8-129">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

