---
title: 'Lync Server 2013: включение качества обслуживания для устройств, не основанных на Windows'
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
ms.openlocfilehash: 94d7a8fc9a2cea4fc59a9ec404486042225915df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="b309c-102">Включение качества обслуживания в Lync Server 2013 для устройств, не основанных на Windows</span><span class="sxs-lookup"><span data-stu-id="b309c-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b309c-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b309c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b309c-104">При установке Microsoft Lync Server 2013, качество обслуживания (QoS) не будет включено для устройств, используемых в Организации, использующих операционную систему, отличную от Windows.</span><span class="sxs-lookup"><span data-stu-id="b309c-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="b309c-105">Это можно проверить, выполнив следующую команду в командной консоли Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="b309c-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="b309c-106">Если вы не вносили изменений в параметры настройки сервера-посредника, должна быть возвращена следующая информация:</span><span class="sxs-lookup"><span data-stu-id="b309c-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="b309c-107">Если для свойства Енаблекос задано значение false (как в предыдущем выводе), то это означает, что качество службы не включено для компьютеров и устройств, использующих операционную систему, отличную от Windows.</span><span class="sxs-lookup"><span data-stu-id="b309c-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="b309c-108">По умолчанию качество обслуживания включено для устройств Lync Phone Edition; Тем не менее, можно отключить качество обслуживания для Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="b309c-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="b309c-109">Чтобы включить качество службы в глобальной области, выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b309c-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b309c-p103">Предыдущая команда включает качество обслуживания на глобальном уровне. Однако важно заметить, что параметры конфигурации сервера-посредника также можно применить на уровне узла. Если нужно включить качество обслуживания для узла, укажите идентификатор параметров конфигурации при вызове командлета Set-CsMediaConfiguration. Например, следующая команда включает качество обслуживания для узла Redmond:</span><span class="sxs-lookup"><span data-stu-id="b309c-p103">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope. If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration. For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="b309c-p104">Необходимость в использовании качества обслуживания на уровне узла зависит от обстоятельств. Параметры, назначенные на уровне узла, имеют приоритет перед заданными на глобальном уровне. Предположим, что вы включили качество обслуживания на глобальном уровне, но отключили на уровне узла (для узла Redmond). В этом случае качество обслуживания будет отключено для узла Redmond, так как параметры узла имеют приоритет. Чтобы включить качество обслуживания для узла Redmond, вам потребуется воспользоваться параметрами конфигурации сервера-посредника, применяемыми к этому узлу.</span><span class="sxs-lookup"><span data-stu-id="b309c-p104">Do you need to enable QoS at the site scope? That depends. Settings assigned to the site scope take precedence over settings assigned to the global scope. Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence. To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="b309c-118">Если вы хотите одновременно включить QoS для всех параметров конфигурации мультимедиа (независимо от области), выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b309c-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="b309c-119">Можно отключить службу QoS для устройств, использующих операционную систему, отличную от Windows, задав для свойства Енаблекос значение false.</span><span class="sxs-lookup"><span data-stu-id="b309c-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="b309c-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="b309c-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="b309c-121">Таким образом вы можете включить качество обслуживания для отдельных частей сети (например, узла Redmond), не включая его для других частей.</span><span class="sxs-lookup"><span data-stu-id="b309c-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="b309c-122">Службу QoS можно включать и отключать только с помощью Windows PowerShell. Эти параметры недоступны в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b309c-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

