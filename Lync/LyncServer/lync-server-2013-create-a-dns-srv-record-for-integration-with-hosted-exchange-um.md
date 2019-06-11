---
title: Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f96b8873e7d83b7025b43b111312185b8e5d5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="e4bc7-102">Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="e4bc7-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4bc7-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="e4bc7-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="e4bc7-104">В этой статье описано, как настроить запись SRV службы доменных имен (DNS), необходимую для того, чтобы сервер Lync Server 2013 Edge направлялся на размещенную службу Exchange, например Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="e4bc7-105">Создание внешней записи SRV DNS для размещенной службы Exchange</span><span class="sxs-lookup"><span data-stu-id="e4bc7-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="e4bc7-106">Войдите на внешний DNS-сервер в качестве участника группы Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="e4bc7-107">Нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="e4bc7-108">В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**и выберите домен SIP, в который будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="e4bc7-109">Вы должны создать SRV-запись DNS в домене SIP, в котором установлен или будет устанавливаться сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-109">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed.</span></span> <span data-ttu-id="e4bc7-110">Когда вы создаете SRV-запись, полное доменное имя, используемое узлом для этого поля службы, должно быть внешним доменным именем пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-110">When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool.</span></span> <span data-ttu-id="e4bc7-111">Например, если внешнее полное доменное имя пограничного пула — edge01.contoso.net, введите это значение.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-111">For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value.</span></span> <span data-ttu-id="e4bc7-112">Этот элемент также должен находиться в том же домене, что и DNS-записи HOSTS (A).</span><span class="sxs-lookup"><span data-stu-id="e4bc7-112">This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="e4bc7-113">Щелкните выбранный домен правой кнопкой мыши и выберите пункт **другие новые записи**.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="e4bc7-114">В списке **тип записи ресурсов**выберите пункт **расположение службы (SRV)** и нажмите кнопку **создать запись**.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="e4bc7-115">В **новой записи ресурса**выберите пункт **Служба**, а затем введите \*\* \_сипфедератионтлс\*\*.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="e4bc7-116">Выберите **протокол**и введите \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="e4bc7-117">Нажмите **Номер порта** и введите значение **5061**.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="e4bc7-118">Щелкните **узел, предлагающий эту службу**, и введите полное доменное имя (FQDN) пула lync Server 2013 EDGE, который предоставляет доступ к системе lync Server 2013 для доверенных внешних клиентов.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="e4bc7-119">Кроме того, домен необходимо настроить в качестве полномочного, обслуживаемого домена в параметрах Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="e4bc7-120">Дополнительные сведения можно найти в разделе Создание обслуживаемых доменов по адресу <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-120">For details, see Create Accepted Domains at <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="e4bc7-121">Нажмите **ОК**, а затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="e4bc7-122">Проверка успешности создания DNS SRV-записи</span><span class="sxs-lookup"><span data-stu-id="e4bc7-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="e4bc7-123">Войдите в домен на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="e4bc7-124">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="e4bc7-125">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e4bc7-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="e4bc7-126">Убедитесь в том, что вы получили ответ на соответствующий IP-адрес для полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="e4bc7-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e4bc7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e4bc7-127">See Also</span></span>


[<span data-ttu-id="e4bc7-128">Создание DNS-записей для обратных прокси-серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4bc7-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

