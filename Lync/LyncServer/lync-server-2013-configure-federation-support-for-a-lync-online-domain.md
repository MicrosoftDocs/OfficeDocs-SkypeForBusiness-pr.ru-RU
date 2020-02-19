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
ms.openlocfilehash: e1f8a73451f88b5195a5137013082dad2c8d5b14
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="69075-102">Настройка поддержки федерации для домена Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69075-102">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69075-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="69075-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="69075-104">Для Федерации с Microsoft Lync Online 2010 пользователь должен выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="69075-104">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="69075-105">Настройте поддержку домена для клиента Lync Online 2010 (например, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="69075-105">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="69075-106">Как указано в разделе [необходимые условия для Федерации с помощью клиента Lync Online 2013 в](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) этой документации, вы уже включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="69075-106">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="69075-107">Для поддержки федерации необходимо указать метод, который будет использоваться для управления доступом в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="69075-107">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="69075-108">Если ваша организация настроена на использование обнаружения, Добавление домена в список разрешенных организаций является необязательным.</span><span class="sxs-lookup"><span data-stu-id="69075-108">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="69075-109">Если вы не включили обнаружение доменов, необходимо добавить доменное имя клиента Lync Online в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="69075-109">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="69075-110">Имя домена можно добавить с помощью панели управления Lync Server или командлета **New – CSAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="69075-110">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="69075-111">Для получения дополнительных сведений об использовании панели управления Lync Server, в том числе для включения обнаружения доменов, ознакомьтесь со статьей [Управление федеративными поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="69075-111">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="69075-112">Для получения дополнительных сведений об использовании командлета **New – CSAllowedDomain** для добавления домена, ознакомьтесь со статьей [New – CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="69075-112">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69075-113">Клиент Lync Online может иметь несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="69075-113">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="69075-114">Если вы хотите создать федерацию с несколькими доменами, необходимо настроить поддержку для каждого отдельного домена, с которым будет поддерживаться Федерация, а администратор Lync Online должен включить федерацию для каждого из доменов в федеративный.</span><span class="sxs-lookup"><span data-stu-id="69075-114">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="69075-115">Настройте поддержку поставщика услуг хостинга для домена клиента Lync Online 2010, с которым вы хотите создать федерацию.</span><span class="sxs-lookup"><span data-stu-id="69075-115">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="69075-116">С помощью процедуры, описанной в этом разделе, можно настроить поддержку поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="69075-116">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="69075-117">Этот шаг необходим только для Федерации с доменом клиента Lync Online, а не для Федерации с доменом, развернутым локально в расположении федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="69075-117">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="69075-118">Настройка поддержки поставщика услуг хостинга</span><span class="sxs-lookup"><span data-stu-id="69075-118">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="69075-119">На сервере переднего плана запустите командную консоль Lync Server: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="69075-119">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="69075-120">Запустите командлет **New – CsHostingProvider** , чтобы создать и настроить поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="69075-120">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="69075-121">Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="69075-121">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="69075-122">Команда в предыдущем примере задает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="69075-122">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="69075-123">**Identity** указывает уникальный идентификатор строкового значения для поставщика услуг хостинга, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="69075-123">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="69075-124">Обратите внимание, что если уже существует поставщик с таким удостоверением, то команда завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="69075-124">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="69075-125">Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="69075-125">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="69075-126">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="69075-126">This value cannot be modified.</span></span> <span data-ttu-id="69075-127">Если поставщик услуг размещения изменяет свой прокси-сервер, то придется удалить и заново создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="69075-127">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="69075-128">**Верификатионлевел** указывает, как (или если) сообщения, отправляемые от поставщика услуг хостинга, проходят проверку, чтобы убедиться, что они отправлены от этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="69075-128">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="69075-p107">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Две организации не смогут обмениваться сообщениями, пока этот параметр не будет установлен в значение **True**.</span><span class="sxs-lookup"><span data-stu-id="69075-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="69075-131">Параметр **EnabledSharedAddressSpace** указывает, используется ли этот поставщик услуг размещения в сценарии общего адресного пространства SIP (разделенного домена).</span><span class="sxs-lookup"><span data-stu-id="69075-131">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="69075-132">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69075-132">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="69075-133">Если установлено значение **False**, то поставщик размещает другие типы учетных записей, такие как учетные записи Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="69075-133">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="69075-134">Параметр "... **" указывает,** входит ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69075-134">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="69075-135">Подробнее об использовании этого командлета можно узнать в статье [New – CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="69075-135">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

