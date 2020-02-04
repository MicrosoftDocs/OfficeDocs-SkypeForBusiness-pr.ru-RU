---
title: 'Lync Server 2013: Включение QoS для устройств, которые не основаны на Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7574169c5a8c9cb660a81b384711a4937056b37
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="afabf-102">Включение QoS в Lync Server 2013 для устройств, которые не основаны на Windows</span><span class="sxs-lookup"><span data-stu-id="afabf-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afabf-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="afabf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="afabf-104">При установке Microsoft Lync Server 2013, качество обслуживания (QoS) не будет разрешено для устройств, используемых в вашей организации, которые используют операционную систему, отличную от Windows.</span><span class="sxs-lookup"><span data-stu-id="afabf-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="afabf-105">Это можно проверить, запустив в командной консоли Lync Server 2013 следующую команду:</span><span class="sxs-lookup"><span data-stu-id="afabf-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="afabf-106">Если вы не внесли никаких изменений в параметры конфигурации мультимедиа, вы должны получить информацию примерно так:</span><span class="sxs-lookup"><span data-stu-id="afabf-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="afabf-107">Если для свойства Енаблекос задано значение false (как в предыдущем выводе), это означает, что качество обслуживания не разрешено для компьютеров и устройств, использующих операционную систему, отличную от Windows.</span><span class="sxs-lookup"><span data-stu-id="afabf-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="afabf-108">Служба QoS включена по умолчанию для устройств Lync Phone Edition; Однако можно отключить качество обслуживания для Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="afabf-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="afabf-109">Чтобы включить качество обслуживания в глобальной области, выполните в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="afabf-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="afabf-110">Предыдущая команда включает QoS в глобальной области; Однако важно отметить, что параметры конфигурации мультимедиа также можно применить к области сайта.</span><span class="sxs-lookup"><span data-stu-id="afabf-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="afabf-111">Если необходимо включить качество обслуживания для сайта, необходимо включить удостоверение параметров конфигурации при вызове Set-Ксмедиаконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="afabf-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="afabf-112">Например, эта команда включает QoS для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="afabf-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="afabf-113">Нужно ли включить качество обслуживания в области сайта?</span><span class="sxs-lookup"><span data-stu-id="afabf-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="afabf-114">Смотря как.</span><span class="sxs-lookup"><span data-stu-id="afabf-114">That depends.</span></span> <span data-ttu-id="afabf-115">Параметры, назначенные области сайта, имеют приоритет над параметрами, назначенными глобальной области.</span><span class="sxs-lookup"><span data-stu-id="afabf-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="afabf-116">Предположим, что в глобальной области включена служба QoS, но она отключена в области сайта (для сайта Redmond). В этом случае качество обслуживания для сайта Redmond будет отключено. Это связано с тем, что параметры сайта имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="afabf-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="afabf-117">Чтобы включить QoS для сайта Redmond, вам понадобится использовать параметры конфигурации мультимедиа, примененные к этому сайту.</span><span class="sxs-lookup"><span data-stu-id="afabf-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="afabf-118">Если вы хотите одновременно включить QoS для всех параметров конфигурации мультимедиа (независимо от области), выполните эту команду в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="afabf-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="afabf-119">Вы можете отключить QoS для устройств, использующих операционную систему, отличную от Windows, установив для свойства Енаблекос значение false.</span><span class="sxs-lookup"><span data-stu-id="afabf-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="afabf-120">Например:</span><span class="sxs-lookup"><span data-stu-id="afabf-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="afabf-121">Это позволяет реализовать качество обслуживания для некоторых частей сети (например, на сайте Redmond), не отключая качество обслуживания для других частей сети.</span><span class="sxs-lookup"><span data-stu-id="afabf-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="afabf-122">Вы можете включить и отключить QoS только с помощью Windows PowerShell. Эти параметры недоступны на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afabf-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

