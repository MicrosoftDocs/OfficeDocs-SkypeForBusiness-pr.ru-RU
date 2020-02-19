---
title: 'Lync Server 2013: удаление файлов обновления устройств, не связанных с устройством'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove Device Update files not associated with a device
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994084(v=OCS.15)
ms:contentKeyID: 51803996
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7089e3f055d89fb07215d119ea287471fd211de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-device-update-files-not-associated-with-a-device-in-lync-server-2013"></a><span data-ttu-id="d6b34-102">Удаление файлов обновления устройств, не связанных с устройством, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6b34-102">Remove Device Update files not associated with a device in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6b34-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d6b34-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d6b34-104">При каждом поступлении новых обновлений устройства в систему создается соответствующее правило обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="d6b34-104">Each time new device updates are uploaded to the system, a corresponding device update rule is created.</span></span> <span data-ttu-id="d6b34-105">По умолчанию эти новые правила обновления устройств назначены состоянию ожидания.</span><span class="sxs-lookup"><span data-stu-id="d6b34-105">By default, these new device update rules are assigned to the Pending state.</span></span> <span data-ttu-id="d6b34-106">Это означает, что правила можно загружать и устанавливать на тестовые устройства, но не на рабочих устройствах, что позволяет протестировать обновления, прежде чем сделать их доступными для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d6b34-106">This means that the rules can be downloaded and installed on test devices, but not on production devices, which enables you to test the updates before making them available to users.</span></span> <span data-ttu-id="d6b34-107">На основе тестов вы принимаете и развертываете или отклоняете и удаляете обновление.</span><span class="sxs-lookup"><span data-stu-id="d6b34-107">Based on the tests, you either accept and deploy or reject and delete the update.</span></span> <span data-ttu-id="d6b34-108">Когда вы отклоняете обновление, обновление устройства не связано с правилом обновления устройства.</span><span class="sxs-lookup"><span data-stu-id="d6b34-108">When you reject an update, the device update is disassociated from its device update rule.</span></span>

<div>


<span data-ttu-id="d6b34-109">Файлы обновления устройств, которые больше не связаны с устройством, можно удалить с помощью Windows PowerShell и командлета **clear – ксдевицеупдатефиле** .</span><span class="sxs-lookup"><span data-stu-id="d6b34-109">Device update files that are no longer associated with a device can be removed by using Windows PowerShell and the **Clear-CsDeviceUpdateFile** cmdlet.</span></span> <span data-ttu-id="d6b34-110">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6b34-110">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6b34-111">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="d6b34-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


  - <span data-ttu-id="d6b34-112">Например, следующая команда удаляет все правила обновления устройств на веб-сервере atl-cs-001.litwareinc.com, которые больше не связаны с устройством:</span><span class="sxs-lookup"><span data-stu-id="d6b34-112">For example, the following command removes any device update rules on the Web server atl-cs-001.litwareinc.com that are no longer associated with a device:</span></span>
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

</div>

<span data-ttu-id="d6b34-113">Дополнительные сведения см. в разделе справки для командлета [clear – ксдевицеупдатефиле](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) .</span><span class="sxs-lookup"><span data-stu-id="d6b34-113">For details, see the Help topic for the [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

