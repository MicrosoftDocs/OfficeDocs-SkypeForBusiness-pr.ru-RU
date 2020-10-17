---
title: 'Lync Server 2013: создание и проверка записей DNS SRV'
description: 'Lync Server 2013: создание и проверка записей DNS SRV.'
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
ms.openlocfilehash: a71c876d0b26b9305feed7146fa6321a3983588d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562385"
---
# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="5af89-103">Создание и проверка записей DNS SRV в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5af89-103">Create and verify DNS SRV records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5af89-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5af89-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5af89-105">Чтобы успешно выполнить данную процедуру, вы должны войти на сервер или в домен хотя бы в качестве члена группы администраторов домена или группы DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="5af89-105">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="5af89-106">В этом разделе описывается, как настроить записи службы доменных имен (DNS), необходимые для создания в среде Lync Server 2013, и те, которые необходимы для автоматического входа клиента.</span><span class="sxs-lookup"><span data-stu-id="5af89-106">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="5af89-107">При создании пула переднего плана программа установки создает объекты и параметры Active Directory для пула, включая полное доменное имя пула.</span><span class="sxs-lookup"><span data-stu-id="5af89-107">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="5af89-108">Аналогичные объекты и параметры создаются для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5af89-108">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="5af89-109">Чтобы клиенты могли подключаться к пулу или серверу Standard Edition, необходимо зарегистрировать полное доменное имя пула или сервера Standard Edition в DNS.</span><span class="sxs-lookup"><span data-stu-id="5af89-109">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="5af89-110">Вам следует создать DNS-записи SRV во внутренней DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="5af89-110">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="5af89-111">В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="5af89-111">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="5af89-112">Настройка DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="5af89-112">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="5af89-113">На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.</span><span class="sxs-lookup"><span data-stu-id="5af89-113">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="5af89-114">В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен SIP, в котором будет установлен сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5af89-114">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="5af89-115">Щелкните элемент **Other New Records** (Другие новые записи).</span><span class="sxs-lookup"><span data-stu-id="5af89-115">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="5af89-116">В разделе **Выбор типа записи ресурса** выберите **Service Location (SRV) (Расположение службы (запись SRV))**, а затем нажмите кнопку **Создать запись**.</span><span class="sxs-lookup"><span data-stu-id="5af89-116">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="5af89-117">Выберите пункт **Служба**и введите \*\* \_ сипинтерналтлс\*\*.</span><span class="sxs-lookup"><span data-stu-id="5af89-117">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="5af89-118">Щелкните **протокол**, а затем введите \*\* \_ TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="5af89-118">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="5af89-119">Нажмите **Номер порта** и введите **5061**.</span><span class="sxs-lookup"><span data-stu-id="5af89-119">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="5af89-120">Щелкните **узел, предоставляющий эту службу**, а затем введите полное доменное имя пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5af89-120">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="5af89-121">Нажмите кнопку **ОК**, а затем нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="5af89-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="5af89-122">Проверка создания DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="5af89-122">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="5af89-123">Выполните вход на клиентский компьютер с использованием учетной записи, которая является членом группы прошедших проверку пользователей или имеет эквивалентные разрешения.</span><span class="sxs-lookup"><span data-stu-id="5af89-123">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="5af89-124">Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5af89-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="5af89-125">В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5af89-125">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5af89-126">Введите **nslookup** в командной строке, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5af89-126">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="5af89-127">Введите **set type=srv**, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5af89-127">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="5af89-128">Введите \*\* \_ сипинтерналтлс. \_ tcp.contoso.com\*\*, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5af89-128">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="5af89-129">Для записи TLS отображаются следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="5af89-129">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="5af89-130">Сервер: \<dns server\> . contoso.com</span><span class="sxs-lookup"><span data-stu-id="5af89-130">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="5af89-131">Address \<IP address of DNS server\></span><span class="sxs-lookup"><span data-stu-id="5af89-131">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="5af89-132">Неофициальный ответ:</span><span class="sxs-lookup"><span data-stu-id="5af89-132">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="5af89-133">\_сипинтерналтлс. \_ расположение службы tcp.contoso.com SRV:</span><span class="sxs-lookup"><span data-stu-id="5af89-133">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="5af89-134">приоритет = 0</span><span class="sxs-lookup"><span data-stu-id="5af89-134">priority = 0</span></span>
    
    <span data-ttu-id="5af89-135">Вес = 0</span><span class="sxs-lookup"><span data-stu-id="5af89-135">weight = 0</span></span>
    
    <span data-ttu-id="5af89-136">порт = 5061</span><span class="sxs-lookup"><span data-stu-id="5af89-136">port = 5061</span></span>
    
    <span data-ttu-id="5af89-137">SVR hostname = poolname.contoso.com (или запись сервера Standard Edition)</span><span class="sxs-lookup"><span data-stu-id="5af89-137">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="5af89-138">адрес Интернета poolname.contoso.com = \<virtual IP Address of the load balancer\> или \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\>\<IP address of the Standard Edition server\></span><span class="sxs-lookup"><span data-stu-id="5af89-138">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="5af89-139">По завершении введите **exit** в командной строке и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5af89-139">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="5af89-140">Проверка возможности разрешения для полного доменного имени интерфейсного пула или сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="5af89-140">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="5af89-141">Войдите на клиентский компьютер в домене.</span><span class="sxs-lookup"><span data-stu-id="5af89-141">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="5af89-142">Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="5af89-142">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="5af89-143">В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5af89-143">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5af89-144">В командной строки введите **nslookup** \<FQDN of the Front End pool\> или и нажмите \<FQDN of the Standard Edition server\> клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="5af89-144">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="5af89-145">Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="5af89-145">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

