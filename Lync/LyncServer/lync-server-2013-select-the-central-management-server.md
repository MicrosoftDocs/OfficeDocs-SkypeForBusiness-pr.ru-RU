---
title: 'Lync Server 2013: выбор центрального сервера управления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef3cff58600697f64b64860f37a7daab8ebfc8f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510426"
---
# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="873f4-102">Выбор центрального сервера управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="873f4-102">Select the Central Management Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="873f4-103">_**Последнее изменение темы:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="873f4-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="873f4-104">Прежде чем вы сможете определять и настраивать топологию, необходимо сначала определить расположение для установки центрального сервера управления.</span><span class="sxs-lookup"><span data-stu-id="873f4-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="873f4-105">Это вступит в силу только после публикации топологии в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="873f4-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="873f4-106">Чтобы задать центральный сервер управления до создания и публикации топологии, выполните командлет <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="873f4-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="873f4-107">Выбор центрального сервера управления</span><span class="sxs-lookup"><span data-stu-id="873f4-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="873f4-108">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="873f4-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="873f4-109">Щелкните правой кнопкой мыши узел Lync Server 2013 и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="873f4-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="873f4-110">В области "Центральный сервер управления" выберите сервер переднего плана, на котором необходимо установить центральный сервер управления, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="873f4-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

