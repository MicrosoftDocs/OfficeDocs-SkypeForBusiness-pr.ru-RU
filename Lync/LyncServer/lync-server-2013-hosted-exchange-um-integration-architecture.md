---
title: 'Lync Server 2013: архитектура интеграции размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2991bb35298534943d030b04c1cae7a438318c62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="beba0-102">Архитектура интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="beba0-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beba0-103">_**Тема последнего изменения:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="beba0-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="beba0-104">Приложение Lync Server 2013 Ексум поддерживает интеграцию с развертыванием в локальной системе обмена сообщениями Exchange (UM), используя службу обмена СООБЩЕНИЯми Exchange, размещенную поставщиком услуг, или сочетанием этих двух возможностей.</span><span class="sxs-lookup"><span data-stu-id="beba0-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="beba0-105">На следующей схеме показаны все три возможности.</span><span class="sxs-lookup"><span data-stu-id="beba0-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="beba0-106">**Интеграция с локальным развертыванием единой системы обмена сообщениями Exchange и двумя поставщиками размещенных служб Exchange**</span><span class="sxs-lookup"><span data-stu-id="beba0-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="beba0-107">![Развертывание локальной системы обмена сообщениями на сервере Lync Server] (images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Развертывание локальной системы обмена сообщениями на сервере Lync Server")</span><span class="sxs-lookup"><span data-stu-id="beba0-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="beba0-108">Поддерживаются перечисленные ниже режимы.</span><span class="sxs-lookup"><span data-stu-id="beba0-108">The following modes are supported:</span></span>

  - <span data-ttu-id="beba0-109">**Локальное развертывание:** Lync Server 2013 и Exchange разворачиваются на локальных серверах в рамках предприятия.</span><span class="sxs-lookup"><span data-stu-id="beba0-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="beba0-110">**Развертывание между локальными** средами: Lync Server 2013 развертывается на локальных серверах организации, а UM-служба Exchange размещается в средстве поставщика Интернет-услуг, например в центре обработки данных Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="beba0-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="beba0-111">**Смешанное развертывание:** В составе сервера Lync Server 2013 есть некоторые почтовые ящики пользователей, расположенные на локальных серверах Exchange, и некоторые почтовые ящики, расположенные в центре обработки данных служб Exchange.</span><span class="sxs-lookup"><span data-stu-id="beba0-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="beba0-112">Смешанное развертывание может использоваться в качестве переходного решения во время оценки и поэтапной миграции пользователей на размещенную UM-среду Exchange или постоянное решение, если вы не хотите, чтобы некоторые пользователи работали в локальной среде обмена СООБЩЕНИЯми, после того как вы перенесите другие.</span><span class="sxs-lookup"><span data-stu-id="beba0-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="beba0-113">Общее адресное пространство SIP</span><span class="sxs-lookup"><span data-stu-id="beba0-113">Shared SIP Address Space</span></span>

