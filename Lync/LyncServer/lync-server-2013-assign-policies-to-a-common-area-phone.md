---
title: 'Lync Server 2013: назначение политик для телефонного телефона с общим регионом'
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
ms.openlocfilehash: e19e2fccabe4759f8cf4cf5eb55ade7e68e2b560
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-policies-in-lync-server-2013-to-a-common-area-phone"></a><span data-ttu-id="7fd68-102">Назначение политик в Lync Server 2013 на стандартном телефоне</span><span class="sxs-lookup"><span data-stu-id="7fd68-102">Assign policies in Lync Server 2013 to a common area phone</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fd68-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="7fd68-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="7fd68-104">После создания политики для обычных телефонов (Дополнительные сведения см. [в разделе Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)) можно назначить политику для обычного телефона с помощью Windows PowerShell и соответствующего командлета **Grant-CS** .</span><span class="sxs-lookup"><span data-stu-id="7fd68-104">After you create your policy for common area phones (for details, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)), you can assign the policy to a common area phone by using Windows PowerShell and the appropriate **Grant-Cs** cmdlet.</span></span> <span data-ttu-id="7fd68-105">Эти командлеты можно запускать либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fd68-105">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7fd68-106">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7fd68-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="assigning-a-policy-to-a-single-common-area-phone"></a><span data-ttu-id="7fd68-107">Назначение политики единому телефону с общим регионом</span><span class="sxs-lookup"><span data-stu-id="7fd68-107">Assigning a Policy to a Single Common Area Phone</span></span>

  - <span data-ttu-id="7fd68-108">Следующая команда назначает политику голосовой связи "на пользователя", Редмондвоице на общем телефоне с телефонным подключением, у которого установлен номер 14 зал здания.</span><span class="sxs-lookup"><span data-stu-id="7fd68-108">The following command assigns the per-user voice policy RedmondVoice to the common area phone that has the Identity Building 14 Lobby.</span></span>
    
        Grant-CsVoicePolicy -Identity "Building 14 Lobby" -PolicyName "RedmondVoicePolicy"

</div>

<div>

## <a name="assigning-a-policy-to-multiple-common-area-phones"></a><span data-ttu-id="7fd68-109">Назначение политики для нескольких распространенных телефонных областей</span><span class="sxs-lookup"><span data-stu-id="7fd68-109">Assigning a Policy to Multiple Common Area Phones</span></span>

  - <span data-ttu-id="7fd68-110">В этом примере политика голосовой связи "на пользователя" Редмондвоице назначается всем телефонам с общим диапазоном, настроенным для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="7fd68-110">In this example, the per-user voice policy RedmondVoice is assigned to all the common area phones configured for use in the organization.</span></span>
    
        Get-CsCommonAreaPhone | Grant-CsVoicePolicy  -PolicyName "RedmondVoicePolicy"

</div>

<span data-ttu-id="7fd68-111">Подробности можно найти в статьях справки для [Grant-ксвоицеполици](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="7fd68-111">For details, see the Help topics for the [Grant-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsVoicePolicy).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7fd68-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7fd68-112">See Also</span></span>


[<span data-ttu-id="7fd68-113">Get-CsCommonAreaPhone</span><span class="sxs-lookup"><span data-stu-id="7fd68-113">Get-CsCommonAreaPhone</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCommonAreaPhone)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

