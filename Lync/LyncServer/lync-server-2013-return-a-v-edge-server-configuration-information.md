---
title: 'Lync Server 2013: возврат сведений о конфигурации пограничного сервера/V'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Return A/V Edge Server configuration information
ms:assetid: b041f5a4-2387-4075-846c-ec4f99640903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721850(v=OCS.15)
ms:contentKeyID: 49733783
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15096099184525890328dbe1c89d891487b46d87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="return-av-edge-server-configuration-information-in-lync-server-2013"></a><span data-ttu-id="4453b-102">Возврат сведений о конфигурации пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4453b-102">Return A/V Edge Server configuration information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4453b-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4453b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4453b-104">Служба "A/V Edge" обеспечивает способ предоставления внутренних пользователей (пользователей, вошедших в вашу организационную сеть) для совместного использования звуковых и видеофайлов с внешними пользователями (пользователям, которые не вошли в свою организационную сеть).</span><span class="sxs-lookup"><span data-stu-id="4453b-104">The A/V Edge service provide a way for your internal users (users who are logged on to your organizational network) to share audio and video with external users (users who are not logged on to your organizational network).</span></span> <span data-ttu-id="4453b-105">Служба EDGE (A/V) главным образом управляется с помощью параметров конфигурации краев/V, параметров, которые можно настроить в области сайта или в области службы (то есть можно настроить для отдельного пограничного сервера A/V).</span><span class="sxs-lookup"><span data-stu-id="4453b-105">The A/V Edge service is primarily managed by using A/V Edge configuration settings, setting that can be configured at the site scope or at the service scope (that is, can be configured for an individual A/V Edge server).</span></span>

<span data-ttu-id="4453b-106">Чтобы получить сведения о параметрах конфигурации краев, используемых в вашей организации, необходимо использовать Windows PowerShell и командлет Get-Ксаведжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="4453b-106">To return information about the A/V Edge configuration settings in use in your organization, you must use Windows PowerShell and the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4453b-107">Дополнительные сведения можно найти в разделе справки по командлету [Get-ксаведжеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4453b-107">For more information, see the help topic for the [Get-CsAVEdgeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsAVEdgeConfiguration) cmdlet.</span></span>

<span data-ttu-id="4453b-108">Данные, возвращаемые командлетом Get-Ксаведжеконфигуратион, будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="4453b-108">Information returned from the Get-CsAVEdgeConfiguration cmdlet will look similar to this:</span></span>

    Identity              : Global
    MaxTokenLifetime      : 08:00:00
    MaxBandwidthPerUserKb : 10000
    MaxBandwidthPerPortKb : 3000

<div>

## <a name="to-return-information-for-all-your-av-edge-configuration-settings"></a><span data-ttu-id="4453b-109">Получение сведений о всех параметрах конфигурации Edge</span><span class="sxs-lookup"><span data-stu-id="4453b-109">To return information for all your A/V Edge configuration settings</span></span>

  - <span data-ttu-id="4453b-110">Следующая команда возвращает сведения обо всех параметрах, которые используются в вашей организации в качестве параметров конфигурации Edge для/V.</span><span class="sxs-lookup"><span data-stu-id="4453b-110">The following command returns information about all the A/V Edge configuration settings currently in use in your organization:</span></span>
    
        Get-CsAVEdgeConfiguration

</div>

<div>

## <a name="to-return-information-for-site-scoped-av-edge-configuration-settings"></a><span data-ttu-id="4453b-111">Возврат сведений о параметрах конфигурации сайта в качестве границы области</span><span class="sxs-lookup"><span data-stu-id="4453b-111">To return information for site-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="4453b-112">Чтобы получить сведения о конкретной коллекции параметров конфигурации краев/V, укажите удостоверение этой коллекции при запуске командлета Get-Ксаведжеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="4453b-112">To return information about a specific collection of A/V Edge configuration settings, specify the Identity of that collection when running the Get-CsAVEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="4453b-113">Например, эта команда возвращает сведения только о параметрах, примененных к сайту Redmond.</span><span class="sxs-lookup"><span data-stu-id="4453b-113">For example, this command returns information only for the settings applied to the Redmond site:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-return-information-for-service-scoped-av-edge-configuration-settings"></a><span data-ttu-id="4453b-114">Возврат сведений о параметрах конфигурации краев, заданных в пределах службы</span><span class="sxs-lookup"><span data-stu-id="4453b-114">To return information for service-scoped A/V Edge configuration settings</span></span>

  - <span data-ttu-id="4453b-115">Эта команда возвращает данные только для параметров, примененных к конкретному пограничному серверу/V.</span><span class="sxs-lookup"><span data-stu-id="4453b-115">And this command returns information only for settings applied the a specific A/V Edge server:</span></span>
    
        Get-CsAVEdgeConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4453b-116">См. также</span><span class="sxs-lookup"><span data-stu-id="4453b-116">See Also</span></span>


[<span data-ttu-id="4453b-117">Создание и изменение коллекции параметров конфигурации пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4453b-117">Create or modify a collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-a-v-edge-server-configuration-settings.md)  
[<span data-ttu-id="4453b-118">Удаление существующей коллекции параметров конфигурации пограничного сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4453b-118">Delete an existing collection of A/V Edge Server configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-a-v-edge-server-configuration-settings.md)  


[<span data-ttu-id="4453b-119">Пограничные серверы для аудио-и видеоустройств (A/V) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4453b-119">Audio/Video (A/V) Edge Servers in Lync Server 2013</span></span>](lync-server-2013-audio-video-a-v-edge-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

