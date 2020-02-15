---
title: 'Lync Server 2013: Настройка службы сведений о дополнительном местоположении'
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
ms.openlocfilehash: 50d63d8316c9ce18bdf8677686a655046601b326
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a><span data-ttu-id="a270a-102">Настройка службы сведений о дополнительном местоположении в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a270a-102">Configure a secondary Location Information service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a270a-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="a270a-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="a270a-104">Lync Server 2013 предоставляет интерфейс веб-службы, который можно использовать для ссылки на службу сведений о местоположении в базу данных дополнительных источников расположения (SLS).</span><span class="sxs-lookup"><span data-stu-id="a270a-104">Lync Server 2013 provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="a270a-105">Интерфейс веб-службы, который подключается к базе данных SLS, должен соответствовать WSDL-службе сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="a270a-105">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="a270a-106">Если для базы данных расположения и базы данных дополнительных расположений настроена служба "сведения о местонахождении", сначала запрашивается база данных расположения, а если совпадения не найдены, отправляет запрос расположения от клиента в базу данных SLS.</span><span class="sxs-lookup"><span data-stu-id="a270a-106">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="a270a-107">Если расположение существует в SLS, служба информационного расположения затем отправляет клиенту расположение обратно.</span><span class="sxs-lookup"><span data-stu-id="a270a-107">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span>

<span data-ttu-id="a270a-108">Для получения дополнительных сведений обратитесь к документации по командной консоли Lync Server для следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="a270a-108">For details, see the Lync Server Management Shell documentation for the following cmdlet:</span></span>

  - <span data-ttu-id="a270a-109">**Set — CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="a270a-109">**Set-CsWebServiceConfiguration**</span></span>

<div>

## <a name="to-configure-secondary-location-database"></a><span data-ttu-id="a270a-110">Настройка базы данных дополнительных расположений</span><span class="sxs-lookup"><span data-stu-id="a270a-110">To configure Secondary Location database</span></span>

1.  <span data-ttu-id="a270a-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a270a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a270a-112">Выполните следующий командлет, чтобы настроить URL-адрес для расположения базы данных дополнительных расположений.</span><span class="sxs-lookup"><span data-stu-id="a270a-112">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span>
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

