---
title: 'Lync Server 2013: Настройка приложения SNMP'
description: 'Lync Server 2013: Настройка приложения SNMP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an SNMP application
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48185346
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7374b61ad85d7ddcb40ef1db535e17f86dea58f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546705"
---
# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="8ba73-103">Настройка приложения SNMP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ba73-103">Configure an SNMP application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ba73-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8ba73-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8ba73-105">Lync Server 2013 включает стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о местоположении к приложениям SNMP, которые совпадают с MAC-адресами и сведениями о порте и коммутаторе.</span><span class="sxs-lookup"><span data-stu-id="8ba73-105">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="8ba73-106">Если приложение SNMP установлено и служба сведений о местоположении не может найти соответствующее значение в базе данных расположений, Служба сведений о местоположении автоматически запрашивает приложение, используя MAC-адрес, предоставленный клиентом.</span><span class="sxs-lookup"><span data-stu-id="8ba73-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="8ba73-107">Затем служба "сведения о местоположении" использует сведения о порте и коммутаторе, возвращенные приложением SNMP, для повторного запроса к базе данных расположений.</span><span class="sxs-lookup"><span data-stu-id="8ba73-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="8ba73-108">Дополнительные сведения см. в статье [Set – CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8ba73-108">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8ba73-109">MAC-адреса недоступны на компьютерах под управлением Windows 8.</span><span class="sxs-lookup"><span data-stu-id="8ba73-109">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="8ba73-110">Настройка URL-адреса приложения SNMP</span><span class="sxs-lookup"><span data-stu-id="8ba73-110">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="8ba73-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8ba73-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8ba73-112">Запустите следующий командлет для настройки URL-адреса приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="8ba73-112">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

