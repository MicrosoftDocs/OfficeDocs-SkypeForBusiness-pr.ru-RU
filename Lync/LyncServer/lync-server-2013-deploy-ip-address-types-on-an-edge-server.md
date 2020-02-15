---
title: 'Lync Server 2013: развертывание типов IP-адресов на пограничном сервере'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd057c79132200dbe5be8ee2551a711d8fb8e95c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="33be1-102">Развертывание типов IP-адресов на пограничном сервере для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33be1-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33be1-103">_**Последнее изменение темы:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="33be1-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="33be1-104">С помощью построителя топологий выполните действия, описанные в следующей процедуре, для развертывания типов IP-адресов на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="33be1-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="33be1-105">Развертывание типов IP-адресов в пограничном сервере</span><span class="sxs-lookup"><span data-stu-id="33be1-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="33be1-106">В построителе топологий в разделе **пограничные пулы**щелкните правой кнопкой мыши сервер в пуле, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="33be1-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="33be1-107">(можно также выбрать сервер, а затем выбрать пункт **Edit Properties (Изменить свойства)** в меню **Action (Действие)**.)</span><span class="sxs-lookup"><span data-stu-id="33be1-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="33be1-p102">В окне **изменения свойств** выберите конфигурацию IP-адресов, которую планируется поддерживать. На следующих рисунках показана конфигурация двойного стека для внутреннего и внешнего интерфейса.</span><span class="sxs-lookup"><span data-stu-id="33be1-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="33be1-110">**Внутренний интерфейс пограничного сервера с конфигурацией двойного стека**</span><span class="sxs-lookup"><span data-stu-id="33be1-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="33be1-111">![Страница общих свойств Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Страница общих свойств Lync Server")</span><span class="sxs-lookup"><span data-stu-id="33be1-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="33be1-112">**Внешний интерфейс пограничного сервера с конфигурацией двойного стека**</span><span class="sxs-lookup"><span data-stu-id="33be1-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="33be1-113">![Страница следующего прыжка или внешней конфигурации Lync Server](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Страница следующего прыжка или внешней конфигурации Lync Server")</span><span class="sxs-lookup"><span data-stu-id="33be1-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="33be1-114">Для каждого выбранного типа адреса необходимо предоставить соответствующие внутренние и внешние адреса.</span><span class="sxs-lookup"><span data-stu-id="33be1-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

