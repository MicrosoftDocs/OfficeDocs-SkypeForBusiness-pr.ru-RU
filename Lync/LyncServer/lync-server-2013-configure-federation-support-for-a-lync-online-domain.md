---
title: 'Lync Server 2013: Настройка поддержки федерации для домена Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation support for a Lync Online domain
ms:assetid: 19d5d5be-cd7f-47b8-b6c5-651a3191def7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202166(v=OCS.15)
ms:contentKeyID: 48183530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f883e8d730e63788b4cbe0ccd3315f21e6fea97
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="0fc03-102">Настройка поддержки федерации для домена Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fc03-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fc03-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0fc03-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0fc03-104">Для Федерации с пользователем Microsoft Lync Online 2010 необходимо выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0fc03-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="0fc03-105">Настройка поддержки домена для клиента Lync Online 2010 (например, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="0fc03-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="0fc03-106">Как указано в разделе [необходимые условия для интеграции с клиентом Lync Online 2013 в составе](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) этой документации, вы должны уже включить федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="0fc03-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="0fc03-107">Для включения Федерации необходимо указать метод, который будет использоваться для управления доступом федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="0fc03-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="0fc03-108">Если ваша организация настроена на использование обнаружения, Добавление домена в список разрешенных организаций не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="0fc03-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="0fc03-109">Если вы не включите функцию обнаружения доменов, необходимо добавить доменное имя клиента Lync Online в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="0fc03-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="0fc03-110">Вы можете добавить доменное имя либо с помощью панели управления Lync Server, либо путем запуска командлета **New-ксалловеддомаин** .</span><span class="sxs-lookup"><span data-stu-id="0fc03-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="0fc03-111">Подробнее об использовании панели управления Lync Server, в том числе для включения обнаружения доменов, можно узнать в статьях [Управление поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="0fc03-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="0fc03-112">Дополнительные сведения о том, как использовать командлет **New-ксалловеддомаин** для добавления домена, можно найти в разделе [New-ксалловеддомаин](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="0fc03-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc03-113">У клиента Lync Online может быть несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="0fc03-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="0fc03-114">Если вы хотите сделать Федерацию более чем одним доменом, необходимо настроить поддержку для каждого домена, с которым вы хотите поддерживать Федерацию, и администратором клиента Lync Online необходимо включить федерацию для каждого из доменов в Федеративной.</span><span class="sxs-lookup"><span data-stu-id="0fc03-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="0fc03-115">Настройте поддержку для поставщика услуг размещения домена пользователей Lync Online 2010, с которым вы хотите присвоить Федерацию.</span><span class="sxs-lookup"><span data-stu-id="0fc03-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="0fc03-116">С помощью описанной в этом разделе процедуры можно настроить поддержку для поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="0fc03-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fc03-117">Этот этап необходим только для Федерации с доменом клиента Lync Online, но не для Федерации с доменом, который развернут локально в расположении федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="0fc03-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="0fc03-118">Настройка поддержки поставщика услуг размещения</span><span class="sxs-lookup"><span data-stu-id="0fc03-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="0fc03-119">На сервере переднего плана запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="0fc03-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="0fc03-120">Запустите командлет **New-кшостингпровидер** для создания и настройки поставщика услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="0fc03-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="0fc03-121">Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0fc03-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="0fc03-122">Команда в предыдущем примере задает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="0fc03-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="0fc03-123">**Identity** — уникальный идентификатор строкового значения для поставщика услуг размещения, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="0fc03-123">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="0fc03-124">Обратите внимание, что если уже существует поставщик с таким удостоверением, то команда завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="0fc03-124">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="0fc03-125">Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="0fc03-125">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="0fc03-126">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="0fc03-126">This value cannot be modified.</span></span> <span data-ttu-id="0fc03-127">Если поставщик услуг размещения изменяет свой прокси-сервер, то придется удалить и заново создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="0fc03-127">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="0fc03-128">**Верификатионлевел** определяет способ проверки подлинности сообщений, отправленных поставщиком услуг размещения, чтобы убедиться, что они были отправлены этим поставщиком.</span><span class="sxs-lookup"><span data-stu-id="0fc03-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="0fc03-p107">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Две организации не смогут обмениваться сообщениями, пока этот параметр не будет установлен в значение **True**.</span><span class="sxs-lookup"><span data-stu-id="0fc03-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="0fc03-131">Параметр **EnabledSharedAddressSpace** указывает, используется ли этот поставщик услуг размещения в сценарии общего адресного пространства SIP (разделенного домена).</span><span class="sxs-lookup"><span data-stu-id="0fc03-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="0fc03-132">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0fc03-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="0fc03-133">Если **False**, то поставщик размещает другие типы учетных записей, такие как учетные записи Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="0fc03-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="0fc03-134">"WebProxy **" показывает,** является ли прокси-сервер, используемый поставщиком услуг размещения, включен в топологию сервера Lync.</span><span class="sxs-lookup"><span data-stu-id="0fc03-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="0fc03-135">Подробнее об использовании этого командлета можно узнать в разделе [New-кшостингпровидер](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="0fc03-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

