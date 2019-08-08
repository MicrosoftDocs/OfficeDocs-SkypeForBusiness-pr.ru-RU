---
title: Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b274469f16ebb10338504afb2855e1c92774e545
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233101"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="5f8b9-102">Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов</span><span class="sxs-lookup"><span data-stu-id="5f8b9-102">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="5f8b9-103">В Skype для бизнеса Online политики можно настроить как в *глобальной области* , так и в *области тега* (или *отдельно для каждого пользователя*).</span><span class="sxs-lookup"><span data-stu-id="5f8b9-103">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="5f8b9-104">При использовании командлетов **Get-CS** вам не нужно указывать область или удостоверение.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-104">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="5f8b9-105">Если вы вызываете один из этих командлетов без параметров, будут возвращены все соответствующие элементы.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-105">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="5f8b9-106">Например, эта команда возвращает сведения обо всех политиках внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="5f8b9-106">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="5f8b9-107">Если вы хотите ограничить возвращаемые данные, необходимо включить параметр Identity или параметр фильтра.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-107">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="5f8b9-108">Например, чтобы возвратить только глобальную политику, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5f8b9-108">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="5f8b9-109">Для возврата политики для пользователей с удостоверением "Редмондакцессполици" используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5f8b9-109">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="5f8b9-110">При обращении к политике на уровне пользователя <STRONG>префикс</STRONG> тега является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-110">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="5f8b9-111">Этот синтаксис, включающий префикс, также является допустимым:</span><span class="sxs-lookup"><span data-stu-id="5f8b9-111">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="5f8b9-112">Get-Ксекстерналакцессполици-Identity "тег: Редмондакцессполици"</span><span class="sxs-lookup"><span data-stu-id="5f8b9-112">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="5f8b9-113">Чтобы получить все политики за исключением глобальных политик (то есть всех политик для пользователей), используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5f8b9-113">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="5f8b9-114">Следующие командлеты работают как в глобальной области, так и в области "на пользователя" (тег).</span><span class="sxs-lookup"><span data-stu-id="5f8b9-114">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="5f8b9-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-115">[Get-CsClientPolicy](https://technet.microsoft.com/en-us/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5f8b9-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-116">[Get-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5f8b9-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-117">[Get-CsDialPlan](https://technet.microsoft.com/en-us/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5f8b9-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-118">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5f8b9-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-119">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5f8b9-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-120">[Get-CsPresencePolicy](https://technet.microsoft.com/en-us/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="5f8b9-121">[Get-Ксвоицеполици](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-121">[Get-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="5f8b9-122">Несмотря на имя, абонентские группы будут функционально говорить, что политики.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-122">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="5f8b9-123">Термин "абонентская <EM>Группа</EM> " используется вместо (например, с политикой набора номера) для сохранения терминологии, используемой в предыдущих версиях Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f8b9-123">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="5f8b9-124">См. также</span><span class="sxs-lookup"><span data-stu-id="5f8b9-124">See Also</span></span>


[<span data-ttu-id="5f8b9-125">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="5f8b9-125">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="5f8b9-126">[Командлеты Lync Online](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="5f8b9-126">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

