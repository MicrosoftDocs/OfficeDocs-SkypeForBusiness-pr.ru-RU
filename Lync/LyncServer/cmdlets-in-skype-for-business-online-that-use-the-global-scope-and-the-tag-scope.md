---
title: Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов
description: Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the global scope and the tag scope
ms:assetid: 1e2bc055-8a72-425e-967b-e253add7018c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362774(v=OCS.15)
ms:contentKeyID: 56558824
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba89ebe7322159027c5de765117afd366cb3dc23
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545625"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope"></a><span data-ttu-id="8e4e5-103">Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов</span><span class="sxs-lookup"><span data-stu-id="8e4e5-103">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>

 


<span data-ttu-id="8e4e5-104">В Skype для бизнеса Online политики можно настроить на *глобальном* уровне или в *области тегов* (или *на уровне отдельных пользователей*).</span><span class="sxs-lookup"><span data-stu-id="8e4e5-104">In Skype for Business Online, policies can be configured at either the *global scope* or at the *tag scope* (or *per-user scope*).</span></span> <span data-ttu-id="8e4e5-105">При использовании командлетов **Get – CS** нет необходимости указывать область или идентификатор.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-105">When using the **Get-Cs** cmdlets, you do not have to specify a scope or identity.</span></span> <span data-ttu-id="8e4e5-106">Если вы вызываете один из этих командлетов без параметров, будут возвращены все соответствующие элементы.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-106">If you call one of these cmdlets without any parameters, then all the relevant items will be returned.</span></span> <span data-ttu-id="8e4e5-107">Например, эта команда возвращает сведения обо всех политиках внешнего доступа:</span><span class="sxs-lookup"><span data-stu-id="8e4e5-107">For example, this command returns information about all your external access policies:</span></span>

    Get-CsExternalAccessPolicy

<span data-ttu-id="8e4e5-108">Если вы хотите ограничить возвращаемые данные, необходимо включить только параметр Identity или параметр Filter.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-108">You need to include only the Identity parameter or the Filter parameter if you want to limit the returned data.</span></span> <span data-ttu-id="8e4e5-109">Например, чтобы возвратить только глобальную политику, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e4e5-109">For example, to return only the global policy, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "global"

<span data-ttu-id="8e4e5-110">Чтобы вернуть политику на уровне пользователя с удостоверением "Редмондакцессполици", используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e4e5-110">To return a per-user policy that has the Identity “RedmondAccessPolicy”, use this command:</span></span>

    Get-CsExternalAccessPolicy -Identity "RedmondAccessPolicy"


> [!NOTE]  
> <span data-ttu-id="8e4e5-111">При ссылке на политику на уровне пользователя <STRONG>префикс</STRONG> тега является необязательным.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-111">When referencing a per-user policy, the tag <STRONG>prefix</STRONG> is optional.</span></span> <span data-ttu-id="8e4e5-112">Этот синтаксис, который включает префикс, также является допустимым:</span><span class="sxs-lookup"><span data-stu-id="8e4e5-112">This syntax, which includes the prefix, is also valid:</span></span><BR><span data-ttu-id="8e4e5-113">Get-CsExternalAccessPolicy — идентификатор "Tag: Редмондакцессполици"</span><span class="sxs-lookup"><span data-stu-id="8e4e5-113">Get-CsExternalAccessPolicy –Identity "tag:RedmondAccessPolicy"</span></span>



<span data-ttu-id="8e4e5-114">Чтобы получить все политики, кроме глобальных (то есть всех политик для отдельных пользователей), используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8e4e5-114">To return all policies except the global policies (that is, all the per-user policies), use this command:</span></span>

    Get-CsExternalAccessPolicy -Filter "tag:*"

<span data-ttu-id="8e4e5-115">Следующие командлеты работают как с глобальной областью, так и с областью "на пользователя" (тег):</span><span class="sxs-lookup"><span data-stu-id="8e4e5-115">The following cmdlets operate against both the global scope and the per-user (tag) scope:</span></span>

  - <span data-ttu-id="8e4e5-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-116">[Get-CsClientPolicy](https://technet.microsoft.com/library/gg398830\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8e4e5-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-117">[Get-CsConferencingPolicy](https://technet.microsoft.com/library/gg398293\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8e4e5-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-118">[Get-CsDialPlan](https://technet.microsoft.com/library/gg413043\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8e4e5-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-119">[Get-CsExternalAccessPolicy](https://technet.microsoft.com/library/gg425805\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8e4e5-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-120">[Get-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg398348\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8e4e5-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-121">[Get-CsPresencePolicy](https://technet.microsoft.com/library/gg398463\(v=ocs.15\))</span></span>

  - <span data-ttu-id="8e4e5-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-122">[Get-CsVoicePolicy](https://technet.microsoft.com/library/gg398101\(v=ocs.15\))</span></span>


> [!NOTE]  
> <span data-ttu-id="8e4e5-123">Несмотря на имя, абонентские группы, функционально говоря, политики.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-123">Despite the name, dial plans are, functionally speaking, policies.</span></span> <span data-ttu-id="8e4e5-124">Для сохранения терминологии, используемой с предыдущими версиями Lync Server, используется термин " <EM>абонентская абонентская</EM> политика", а не, например, политика набора номера.</span><span class="sxs-lookup"><span data-stu-id="8e4e5-124">The term <EM>dial plan</EM> is used instead of, for example, dialing policy, in order to preserve the terminology used with previous versions of Lync Server.</span></span>



## <a name="see-also"></a><span data-ttu-id="8e4e5-125">См. также</span><span class="sxs-lookup"><span data-stu-id="8e4e5-125">See Also</span></span>


[<span data-ttu-id="8e4e5-126">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8e4e5-126">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="8e4e5-127">[Командлеты Skype для бизнеса Online](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8e4e5-127">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

