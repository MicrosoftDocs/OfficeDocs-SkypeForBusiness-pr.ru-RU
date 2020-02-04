---
title: 'Lync Server 2013: Настройка SNMP для приложения'
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
ms.openlocfilehash: 9e11d79278318c99e1c6a1db3c4609e19553ba4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-snmp-application-in-lync-server-2013"></a><span data-ttu-id="8db13-102">Настройка приложения SNMP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8db13-102">Configure an SNMP application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8db13-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="8db13-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="8db13-104">Lync Server 2013 включает стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о расположении к приложениям протокола SNMP, которые соответствуют MAC-адресам с портом и переключаются.</span><span class="sxs-lookup"><span data-stu-id="8db13-104">Lync Server 2013 includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span>

<span data-ttu-id="8db13-105">Если установлено приложение SNMP и служба "сведения о местоположении" не может найти соответствие в базе данных расположения, Служба сведений о расположении автоматически запрашивает это приложение, используя MAC-адрес, предоставленный клиентом.</span><span class="sxs-lookup"><span data-stu-id="8db13-105">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="8db13-106">Затем служба сведения о местоположении использует данные порта и коммутатора, возвращенные приложением SNMP, для повторного запроса к базе данных о расположении.</span><span class="sxs-lookup"><span data-stu-id="8db13-106">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>

<span data-ttu-id="8db13-107">Подробности можно найти в разделе [Set-ксвебсервицеконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span><span class="sxs-lookup"><span data-stu-id="8db13-107">For details, see [Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServiceConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8db13-108">MAC-адреса недоступны на компьютерах под управлением Windows 8.</span><span class="sxs-lookup"><span data-stu-id="8db13-108">MAC addresses are not available on computers running Windows 8.</span></span>



</div>

<div>

## <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="8db13-109">Настройка URL-адреса приложения SNMP</span><span class="sxs-lookup"><span data-stu-id="8db13-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="8db13-110">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8db13-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8db13-111">Запустите следующий командлет для настройки URL-адреса приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="8db13-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span>
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

