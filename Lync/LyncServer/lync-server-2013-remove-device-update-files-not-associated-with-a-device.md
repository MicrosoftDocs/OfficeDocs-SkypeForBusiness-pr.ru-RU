---
title: 'Lync Server 2013: удаление файлов обновлений устройств, не связанных с устройством'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ea26cd20826ed099e27c7287c53cc7ca79bef9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="721eb-102">Удаление файлов обновления устройства, не связанных с устройством в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="721eb-102">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="721eb-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="721eb-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="721eb-104">Каждый раз, когда новые обновления устройства загружаются в систему, создается соответствующее правило обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="721eb-104">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="721eb-105">По умолчанию новые правила обновления устройства назначаются в состояние ожидания.</span><span class="sxs-lookup"><span data-stu-id="721eb-105">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="721eb-106">Это означает, что правила можно загрузить и установить на тестовые устройства, но не на производственные устройства, что позволит вам тестировать обновления перед их предоставлением пользователям.</span><span class="sxs-lookup"><span data-stu-id="721eb-106">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="721eb-107">На основании тестов вы принимаете и разворачиваете или отклоняете и удаляете обновление.</span><span class="sxs-lookup"><span data-stu-id="721eb-107">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="721eb-108">Когда вы отклоняете обновление, обновление устройства не связано с его правилом обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="721eb-108">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="721eb-109">Файлы обновления устройства, которые больше не связаны с устройством, можно удалить с помощью Windows PowerShell и командлета **clear-ксдевицеупдатефиле** .</span><span class="sxs-lookup"><span data-stu-id="721eb-109">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="721eb-110">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="721eb-110">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="721eb-111">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="721eb-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="721eb-112">Например, следующая команда удаляет все правила обновления устройства на веб-сервере atl-cs-001.litwareinc.com, которые больше не связаны с устройством.</span><span class="sxs-lookup"><span data-stu-id="721eb-112">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="721eb-113">Дополнительные сведения можно найти в разделе справки по командлету [clear-ксдевицеупдатефиле](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .</span><span class="sxs-lookup"><span data-stu-id="721eb-113">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

