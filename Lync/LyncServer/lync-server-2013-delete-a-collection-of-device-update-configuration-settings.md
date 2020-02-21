---
title: 'Lync Server 2013: Удаление коллекции параметров конфигурации обновления устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28b12835916577e2900c5bd740a599aa229e250d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190812"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4b3e7-102">Удаление коллекции параметров конфигурации обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b3e7-102">Delete a collection of Device Update configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b3e7-103">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="4b3e7-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="4b3e7-104">Параметры конфигурации обновления устройств также можно удалить с помощью Windows PowerShell и командлета **Remove – CsdeviceUpdateConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4b3e7-104">Device update configuration settings can also be deleted by using Windows PowerShell and the **Remove-CsdeviceUpdateConfiguration** cmdlet.</span></span> <span data-ttu-id="4b3e7-105">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4b3e7-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4b3e7-106">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="4b3e7-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a><span data-ttu-id="4b3e7-107">Удаление определенной коллекции параметров конфигурации обновления устройств</span><span class="sxs-lookup"><span data-stu-id="4b3e7-107">To remove a specific collection of device update configuration settings</span></span>

  - <span data-ttu-id="4b3e7-108">Эта команда удаляет параметры конфигурации обновления устройств, примененные к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="4b3e7-108">This command deletes the device update configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="4b3e7-109">Удаление всех параметров конфигурации обновления устройств, примененных к области сайта</span><span class="sxs-lookup"><span data-stu-id="4b3e7-109">To remove all the device update configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="4b3e7-110">Эта команда удаляет все параметры конфигурации обновления устройств, примененные к области сайта:</span><span class="sxs-lookup"><span data-stu-id="4b3e7-110">This command deletes all the device update configuration settings applied to the site scope:</span></span>
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a><span data-ttu-id="4b3e7-111">Удаление параметров конфигурации обновления устройств на основе значения свойства Логклеанупинтервал</span><span class="sxs-lookup"><span data-stu-id="4b3e7-111">To remove device update configuration settings based on the value of the LogCleanUpInterval property</span></span>

  - <span data-ttu-id="4b3e7-112">Следующая команда удаляет все параметры конфигурации обновления устройств, для которых интервал очистки журнала превышает 10 дней (10,00:00:00):</span><span class="sxs-lookup"><span data-stu-id="4b3e7-112">The following command deletes all the device update configuration settings where the log cleanup interval is greater than 10 days (10.00:00:00):</span></span>
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

<span data-ttu-id="4b3e7-113">Дополнительные сведения см. в разделе справки для командлета [Remove – CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4b3e7-113">For details, see the Help topic for the [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