<span data-ttu-id="beba0-114">Чтобы интегрировать Lync Server 2013 с локальной развертыванием UM, вы предоставляете разрешение Lync Server 2013 для чтения объектов доменных служб Active Directory в Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="beba0-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="beba0-115">Тем не менее, этот подход не работает для интеграции с размещенной единой системой обмена сообщениями Exchange, поскольку Lync Server 2013 и Exchange UM установлены в разных лесах, не имеющих доверительных отношений между ними.</span><span class="sxs-lookup"><span data-stu-id="beba0-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="beba0-116">Чтобы интегрировать Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange, необходимо настроить *Общее адресное пространство SIP*.</span><span class="sxs-lookup"><span data-stu-id="beba0-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="beba0-117">В этой конфигурации одно и то же адресное пространство домена SIP доступно как для Lync Server 2013, так и для размещенного поставщика служб единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="beba0-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beba0-118">Использование общедоступного адресного пространства SIP сходно с подходом, используемым в гибридной среде Lync Server 2013, в которой некоторые пользователи находятся в локальном развертывании, а некоторые — в размещенном развертывании (например, Lync Online).</span><span class="sxs-lookup"><span data-stu-id="beba0-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="beba0-119">Домен SIP делится между собой.</span><span class="sxs-lookup"><span data-stu-id="beba0-119">The SIP domain is split between them.</span></span> <span data-ttu-id="beba0-120">При интеграции Lync Server 2013 с размещенной UM-службой Exchange убедитесь в том, что в общее адресное пространство SIP включается поставщик служб Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="beba0-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="beba0-121">Чтобы настроить общее адресное пространство SIP для интеграции с поставщиком служб Exchange UM, необходимо настроить пограничный сервер следующим образом:</span><span class="sxs-lookup"><span data-stu-id="beba0-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="beba0-122">Настройте пограничный сервер для Федерации, запустив командлет **Set-ксакцесседжеконфигуратион** , чтобы задать указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="beba0-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="beba0-123">**UseDnsSrvRouting** указывает, что пограничные серверы будут основываться на записях DNS SRV при отправке и получении запросов федерации.</span><span class="sxs-lookup"><span data-stu-id="beba0-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="beba0-p105">**AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов. Это свойство также определяет, разрешено ли внутренним пользователям связываться с пользователями в сценарии разделенного домена.</span><span class="sxs-lookup"><span data-stu-id="beba0-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="beba0-126">**Енаблепартнердисковери** указывает, будет ли Lync Server 2013 использовать DNS-записи для определения доменных партнеров, не указанных в списке разрешенных доменов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="beba0-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="beba0-127">Если значение "ложь", Lync Server 2013 будет включать только те домены, которые находятся в списке разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="beba0-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="beba0-128">Этот параметр обязателен, если используется маршрутизация службы DNS.</span><span class="sxs-lookup"><span data-stu-id="beba0-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="beba0-129">В большинстве развертываний устанавливается значение False, чтобы исключить открытие федерации со всеми партнерами.</span><span class="sxs-lookup"><span data-stu-id="beba0-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="beba0-130">Репликация центрального хранилища управления на пограничном сервере и проверка репликации.</span><span class="sxs-lookup"><span data-stu-id="beba0-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="beba0-131">Подробности можно найти в разделе [Экспорт топологии Lync Server 2013 и копирование на внешние носители для установки Edge](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="beba0-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="beba0-132">Настройте *поставщик услуг размещения* на пограничном сервере, запустив командлет **New-кшостингпровидер** , чтобы задать указанные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="beba0-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="beba0-133">**Identity** указывает уникальный идентификатор строкового значения для поставщика услуг размещения, который вы создаете, например **размещенной UM-среды Exchange**.</span><span class="sxs-lookup"><span data-stu-id="beba0-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="beba0-134">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="beba0-134">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="beba0-135">Необходимо установить значение **true**.</span><span class="sxs-lookup"><span data-stu-id="beba0-135">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="beba0-136">Параметр **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP.</span><span class="sxs-lookup"><span data-stu-id="beba0-136">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="beba0-137">Необходимо установить значение **true**.</span><span class="sxs-lookup"><span data-stu-id="beba0-137">Must be set to **True**.</span></span>
    
      - <span data-ttu-id="beba0-138">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="beba0-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="beba0-139">Для него должно быть задано **значение false**.</span><span class="sxs-lookup"><span data-stu-id="beba0-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="beba0-140">**Проксифкдн** указывает полное доменное имя (FQDN) для прокси-сервера, используемого поставщиком услуг размещения, например **proxyserver.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="beba0-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="beba0-141">Обратитесь к поставщику услуг хостинга для получения этих сведений.</span><span class="sxs-lookup"><span data-stu-id="beba0-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="beba0-142">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="beba0-142">This value cannot be modified.</span></span> <span data-ttu-id="beba0-143">Если поставщик услуг размещения изменит свой прокси-сервер, необходимо удалить и повторно создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="beba0-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="beba0-144">\*\*\*\* "WebProxy" показывает, является ли прокси-сервер, используемый поставщиком услуг размещения, включен в топологию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="beba0-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="beba0-145">Для него должно быть задано **значение false**.</span><span class="sxs-lookup"><span data-stu-id="beba0-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

