---
title: Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Edge Server for integration with hosted Exchange UM
ms:assetid: ede3f2f9-f412-418e-a705-8d8ec98176c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399075(v=OCS.15)
ms:contentKeyID: 48185745
ms.date: 01/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a801ba4bf5f67eeda2eb760b3f639bac4cd13b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-edge-server-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="3c253-102">Настройка пограничного сервера для интеграции с размещенной единой системой обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="3c253-102">Configure the Edge Server for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c253-103">_**Тема последнего изменения:** 2015-01-23_</span><span class="sxs-lookup"><span data-stu-id="3c253-103">_**Topic Last Modified:** 2015-01-23_</span></span>

<span data-ttu-id="3c253-104">Чтобы предоставить пользователям Lync Server 2013 возможности голосовой почты на размещенной единой системе обмена сообщениями Exchange, необходимо выполнить следующие задачи по настройке пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="3c253-104">To provide your Lync Server 2013 users with voice mail capabilities on hosted Exchange Unified Messaging (UM), you must perform the following configuration tasks on the Edge Server:</span></span>

  - <span data-ttu-id="3c253-105">Настроить пограничный сервер для федерации.</span><span class="sxs-lookup"><span data-stu-id="3c253-105">Configure the Edge Server for federation.</span></span>

  - <span data-ttu-id="3c253-106">Реплицируются данные из хранилища Central Management на пограничном сервере и проверяйте репликацию.</span><span class="sxs-lookup"><span data-stu-id="3c253-106">Replicate Central Management store data to the Edge Server and verify the replication.</span></span>

  - <span data-ttu-id="3c253-107">Создать поставщика услуг размещения на пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="3c253-107">Create a hosting provider on the Edge Server.</span></span>

