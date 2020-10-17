---
title: 'Lync Server 2013: Архитектура интеграции размещенной единой системы обмена сообщениями Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM integration architecture
ms:assetid: 0094d5dc-1836-441c-b6e2-f88e35203a8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398067(v=OCS.15)
ms:contentKeyID: 48183222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c2c16350ff111f31eb52a73290b1dbcddc9e580
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512586"
---
# <a name="hosted-exchange-um-integration-architecture-in-lync-server-2013"></a><span data-ttu-id="75aba-102">Архитектура интеграции размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75aba-102">Hosted Exchange UM integration architecture in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75aba-103">_**Последнее изменение темы:** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="75aba-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="75aba-104">Приложение Lync Server 2013 ExUM Routing поддерживает интеграцию с локальным развертыванием единой системы обмена сообщениями Exchange, с единой системой обмена сообщениями Exchange, размещенной у поставщика услуг, или с сочетанием этих двух способов.</span><span class="sxs-lookup"><span data-stu-id="75aba-104">The Lync Server 2013 ExUM Routing application supports integration with an on-premises Exchange Unified Messaging (UM) deployment, with Exchange UM hosted by a service provider, or with a combination of the two.</span></span> <span data-ttu-id="75aba-105">На следующей схеме показаны все три возможности.</span><span class="sxs-lookup"><span data-stu-id="75aba-105">The following diagram shows all three possibilities.</span></span>

<span data-ttu-id="75aba-106">**Интеграция с локальным развертыванием системы обмена сообщениями Exchange и двумя размещенными поставщиками Exchange**</span><span class="sxs-lookup"><span data-stu-id="75aba-106">**Integration with an on-premises Exchange UM deployment and two hosted Exchange providers**</span></span>

<span data-ttu-id="75aba-107">![Развертывание локальной единой системы обмена сообщениями Lync Server Exchange](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "Развертывание локальной единой системы обмена сообщениями Lync Server Exchange")</span><span class="sxs-lookup"><span data-stu-id="75aba-107">![On-premises Lync Server Exchange UM Deployment](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "On-premises Lync Server Exchange UM Deployment")</span></span>

<span data-ttu-id="75aba-108">Поддерживаются следующие режимы:</span><span class="sxs-lookup"><span data-stu-id="75aba-108">The following modes are supported:</span></span>

  - <span data-ttu-id="75aba-109">**Локальное развертывание:** Lync Server 2013 и служба единой системы обмена сообщениями Exchange развернуты на локальных серверах предприятия.</span><span class="sxs-lookup"><span data-stu-id="75aba-109">**On-premises deployment:** Lync Server 2013 and Exchange UM are both deployed on local servers within your enterprise.</span></span>

  - <span data-ttu-id="75aba-110">**Развертывание между организациями:** Lync Server 2013 развернут на локальных серверах в Организации, а единая система обмена сообщениями Exchange размещается в средстве поставщика веб-служб, например в центре обработки данных Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75aba-110">**Cross-premises deployment:** Lync Server 2013 is deployed on local servers within your enterprise and Exchange UM is hosted in an online service provider’s facility, such as a Microsoft Exchange Online data center.</span></span>

  - <span data-ttu-id="75aba-111">**Смешанное развертывание:** В развертывании Lync Server 2013 есть некоторые почтовые ящики пользователей, размещенные на локальных серверах Exchange на предприятии, а некоторые почтовые ящики находятся в центре обработки данных службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="75aba-111">**Mixed deployment:** Your Lync Server 2013 deployment has some user mailboxes homed on local Exchange servers within your enterprise and some mailboxes homed in a hosted Exchange service data center.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75aba-112">Смешанное развертывание может использоваться в качестве переходного решения в процессе оценки и поэтапной миграции пользователей в размещенную единую систему обмена сообщениями Exchange, или постоянного решения, если вы хотите оставить некоторые службы единой системы обмена сообщениями Exchange на локальных серверах и перенести остальные.</span><span class="sxs-lookup"><span data-stu-id="75aba-112">The mixed deployment can be used as a transitional solution during evaluation and phased migration of users to hosted Exchange UM, or a permanent solution if you opt to keep some users’ Exchange UM services on-premises after transferring others.</span></span>

    
    </div>

