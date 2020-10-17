---
title: Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями Exchange
description: Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями Exchange.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542145"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="41446-103">Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями Exchange</span><span class="sxs-lookup"><span data-stu-id="41446-103">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41446-104">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="41446-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="41446-105">В этом разделе описывается настройка записи SRV службы доменных имен (DNS), которая требуется для маршрутизации сервера Lync Server 2013, для маршрутизации в размещенную службу Exchange, например Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="41446-105">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="41446-106">Создание внешней записи SRV DNS для размещенной службы Exchange</span><span class="sxs-lookup"><span data-stu-id="41446-106">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="41446-107">Войдите на внешний сервер DNS как член группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="41446-107">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="41446-108">Нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="41446-108">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="41446-109">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**и выберите домен SIP, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41446-109">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="41446-p101">Необходимо создать запись SRV DNS в том домене SIP, в котором установлен или будет установлен Lync Server. При создании записи SRV полное доменное имя, которое указывается в поле узла этой службы, должно быть внешним полным доменным именем пограничного пула. Например, если внешнее полное доменное имя пограничного пула edge01.contoso.net, то введите это значение. Кроме того, это должен быть тот же домен, который указан в записи узлов DNS (A).</span><span class="sxs-lookup"><span data-stu-id="41446-p101">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed. When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool. For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value. This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="41446-114">Щелкните правой кнопкой мыши выбранный домен, а затем выберите пункт **Другие новые записи**.</span><span class="sxs-lookup"><span data-stu-id="41446-114">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="41446-115">В разделе **Тип записи ресурса** выберите **Расположение службы (запись SRV)**, а затем нажмите **Создать запись**.</span><span class="sxs-lookup"><span data-stu-id="41446-115">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="41446-116">В **новой записи ресурса**щелкните **Служба**и введите \*\* \_ сипфедератионтлс\*\*.</span><span class="sxs-lookup"><span data-stu-id="41446-116">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="41446-117">Щелкните **протокол**, а затем введите \*\* \_ TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="41446-117">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="41446-118">Нажмите **Номер порта** и введите **5061**.</span><span class="sxs-lookup"><span data-stu-id="41446-118">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="41446-119">Щелкните **узел, предоставляющий эту службу**, а затем введите полное доменное имя (FQDN) пограничного пула lync Server 2013, который предоставляет доступ к системе lync Server 2013 для доверенных внешних клиентов.</span><span class="sxs-lookup"><span data-stu-id="41446-119">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="41446-120">Этот домен также должен быть настроен в параметрах Exchange Online как заслуживающий доверия обслуживающий домен.</span><span class="sxs-lookup"><span data-stu-id="41446-120">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="41446-121">Для получения дополнительных сведений обратитесь к разделу Создание обслуживаемых доменов на сайте <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> .</span><span class="sxs-lookup"><span data-stu-id="41446-121">For details, see Create Accepted Domains at <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="41446-122">Нажмите кнопку **ОК**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="41446-122">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="41446-123">Проверка успешности создания записи SRV DNS</span><span class="sxs-lookup"><span data-stu-id="41446-123">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="41446-124">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="41446-124">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="41446-125">Нажмите кнопку **Пуск** и выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="41446-125">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="41446-126">В командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="41446-126">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="41446-127">Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="41446-127">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41446-128">См. также</span><span class="sxs-lookup"><span data-stu-id="41446-128">See Also</span></span>


[<span data-ttu-id="41446-129">Создание записей DNS для обратных прокси-серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41446-129">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

