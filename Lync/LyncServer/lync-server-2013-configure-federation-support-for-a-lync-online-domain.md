---
title: 'Lync Server 2013: Настройка поддержки федерации для домена Lync Online'
description: 'Lync Server 2013: Настройка поддержки федерации для домена Lync Online.'
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
ms.openlocfilehash: ee814efdfb68d3c5ef9772b733bf136ae53ea9e2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553305"
---
# <a name="configure-federation-support-for-a-lync-online-domain-in-lync-server-2013"></a><span data-ttu-id="2a3f5-103">Настройка поддержки федерации для домена Lync Online в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a3f5-103">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a3f5-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2a3f5-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2a3f5-105">Для Федерации с Microsoft Lync Online 2010 пользователь должен выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2a3f5-105">Federating with a Microsoft Lync Online 2010 customer requires you to complete the following steps:</span></span>

  - <span data-ttu-id="2a3f5-106">Настройте поддержку домена для клиента Lync Online 2010 (например, contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2a3f5-106">Configure support for the domain of the Lync Online 2010 customer (for example, contoso.onmicrosoft.com).</span></span> <span data-ttu-id="2a3f5-107">Как указано в разделе [необходимые условия для Федерации с помощью клиента Lync Online 2013 в](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) этой документации, вы уже включили Федерацию для своей организации.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-107">As specified in the [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md) section of this documentation, you should have already enabled federation for your organization.</span></span> <span data-ttu-id="2a3f5-108">Для поддержки федерации необходимо указать метод, который будет использоваться для управления доступом в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-108">Enabling federation requires specifying the method to be used to control access by federated domains.</span></span> <span data-ttu-id="2a3f5-109">Если ваша организация настроена на использование обнаружения, Добавление домена в список разрешенных организаций является необязательным.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-109">If you configured your organization to use discovery, adding the domain to your organization’s allowed list is optional.</span></span> <span data-ttu-id="2a3f5-110">Если вы не включили обнаружение доменов, необходимо добавить доменное имя клиента Lync Online в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-110">If you did not enable domain discovery, then you must add the domain name of the Lync Online customer to your allowed domains list.</span></span> <span data-ttu-id="2a3f5-111">Имя домена можно добавить с помощью панели управления Lync Server или командлета **New – CSAllowedDomain** .</span><span class="sxs-lookup"><span data-stu-id="2a3f5-111">You can add a domain name either by using Lync Server Control Panel or by running the **New-CSAllowedDomain** cmdlet.</span></span> <span data-ttu-id="2a3f5-112">Для получения дополнительных сведений об использовании панели управления Lync Server, в том числе для включения обнаружения доменов, ознакомьтесь со статьей [Управление федеративными поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-112">For details about using Lync Server Control Panel, including enabling discovery of domains, see [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span> <span data-ttu-id="2a3f5-113">Для получения дополнительных сведений об использовании командлета **New – CSAllowedDomain** для добавления домена, ознакомьтесь со статьей [New – CSAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-113">For details about using the **New-CSAllowedDomain** cmdlet to add a domain, see [New-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/New-CsAllowedDomain) in the Operations documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2a3f5-114">Клиент Lync Online может иметь несколько доменов.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-114">A Lync Online customer can have multiple domains.</span></span> <span data-ttu-id="2a3f5-115">Если вы хотите создать федерацию с несколькими доменами, необходимо настроить поддержку для каждого отдельного домена, с которым будет поддерживаться Федерация, а администратор Lync Online должен включить федерацию для каждого из доменов в федеративный.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-115">If you want to federate with more than one of the domains, you must configure support for each individual domain with which you want to support federation, and the administrator of the Lync Online customer must enable federation for each of the domains to be federated.</span></span>

    
    </div>

  - <span data-ttu-id="2a3f5-116">Настройте поддержку поставщика услуг хостинга для домена клиента Lync Online 2010, с которым вы хотите создать федерацию.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-116">Configure support for the hosting provider of the Lync Online 2010 customer domain with which you want to federate.</span></span> <span data-ttu-id="2a3f5-117">С помощью процедуры, описанной в этом разделе, можно настроить поддержку поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-117">Use the procedure in this section to configure support for hosting provider.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2a3f5-118">Этот шаг необходим только для Федерации с доменом клиента Lync Online, а не для Федерации с доменом, развернутым локально в расположении федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-118">This step is required only for federation with a domain of a Lync Online customer, not for federation with any domain that is deployed on-premises at a federated partner’s location.</span></span>

    
    </div>

<div>

## <a name="to-configure-support-for-a-hosting-provider"></a><span data-ttu-id="2a3f5-119">Настройка поддержки поставщика услуг хостинга</span><span class="sxs-lookup"><span data-stu-id="2a3f5-119">To configure support for a hosting provider</span></span>

1.  <span data-ttu-id="2a3f5-120">На сервере переднего плана запустите командную консоль Lync Server: нажмите кнопку **Пуск**, выберите **все программы**, **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-120">From a Front End Server, Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2a3f5-121">Запустите командлет **New – CsHostingProvider** , чтобы создать и настроить поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-121">Run the **New-CsHostingProvider** cmdlet to create and configure the hosting provider.</span></span> <span data-ttu-id="2a3f5-122">Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="2a3f5-122">For example, run:</span></span>
    
        New-CsHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification -Enabled $True -EnabledSharedAddressSpace $False -HostsOCSUsers $False -IsLocal $False
    
    <span data-ttu-id="2a3f5-123">Команда в предыдущем примере задает следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2a3f5-123">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="2a3f5-124">**Identity** указывает уникальный идентификатор строкового значения для поставщика услуг хостинга, который вы создаете.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-124">**Identity** specifies a unique string value identifier for the hosting provider that you are creating.</span></span> <span data-ttu-id="2a3f5-125">Обратите внимание, что если уже существует поставщик с таким удостоверением, то команда завершится неудачно.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-125">Note that the command will fail if an existing provider has already been configured with that Identity.</span></span>
    
      - <span data-ttu-id="2a3f5-126">Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-126">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider.</span></span> <span data-ttu-id="2a3f5-127">Это значение нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-127">This value cannot be modified.</span></span> <span data-ttu-id="2a3f5-128">Если поставщик услуг размещения изменяет свой прокси-сервер, то придется удалить и заново создать запись для этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-128">If the hosting provider changes its proxy server you will need to delete and then recreate the entry for that provider.</span></span>
    
      - <span data-ttu-id="2a3f5-129">**Верификатионлевел** указывает, как (или если) сообщения, отправляемые от поставщика услуг хостинга, проходят проверку, чтобы убедиться, что они отправлены от этого поставщика.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-129">**VerificationLevel** specifies how (or if) messages sent from a hosting provider are verified to ensure that they were sent from that provider.</span></span>
    
      - <span data-ttu-id="2a3f5-p107">Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Две организации не смогут обмениваться сообщениями, пока этот параметр не будет установлен в значение **True**.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-p107">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled. Messages cannot be exchanged between the two organizations until this value is set to **True**.</span></span>
    
      - <span data-ttu-id="2a3f5-132">Параметр **EnabledSharedAddressSpace** указывает, используется ли этот поставщик услуг размещения в сценарии общего адресного пространства SIP (разделенного домена).</span><span class="sxs-lookup"><span data-stu-id="2a3f5-132">**EnabledSharedAddressSpace** indicates whether the hosting provider is being used in a shared SIP address space (split domain) scenario.</span></span>
    
      - <span data-ttu-id="2a3f5-133">**Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения учетных записей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-133">**HostsOCSUsers** indicates whether the hosting provider is used to host Lync Server accounts.</span></span> <span data-ttu-id="2a3f5-134">Если установлено значение **False**, то поставщик размещает другие типы учетных записей, такие как учетные записи Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-134">If **False**, the provider hosts other account types, such as Microsoft Exchange accounts.</span></span>
    
      - <span data-ttu-id="2a3f5-135">Параметр "... **" указывает,** входит ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-135">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Lync Server topology.</span></span>
    
    <span data-ttu-id="2a3f5-136">Подробнее об использовании этого командлета можно узнать в статье [New – CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="2a3f5-136">For details about using this cmdlet, see [New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