<div>

## <a name="shared-sip-address-space"></a><span data-ttu-id="75aba-113">Общее адресное пространство SIP</span><span class="sxs-lookup"><span data-stu-id="75aba-113">Shared SIP Address Space</span></span>

<span data-ttu-id="75aba-114">Чтобы интегрировать Lync Server 2013 с локальным развертыванием единой системы обмена сообщениями Exchange, предоставьте Lync Server 2013 разрешение на чтение объектов доменных служб Active Directory единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="75aba-114">To integrate Lync Server 2013 with an on-premises Exchange UM deployment, you grant Lync Server 2013 permission to read Exchange UM Active Directory Domain Services objects.</span></span> <span data-ttu-id="75aba-115">Однако этот подход не работает для интеграции с размещенной единой системой обмена сообщениями Exchange, так как Lync Server 2013 и Exchange единой системы обмена сообщениями устанавливаются в отдельных лесах без доверия между ними.</span><span class="sxs-lookup"><span data-stu-id="75aba-115">This approach does not work for integration with hosted Exchange UM, however, because Lync Server 2013 and Exchange UM are installed in separate forests with no trust between them.</span></span>

<span data-ttu-id="75aba-116">Чтобы интегрировать Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange, необходимо настроить *Общее адресное пространство SIP*.</span><span class="sxs-lookup"><span data-stu-id="75aba-116">To integrate Lync Server 2013 with hosted Exchange UM, you must configure a *shared SIP address space*.</span></span> <span data-ttu-id="75aba-117">В этой конфигурации одно и то же адресное пространство домена SIP доступно как в Lync Server 2013, так и на размещенном поставщике службы единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="75aba-117">In this configuration, the same SIP domain address space is available to both Lync Server 2013 and the hosted Exchange UM service provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75aba-118">Использование общего адресного пространства SIP аналогично подходу, используемому в локальной среде Lync Server 2013, в которой некоторые пользователи размещены в локальном развертывании, а некоторые — в размещенном развертывании (например, Lync Online).</span><span class="sxs-lookup"><span data-stu-id="75aba-118">Use of the shared SIP address space is similar to the approach used in a cross-premises Lync Server 2013 environment, in which some users are homed in the on-premises deployment and some are homed in a hosted deployment (such as Lync Online).</span></span> <span data-ttu-id="75aba-119">Домен SIP разделяется между ними.</span><span class="sxs-lookup"><span data-stu-id="75aba-119">The SIP domain is split between them.</span></span> <span data-ttu-id="75aba-120">При интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange убедитесь, что поставщик службы Exchange единой системы обмена сообщениями включен в общее адресное пространство SIP.</span><span class="sxs-lookup"><span data-stu-id="75aba-120">When you integrate Lync Server 2013 with hosted Exchange UM, ensure that you include the Exchange UM service provider in the shared SIP address space.</span></span>



</div>

<span data-ttu-id="75aba-121">Чтобы настроить общее адресное пространство SIP на интеграцию с поставщиком единой системы обмена сообщениями Exchange, необходимо настроить пограничный сервер следующим образом.</span><span class="sxs-lookup"><span data-stu-id="75aba-121">To configure the shared SIP address space for integrating with an Exchange UM service provider, you need to configure your Edge Server as follows:</span></span>

