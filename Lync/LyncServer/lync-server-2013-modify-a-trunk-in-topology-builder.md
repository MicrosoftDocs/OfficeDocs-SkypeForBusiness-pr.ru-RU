---
title: 'Lync Server 2013: изменение магистрали в построителе топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a trunk in Topology Builder
ms:assetid: 81055a82-c6f8-47b2-9779-223b1d842f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688110(v=OCS.15)
ms:contentKeyID: 49733709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1c603aa24a0d31ea87178f740f824ae77f20f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-trunk-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="f7174-102">Изменение магистрали в построителе топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7174-102">Modify a trunk in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7174-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f7174-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f7174-104">Выполните указанные ниже действия, чтобы изменить дополнительный IP-адрес и отказаться от использования идентификатора межсетевого связи.</span><span class="sxs-lookup"><span data-stu-id="f7174-104">Follow these steps to modify the alternate media IP address and alternate bypass identifier of a trunk.</span></span>

<div>

## <a name="to-modify-the-alternate-media-ip-address-of-a-trunk"></a><span data-ttu-id="f7174-105">Изменение альтернативного IP-адреса носителя для магистрали</span><span class="sxs-lookup"><span data-stu-id="f7174-105">To Modify the Alternate Media IP Address of a Trunk</span></span>

1.  <span data-ttu-id="f7174-106">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f7174-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f7174-107">Запустите командлет Set-Кспстнгатевай и измените поле Алтернатебипассид в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f7174-107">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -RepresentativeMediaIP <IP address>

</div>

<div>

## <a name="to-modify-the-alternate-bypassid-of-a-trunk"></a><span data-ttu-id="f7174-108">Изменение альтернативных Бипассид на магистральной магистрали</span><span class="sxs-lookup"><span data-stu-id="f7174-108">To Modify the Alternate BypassID of a Trunk</span></span>

1.  <span data-ttu-id="f7174-109">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f7174-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f7174-110">Запустите командлет Set-Кспстнгатевай и измените поле Алтернатебипассид в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f7174-110">Run the Set-CsPstnGateway cmdlet and modify the AlternateBypassId field in the Lync Server Management Shell.</span></span>
    
        Set-CsPstnGateway -Identity "PstnGateway:<peer FQDN> -AlternateBypassID <identifier>

</div>

</div>

<span> </span>

</div>

</div>

</div>