<span data-ttu-id="3c253-108">Дополнительные сведения можно найти в документации по оболочке управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="3c253-108">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="3c253-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c253-109">[Set-CsAccessEdgeConfiguration](https://technet.microsoft.com/en-us/library/Gg413017(v=OCS.15))</span></span>

  - <span data-ttu-id="3c253-110">[New-Кшостингпровидер](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c253-110">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="3c253-111">Перед выполнением этих действий необходимо создать внешнюю запись DNS SRV для размещения службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="3c253-111">You must create an external DNS SRV record for the hosting Exchange service before you perform these steps.</span></span> <span data-ttu-id="3c253-112">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Создание записи SRV DNS для интеграции с размещенной единой системой обмена сообщениями Exchange</A>.</span><span class="sxs-lookup"><span data-stu-id="3c253-112">For details, see <A href="lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md">Create a DNS SRV record for integration with hosted Exchange UM</A>.</span></span>



</div>

<div>

## <a name="to-configure-the-edge-server-for-federation"></a><span data-ttu-id="3c253-113">Настройка пограничного сервера для федерации</span><span class="sxs-lookup"><span data-stu-id="3c253-113">To configure the Edge Server for federation</span></span>

1.  <span data-ttu-id="3c253-114">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3c253-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3c253-p102">Выполните командлет Set-CsAccessEdgeConfiguration, чтобы настроить этот сервер для федерации. Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3c253-p102">Run the Set-CsAccessEdgeConfiguration cmdlet to configure the server for federation. For example, run:</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -AllowFederatedUsers 1 -EnablePartnerDiscovery 0
    
    <span data-ttu-id="3c253-117">Команда в предыдущем примере задает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3c253-117">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="3c253-118">**UseDnsSrvRouting** указывает, что пограничные серверы будут основываться на записях DNS SRV при отправке и получении запросов федерации.</span><span class="sxs-lookup"><span data-stu-id="3c253-118">**UseDnsSrvRouting** specifies that Edge Servers will rely on DNS SRV records when sending and receiving federation requests.</span></span>
    
      - <span data-ttu-id="3c253-p103">**AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов. Это свойство также определяет, разрешено ли внутренним пользователям связываться с пользователями в сценарии разделенного домена.</span><span class="sxs-lookup"><span data-stu-id="3c253-p103">**AllowFederatedUsers** specifies whether internal users are allowed to communicate with users from federated domains. This property also determines whether internal users can communicate with users in a split domain scenario.</span></span>
    
      - <span data-ttu-id="3c253-121">**Енаблепартнердисковери** указывает, будет ли Lync Server использовать DNS-записи для выяснения доменных доменов, не указанных в списке разрешенных доменов Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3c253-121">**EnablePartnerDiscovery** specifies whether Lync Server will use DNS records to try to discover partner domains not listed in the Active Directory allowed domains list.</span></span> <span data-ttu-id="3c253-122">Если значение равно false, Lync Server 2013 будет использоваться только для Федерации с доменами, которые находятся в списке разрешенные домены.</span><span class="sxs-lookup"><span data-stu-id="3c253-122">If False, Lync Server 2013 will only federate with domains found on the allowed domains list.</span></span> <span data-ttu-id="3c253-123">Этот параметр обязателен, если используется маршрутизация службы DNS.</span><span class="sxs-lookup"><span data-stu-id="3c253-123">This parameter is required if you use DNS service routing.</span></span> <span data-ttu-id="3c253-124">В большинстве развертываний устанавливается значение False, чтобы исключить открытие федерации со всеми партнерами.</span><span class="sxs-lookup"><span data-stu-id="3c253-124">In most deployments, the value is set to false to avoid opening up federation to all partners.</span></span>

</div>

<div>

## <a name="to-replicate-data-to-the-edge-server-and-verify-the-replication"></a><span data-ttu-id="3c253-125">Репликация данных на пограничный сервер и проверка репликации</span><span class="sxs-lookup"><span data-stu-id="3c253-125">To replicate data to the Edge Server and verify the replication</span></span>

  - <span data-ttu-id="3c253-126">Убедитесь, что репликация на пограничный сервер выполнена в полном объеме.</span><span class="sxs-lookup"><span data-stu-id="3c253-126">Verify that the replication to the Edge Server is complete.</span></span> <span data-ttu-id="3c253-127">Описание процедуры можно найти [в разделе Проверка соединения внутренних серверов и пограничных серверов в Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="3c253-127">For the procedure, see [Verify connectivity between internal servers and Edge Servers in Lync Server 2013](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md).</span></span>

</div>

<div>

## <a name="to-create-a-hosting-provider-on-the-edge-server"></a><span data-ttu-id="3c253-128">Создание в пограничном сервере поставщика услуг размещения</span><span class="sxs-lookup"><span data-stu-id="3c253-128">To create a hosting provider on the Edge Server</span></span>

1.  <span data-ttu-id="3c253-129">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="3c253-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3c253-130">Выполните командлет **New-CsHostingProvider**, чтобы настроить поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="3c253-130">Run the **New-CsHostingProvider** cmdlet to configure the hosting provider.</span></span> <span data-ttu-id="3c253-131">Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3c253-131">For example, run:</span></span>
    
        New-CsHostingProvider -Identity Fabrikam.com -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFQDN "proxyserver.fabrikam.com" -IsLocal $False -VerificationLevel UseSourceVerification
    
    <span data-ttu-id="3c253-132">Команда в предыдущем примере задает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3c253-132">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="3c253-p107">Параметр **Identity** задает уникальный строковый идентификатор создаваемого поставщика услуг размещения, в данном случае это \*\*Fabrikam.com \*\*. Обратите внимание, что если уже существует поставщик с таким удостоверением, то команда завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="3c253-p107">**Identity** specifies a unique string value identifier for the hosting provider you are creating, in this example, **Fabrikam.com**. Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="3c253-p108">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Две организации не смогут обмениваться сообщениями, пока этот параметр не будет установлен в значение **True**.</span><span class="sxs-lookup"><span data-stu-id="3c253-p108">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="3c253-137">Параметр **EnabledSharedAddressSpace** указывает, используется ли этот поставщик услуг размещения в сценарии общего адресного пространства SIP (разделенного домена).</span><span class="sxs-lookup"><span data-stu-id="3c253-137">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="3c253-138">Прежде чем приступить к заданию значения <CODE>EnableSharedAddressSpace</CODE> true, попробуйте разрешить внутреннюю запись SRV-записи для Федерации.</span><span class="sxs-lookup"><span data-stu-id="3c253-138">Before you set <CODE>EnableSharedAddressSpace</CODE> to True, try to resolve the Federation SRV record internally.</span></span> <span data-ttu-id="3c253-139">Если эту запись невозможно устранить внутренне, необходимо создать записи _sipfederationtls. _tcp. &lt;domain&gt; и _sip. _tls. &lt;домен&gt; во внутренней DNS-службе.</span><span class="sxs-lookup"><span data-stu-id="3c253-139">If this record cannot be resolved internally, then you need to create the records, _sipfederationtls._tcp.&lt;domain&gt; and _sip._tls.&lt;domain&gt; in the internal DNS.</span></span> <span data-ttu-id="3c253-140">Данные записи должны указывать на внешний IP-адрес интерфейса доступа пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="3c253-140">These records should point to the external IP address of the Access Interface of the Edge Server.</span></span>

        
        </div>
    
      - <span data-ttu-id="3c253-141">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c253-141">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server 2013 accounts.</span></span> <span data-ttu-id="3c253-142">Если **False**, то поставщик размещает другие типы учетных записей, такие как учетные записи Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="3c253-142">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="3c253-p111">Параметр **ProxyFQDN** задает полное доменное имя прокси-сервера, используемого поставщиком услуг размещения, в данном примере это **proxyserver.fabrikam.com**. Это значение нельзя изменить. Если поставщик услуг размещения изменяет свой прокси-сервер, то придется удалить и заново создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="3c253-p111">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider, in this example, **proxyserver.fabrikam.com**. This value cannot be modified. If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="3c253-146">"WebProxy **" показывает,** является ли прокси-сервер, используемый поставщиком услуг размещения, включен в топологию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3c253-146">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server 2013 topology.</span></span>
    
      - <span data-ttu-id="3c253-147">Параметр **VerficationLevel** указывает разрешенный уровень проверки для сообщений, отправляемых поставщику услуг размещения и от него.</span><span class="sxs-lookup"><span data-stu-id="3c253-147">**VerficationLevel** indicates the allowed verification level for messages sent to and from the hosted provider.</span></span> <span data-ttu-id="3c253-148">Укажите параметр **UseSourceVerification**, который основывается на уровне проверки, включенном в сообщения, отправленные от поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="3c253-148">Specify **UseSourceVerification**, which relies on the verification level included in messages sent from the hosting provider.</span></span> <span data-ttu-id="3c253-149">Если этот уровень не указан, то сообщения будут отклоняться как недоступные для проверки.</span><span class="sxs-lookup"><span data-stu-id="3c253-149">If this level is not specified, then the message will be rejected as being unverifiable.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c253-150">См. также</span><span class="sxs-lookup"><span data-stu-id="3c253-150">See Also</span></span>


[<span data-ttu-id="3c253-151">Экспорт топологии Lync Server 2013 и ее копирование на внешние носители для установки в пограничной топологии</span><span class="sxs-lookup"><span data-stu-id="3c253-151">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)  


[<span data-ttu-id="3c253-152">Проверка подключения между внутренними и пограничными серверами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3c253-152">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>](lync-server-2013-verify-connectivity-between-internal-servers-and-edge-servers.md)  


<span data-ttu-id="3c253-153">[New-Кшостингпровидер](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3c253-153">[New-CsHostingProvider](https://technet.microsoft.com/en-us/library/Gg398490(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

