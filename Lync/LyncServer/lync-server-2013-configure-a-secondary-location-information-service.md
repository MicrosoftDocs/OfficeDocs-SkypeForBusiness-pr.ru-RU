---
title: 'Lync Server 2013: Настройка дополнительной службы сведений о расположении'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b7ee9383939e8df5466d615f6fda4a2af33c2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="e6afb-102">Настройка дополнительной службы сведений о расположении в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6afb-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6afb-103">_**Тема последнего изменения:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="e6afb-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="e6afb-104">Lync Server 2013 предоставляет интерфейс веб-службы, который можно использовать для указания службы сведений о расположении в базу данных дополнительного расположения (СЛС).</span><span class="sxs-lookup"><span data-stu-id="e6afb-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="e6afb-105">Интерфейс веб-службы, который подключается к базе данных СЛС, должен соответствовать WSDL службы сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="e6afb-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="e6afb-106">Если вы настроили базу данных расположения и дополнительную базу данных расположения, Служба сведений о расположении сначала запрашивает базу данных расположения, а если совпадений не найдено, отправляет запрос на расположение от клиента в базу данных СЛС.</span><span class="sxs-lookup"><span data-stu-id="e6afb-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="e6afb-107">Если расположение находится в СЛС, служба сведения о местоположении затем отправляет клиенту расположение обратно.</span><span class="sxs-lookup"><span data-stu-id="e6afb-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="e6afb-108">Подробности можно найти в документации по оболочке управления Lync Server для следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="e6afb-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="e6afb-109">**Set-Ксвебсервицеконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="e6afb-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="e6afb-110">Настройка дополнительной базы данных расположения</span><span class="sxs-lookup"><span data-stu-id="e6afb-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="e6afb-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e6afb-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e6afb-112">Чтобы настроить URL-адрес базы данных дополнительных расположений, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="e6afb-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

