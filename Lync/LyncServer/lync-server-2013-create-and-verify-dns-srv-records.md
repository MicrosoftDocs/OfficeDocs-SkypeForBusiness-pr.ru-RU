---
title: 'Lync Server 2013: создание и проверка записей DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f56b2c406a14a6a1781705017d13d8b823472c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="b976b-102">Создание и проверка записей DNS SRV в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b976b-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b976b-103">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b976b-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b976b-104">Чтобы успешно выполнить данную процедуру, вы должны войти на сервер или в домен хотя бы в качестве члена группы администраторов домена или группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="b976b-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="b976b-105">В этом разделе описывается, как настроить записи службы доменных имен (DNS), необходимые для создания в среде Lync Server 2013, и те, которые необходимы для автоматического входа клиента.</span><span class="sxs-lookup"><span data-stu-id="b976b-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="b976b-106">При создании пула переднего плана программа установки создает объекты и параметры Active Directory для пула, включая полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="b976b-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="b976b-107">Аналогичные объекты и параметры создаются для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b976b-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="b976b-108">Чтобы клиенты могли подключаться к пулу или серверу Standard Edition, необходимо зарегистрировать полное доменное имя пула или сервера Standard Edition в DNS.</span><span class="sxs-lookup"><span data-stu-id="b976b-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="b976b-109">Вам следует создать DNS-записи SRV во внутренней DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="b976b-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="b976b-110">В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="b976b-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="b976b-111">Настройка DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="b976b-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="b976b-112">На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b976b-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="b976b-113">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен SIP, в котором будет установлен сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b976b-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="b976b-114">Щелкните элемент **Other New Records** (Другие новые записи).</span><span class="sxs-lookup"><span data-stu-id="b976b-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="b976b-115">В разделе **Выбор типа записи ресурса** выберите **Service Location (SRV) (Расположение службы (запись SRV))**, а затем нажмите кнопку **Создать запись**.</span><span class="sxs-lookup"><span data-stu-id="b976b-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="b976b-116">Выберите пункт **Служба**и введите \*\* \_сипинтерналтлс\*\*.</span><span class="sxs-lookup"><span data-stu-id="b976b-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="b976b-117">Щелкните **протокол**, а затем введите \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="b976b-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="b976b-118">Нажмите **Номер порта** и введите **5061**.</span><span class="sxs-lookup"><span data-stu-id="b976b-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="b976b-119">Щелкните **узел, предоставляющий эту службу**, а затем введите полное доменное имя пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b976b-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="b976b-120">Нажмите кнопку **ОК**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="b976b-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="b976b-121">Проверка создания DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="b976b-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="b976b-122">Выполните вход на клиентский компьютер с использованием учетной записи, которая является членом группы прошедших проверку пользователей или имеет эквивалентные разрешения.</span><span class="sxs-lookup"><span data-stu-id="b976b-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="b976b-123">Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b976b-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="b976b-124">В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b976b-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="b976b-125">Введите **nslookup** в командной строке, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b976b-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="b976b-126">Введите **set type=srv**, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b976b-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="b976b-127">Введите \*\* \_сипинтерналтлс.\_ tcp.contoso.com\*\*, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b976b-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="b976b-128">Для записи TLS отображаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="b976b-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="b976b-129">Сервер: \<DNS server\>. contoso.com</span><span class="sxs-lookup"><span data-stu-id="b976b-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="b976b-130">Адрес: \<IP-адрес DNS-сервера\></span><span class="sxs-lookup"><span data-stu-id="b976b-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="b976b-131">Неофициальный ответ:</span><span class="sxs-lookup"><span data-stu-id="b976b-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="b976b-132">\_сипинтерналтлс. \_расположение службы TCP.contoso.com SRV:</span><span class="sxs-lookup"><span data-stu-id="b976b-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="b976b-133">приоритет = 0</span><span class="sxs-lookup"><span data-stu-id="b976b-133">priority = 0</span></span>
    
    <span data-ttu-id="b976b-134">Вес = 0</span><span class="sxs-lookup"><span data-stu-id="b976b-134">weight = 0</span></span>
    
    <span data-ttu-id="b976b-135">порт = 5061</span><span class="sxs-lookup"><span data-stu-id="b976b-135">port = 5061</span></span>
    
    <span data-ttu-id="b976b-136">SVR hostname = poolname.contoso.com (или запись сервера Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="b976b-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="b976b-137">poolname.contoso.com Интернет-адрес \<= виртуальный IP-\> адрес подсистемы балансировки \<нагрузки или IP-адреса одного сервера Enterprise Edition для пулов с одним сервером Enterprise Edition\> или \<IP-адресом сервера Standard Edition.\></span><span class="sxs-lookup"><span data-stu-id="b976b-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="b976b-138">По завершении введите **exit** в командной строке и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b976b-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="b976b-139">Проверка возможности разрешения для полного доменного имени интерфейсного пула или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b976b-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="b976b-140">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="b976b-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="b976b-141">Нажмите кнопку **Пуск** и затем щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="b976b-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="b976b-142">В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b976b-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="b976b-143">В командной строки введите **nslookup** \<FQDN переднего плана\> или \<полное доменное имя сервера\>Standard Edition, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="b976b-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="b976b-144">Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="b976b-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