1.  <span data-ttu-id="75aba-122">Настройте федерацию на пограничном сервере, задав с помощью командлета **Set-CsAccessEdgeConfiguration** следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="75aba-122">Configure the Edge Server for federation by running the **Set-CsAccessEdgeConfiguration** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="75aba-123">**UseDnsSrvRouting** указывает на то, что пограничные серверы будут использовать записи DNS SRV при отправке и получении запросов федерации.</span><span class="sxs-lookup"><span data-stu-id="75aba-123">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="75aba-p105">**AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов. Это свойство также определяет, разрешено ли внутренним пользователям связываться с пользователями в сценарии разделенного домена.</span><span class="sxs-lookup"><span data-stu-id="75aba-p105">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="75aba-126">**EnablePartnerDiscovery** указывает, будет ли Lync Server 2013 использовать DNS-записи для обнаружения партнерских доменов, не указанных в списке разрешенных доменов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="75aba-126">**EnablePartnerDiscovery** specifies whether Lync Server 2013 will use DNS records to try to discover partner domains that are not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="75aba-127">Если значение равно false, Lync Server 2013 будет выполнять Федерацию только с доменами, которые находятся в списке разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="75aba-127">If False, Lync Server 2013 will federate only with domains that are found on the allowed domains list.</span></span> <span data-ttu-id="75aba-128">Этот параметр обязателен, если используется маршрутизация службы DNS.</span><span class="sxs-lookup"><span data-stu-id="75aba-128">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="75aba-129">В большинстве развертываний устанавливается значение False, чтобы исключить открытие федерации со всеми партнерами.</span><span class="sxs-lookup"><span data-stu-id="75aba-129">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

2.  <span data-ttu-id="75aba-130">Репликация центрального хранилища управления на пограничный сервер и проверка репликации.</span><span class="sxs-lookup"><span data-stu-id="75aba-130">Replicate the Central Management store to the Edge Server and verify the replication.</span></span> <span data-ttu-id="75aba-131">Сведения о том, как [экспортировать топологию Lync Server 2013 и скопировать ее на внешние носители для установки пограничного сервера, можно](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) найти в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="75aba-131">For details, see [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md) in the Deployment documentation.</span></span>

3.  <span data-ttu-id="75aba-132">Настройте *поставщика услуг размещения* на пограничном сервере, задав с помощью командлета **New-CsHostingProvider** следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="75aba-132">Configure a *hosting provider* on the Edge Server by running the **New-CsHostingProvider** cmdlet to set the following parameters:</span></span>
    
      - <span data-ttu-id="75aba-133">**Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения, например **Hosted Exchange UM**.</span><span class="sxs-lookup"><span data-stu-id="75aba-133">**Identity** specifies a unique string value identifier for the hosting provider that you are creating, for example, **Hosted Exchange UM**.</span></span>
    
      - <span data-ttu-id="75aba-p108">**Enabled** определяет, включено ли сетевое соединение между вашим доменом и поставщиком услуг размещения. Должен иметь значение **True**.</span><span class="sxs-lookup"><span data-stu-id="75aba-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="75aba-p109">**EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должен иметь значение **True**.</span><span class="sxs-lookup"><span data-stu-id="75aba-p109">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario. Must be set to **True**.</span></span>
    
      - <span data-ttu-id="75aba-138">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75aba-138">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="75aba-139">Должен иметь значение **False**.</span><span class="sxs-lookup"><span data-stu-id="75aba-139">Must be set to **False**.</span></span>
    
      - <span data-ttu-id="75aba-140">**ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения, например **proxyserver.fabrikam.com**.</span><span class="sxs-lookup"><span data-stu-id="75aba-140">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, for example, **proxyserver.fabrikam.com**.</span></span> <span data-ttu-id="75aba-141">Чтобы получить эту информацию, обратитесь к своему поставщику услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="75aba-141">Contact your hosting provider for this information.</span></span> <span data-ttu-id="75aba-142">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="75aba-142">This value cannot be modified.</span></span> <span data-ttu-id="75aba-143">Если поставщик услуг размещения изменит прокси-сервер, вам потребуется удалить и заново создать эту запись.</span><span class="sxs-lookup"><span data-stu-id="75aba-143">If the hosting provider changes its proxy server, you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="75aba-144">Параметр "... **" указывает,** включен ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75aba-144">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span> <span data-ttu-id="75aba-145">Должен иметь значение **False**.</span><span class="sxs-lookup"><span data-stu-id="75aba-145">Must be set to **False**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

