---
title: 'Lync Server 2013: Настройка качества голосовой связи службы для Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice Quality of Service for Lync Phone Edition
ms:assetid: 2fbe19f7-7ebf-4f9b-a779-3a91f41d488f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520971(v=OCS.15)
ms:contentKeyID: 48183741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8967207d90450f769312ee0259549d0b12378cc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-voice-quality-of-service-for-lync-phone-edition-in-lync-server-2013"></a><span data-ttu-id="6a47b-102">Настройка качества обслуживания голосовой связи для Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a47b-102">Configure voice Quality of Service for Lync Phone Edition in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a47b-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="6a47b-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="6a47b-104">Требования к качеству обслуживания голосовой связи для устройств Lync Phone Edition в пуле можно настроить, задав уровень качества обслуживания для IP-телефонов, которые подключаются к Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6a47b-104">You can configure voice Quality of Service (QoS) requirements for Lync Phone Edition devices in a pool by setting the QoS level for IP phones that connect to Lync Server 2013.</span></span>

<div>

## <a name="to-configure-voice-quality-of-service-for-lync-phone-edition"></a><span data-ttu-id="6a47b-105">Настройка качества обслуживания голосовой связи для Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="6a47b-105">To configure voice Quality of Service for Lync Phone Edition</span></span>

1.  <span data-ttu-id="6a47b-106">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6a47b-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6a47b-107">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6a47b-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="6a47b-108">В левой панели навигации щелкните элемент **Clients** (Клиенты), а затем **Device Configuration** (Конфигурация устройства).</span><span class="sxs-lookup"><span data-stu-id="6a47b-108">In the left navigation bar, click **Clients**, and then click **Device Configuration**.</span></span>

3.  <span data-ttu-id="6a47b-109">В списке конфигураций на странице **Device Configuration** (Конфигурация устройства) дважды щелкните конфигурацию, для которой хотите изменить параметры качества обслуживания.</span><span class="sxs-lookup"><span data-stu-id="6a47b-109">On the **Device Configuration** page, in the list of device configurations, double-click the configuration for which you want to change QoS settings.</span></span>

4.  <span data-ttu-id="6a47b-p102">Укажите уровень качества обслуживания в области **Voice quality of service** (Качество обслуживания голосовой связи) окна **Edit Device Configuration** (Изменение конфигурации устройства). По умолчанию используется значение **40**.</span><span class="sxs-lookup"><span data-stu-id="6a47b-p102">In **Edit Device Configuration**, under **Voice quality of service**, specify the QoS level. The default level is **40**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6a47b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="6a47b-112">See Also</span></span>


[<span data-ttu-id="6a47b-113">Управление инфраструктурой сети Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a47b-113">Managing the Lync Server 2013 network infrastructure</span></span>](lync-server-2013-managing-the-lync-server-2013-network-infrastructure.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

