---
title: 'Lync Server 2013: развертывание типов IP-адресов на сервере-посреднике'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e629b1074f41f1e32795de391b31e8b610f88b2e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="e024e-102">Развертывание типов IP-адресов на сервере-посреднике для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e024e-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e024e-103">_**Тема последнего изменения:** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="e024e-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="e024e-104">С помощью построителя топологии выполните действия, описанные в следующей процедуре, чтобы развернуть типы IP-адресов на сервере обновлений.</span><span class="sxs-lookup"><span data-stu-id="e024e-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="e024e-105">Развертывание типов IP-адресов на сервере-посреднике</span><span class="sxs-lookup"><span data-stu-id="e024e-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="e024e-106">В построителе топологии в разделе **Пулы исправлений**щелкните правой кнопкой мыши сервер в пуле и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e024e-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="e024e-107">(Или же выберите сервер и щелкните **Edit Properties** (Изменить свойства) в меню **Action** (Действие).)</span><span class="sxs-lookup"><span data-stu-id="e024e-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="e024e-p102">В диалоговом окне **Edit Properties** (Изменение свойств) выберите тип IP-адреса, который необходимо настроить. Для конфигурации двойного стека установите флажки **Enable IPv4** (Включить IP версии 4) и **Enable IPv6** (Включить IP версии 6), как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="e024e-p102">In the **Edit Properties** dialog box, select the IP address type that you want to configure. For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="e024e-110">**Диалоговое окно "Изменение свойств" для пула сервера-посредника**</span><span class="sxs-lookup"><span data-stu-id="e024e-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="e024e-111">![Страница общих свойств Lync Server с полным доменным именем] (images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Страница общих свойств Lync Server с полным доменным именем")</span><span class="sxs-lookup"><span data-stu-id="e024e-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="e024e-p103">**Use all configured IP addresses** (Использовать все заданные IP-адреса). Выберите этот параметр, если требуется разрешить использование любых IP-адресов, заданных на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e024e-p103">**Use all configured IP addresses**. Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e024e-114">Этот параметр рекомендуется использовать для конфигураций IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="e024e-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="e024e-p104">**Limit service usage to selected IP addresses** (Разрешить использовать службу только указанным IP-адресам). Выберите этот параметр, чтобы указать адрес, используемый на новом сервере. Если вы выберете этот параметр, потребуется ввести значение в поле Primary IP address (Основной IP-адрес).</span><span class="sxs-lookup"><span data-stu-id="e024e-p104">**Limit service usage to selected IP addresses**. Select this option to specify a specific address to use on the new server. If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="e024e-p105">**Primary IP address** (Основной IP-адрес). Введите IP-адрес, который будет использовать сервер для всех коммуникаций, за исключением ТСОП. Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="e024e-p105">**Primary IP address**. Enter an IP address that the server will use for all communications except public switched telephone network (PSTN). The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="e024e-121">**PSTN IP address** (IP-адрес ТСОП).</span><span class="sxs-lookup"><span data-stu-id="e024e-121">**PSTN IP address**.</span></span> <span data-ttu-id="e024e-122">Определите IP-адрес PSTN, если сервер-посредник является автономным.</span><span class="sxs-lookup"><span data-stu-id="e024e-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="e024e-123">Введенный IP-адрес должен соответствовать формату выбранного типа адресов.</span><span class="sxs-lookup"><span data-stu-id="e024e-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="e024e-124">Установка дополнительных сетевых интерфейсных карт (NIC) для поддержки конфигурации IP-адреса PSTN для Lync Server 2013 не поддерживается на размещенных ролях серверов с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="e024e-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="e024e-125">Дополнительные сведения о поддерживаемых конфигурациях сетевых адаптеров для Lync Server 2013 можно найти в разделе <A href="lync-server-2013-server-hardware-platforms.md">аппаратные платформы сервера для Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e024e-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

