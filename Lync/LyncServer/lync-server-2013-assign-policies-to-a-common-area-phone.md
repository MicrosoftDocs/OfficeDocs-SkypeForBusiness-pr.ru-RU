---
title: 'Lync Server 2013: назначение политик для телефона общего пользования'
description: 'Lync Server 2013: назначение политик для телефона общего пользования.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign policies to a common area phone
ms:assetid: f0554fd1-b237-49b3-9eb4-26f4b91f5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994082(v=OCS.15)
ms:contentKeyID: 51803993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe437ec87ba30eff834239db2b4815adb2d5718c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559825"
---
# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="40841-103">Назначение политик в Lync Server 2013 на телефон общего пользования</span><span class="sxs-lookup"><span data-stu-id="40841-103">Assign policies in Lync Server 2013 to a common area phone</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40841-104">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="40841-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="40841-105">После создания политики для телефонов с общими областями (Дополнительные сведения см. [в статье Создание политики голосовой связи и настройке записей использования PSTN в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)) можно назначить политику для телефона общего пользования с помощью Windows PowerShell и соответствующего командлета **Grant-CS** .</span><span class="sxs-lookup"><span data-stu-id="40841-105">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="40841-106">Эти командлеты можно запускать из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="40841-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="40841-107">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="40841-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="40841-108">Назначение политики для одного телефона общего пользования</span><span class="sxs-lookup"><span data-stu-id="40841-108">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="40841-109">Следующая команда назначает политику голосовой связи на уровне пользователя Редмондвоице на телефон общего пользования с идентификатором 14 "зал ожидания".</span><span class="sxs-lookup"><span data-stu-id="40841-109">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="40841-110">Назначение политики нескольким телефонам общего пользования</span><span class="sxs-lookup"><span data-stu-id="40841-110">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="40841-111">В этом примере политика голосовой связи на уровне пользователя Редмондвоице назначается всем телефонам, настроенным для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="40841-111">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="40841-112">Дополнительные сведения можно найти в разделах справки для [Grant — CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="40841-112">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40841-113">См. также</span><span class="sxs-lookup"><span data-stu-id="40841-113">See Also</span></span>


[<span data-ttu-id="40841-114">Get — CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="40841-114">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

