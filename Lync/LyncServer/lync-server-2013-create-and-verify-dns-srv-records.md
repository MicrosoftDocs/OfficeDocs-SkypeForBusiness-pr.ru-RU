---
title: 'Lync Server 2013: создание и проверка записей DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a539b58abbad323aaf7c7343b40eabb49d04d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="57068-102">Создание и проверка записей DNS SRV в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57068-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57068-103">_**Тема последнего изменения:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="57068-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="57068-104">Для успешного выполнения этой процедуры необходимо войти в систему на сервере или в домене в группу администраторов домена или в группу пользователей Днсадминс.</span><span class="sxs-lookup"><span data-stu-id="57068-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="57068-105">В этой статье описано, как настроить записи DNS, необходимые для автоматического входа в Lync Server 2013, и те, которые необходимы для автоматической регистрации клиента.</span><span class="sxs-lookup"><span data-stu-id="57068-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="57068-106">При создании пула переднего плана программа установки создает объекты Active Directory и параметры для пула, включая полное доменное имя пула (FQDN).</span><span class="sxs-lookup"><span data-stu-id="57068-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="57068-107">Аналогичные объекты и параметры создаются для сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="57068-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="57068-108">Чтобы клиенты смогли подключиться к серверу пула или стандарту Standard Edition, в DNS должны быть зарегистрированы полные доменные имена для пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="57068-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="57068-109">Вы должны создать записи DNS SRV во внутренней DNS для каждого домена SIP.</span><span class="sxs-lookup"><span data-stu-id="57068-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="57068-110">В этой процедуре предполагается, что в вашей внутренней DNS-зоне есть зоны для доменов пользователей SIP.</span><span class="sxs-lookup"><span data-stu-id="57068-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="57068-111">Настройка DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="57068-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="57068-112">На DNS-сервере нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.</span><span class="sxs-lookup"><span data-stu-id="57068-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="57068-113">В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**, а затем щелкните правой кнопкой мыши домен SIP, в котором будет установлен Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="57068-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="57068-114">Нажмите кнопку **другие новые записи**.</span><span class="sxs-lookup"><span data-stu-id="57068-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="57068-115">В разделе **Выбор типа записи ресурса** выберите **Обнаружение службы (запись SRV)**, а затем нажмите кнопку **Создать запись**.</span><span class="sxs-lookup"><span data-stu-id="57068-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="57068-116">Выберите пункт **Служба**, а затем введите \*\* \_сипинтерналтлс\*\*.</span><span class="sxs-lookup"><span data-stu-id="57068-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="57068-117">Выберите **протокол**и введите \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="57068-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="57068-118">Нажмите **Номер порта** и введите значение **5061**.</span><span class="sxs-lookup"><span data-stu-id="57068-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="57068-119">Нажмите **Узел этой службы** и введите полное доменное имя пула или сервера Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="57068-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="57068-120">Нажмите **ОК**, а затем нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="57068-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="57068-121">Проверка создания DNS-записи SRV</span><span class="sxs-lookup"><span data-stu-id="57068-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="57068-122">Выполните вход на клиентский компьютер с использованием учетной записи, которая является членом группы прошедших проверку пользователей или имеет эквивалентные разрешения.</span><span class="sxs-lookup"><span data-stu-id="57068-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="57068-123">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="57068-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="57068-124">В поле **Открыть** введите **cmd**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="57068-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="57068-125">В командной строке введите **nslookup**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="57068-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="57068-126">Введите **Set Type = SRV**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="57068-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="57068-127">Введите \*\* \_сипинтерналтлс.\_ tcp.contoso.com\*\*, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="57068-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="57068-128">Ниже указаны выходные данные, отображаемые для записи протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="57068-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="57068-129">Сервер: \<DNS-\>Server. contoso.com</span><span class="sxs-lookup"><span data-stu-id="57068-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="57068-130">Адрес: \<IP-адрес DNS-сервера\></span><span class="sxs-lookup"><span data-stu-id="57068-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="57068-131">Неофициальный ответ:</span><span class="sxs-lookup"><span data-stu-id="57068-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="57068-132">\_сипинтерналтлс. \_расположение службы TCP.contoso.com SRV:</span><span class="sxs-lookup"><span data-stu-id="57068-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="57068-133">Priority (приоритет) = 0</span><span class="sxs-lookup"><span data-stu-id="57068-133">priority = 0</span></span>
    
    <span data-ttu-id="57068-134">Вес = 0</span><span class="sxs-lookup"><span data-stu-id="57068-134">weight = 0</span></span>
    
    <span data-ttu-id="57068-135">порт = 5061</span><span class="sxs-lookup"><span data-stu-id="57068-135">port = 5061</span></span>
    
    <span data-ttu-id="57068-136">SVR hostname = poolname.contoso.com (или стандартный сервер выпуска A Record)</span><span class="sxs-lookup"><span data-stu-id="57068-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="57068-137">poolname.contoso.com Internet address = \<виртуальный IP-адрес подсистемы балансировки\> нагрузки \<или IP-адреса одного сервера Enterprise Edition для пулов только с одним сервером\> выпуска Enterprise Edition \<или IP-адресом стандартного Выиздание сервера\></span><span class="sxs-lookup"><span data-stu-id="57068-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="57068-138">Когда все будет готово, в командной строке введите **Exit**и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="57068-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="57068-139">Проверка возможности разрешения полных доменных имен в пуле или сервере Standard Edition</span><span class="sxs-lookup"><span data-stu-id="57068-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="57068-140">Войдите в домен на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="57068-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="57068-141">В меню **Пуск** выберите пункт **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="57068-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="57068-142">В поле **Открыть** введите **cmd**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="57068-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="57068-143">В командной строке введите **nslookup** \<FQDN для пула\> переднего плана или \<полное доменное имя сервера\>Standard Edition, а затем нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="57068-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="57068-144">Убедитесь в том, что вы получили ответ на соответствующий IP-адрес для полного доменного имени.</span><span class="sxs-lookup"><span data-stu-id="57068-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

