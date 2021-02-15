---
title: Изменение топологии в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: После завершения вопросов о начальном собеседовании можно изменить полное доменное имя и IP-адреса сайта. Для этого дважды щелкните сайт, который нужно изменить, на странице "Глобальная топология".
ms.openlocfilehash: ba18070b21494028d31b4167ab92a622794c5e51
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834889"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="3cde8-104">Изменение топологии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3cde8-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="3cde8-105">После завершения вопросов о начальном собеседовании можно изменить полное доменное имя и IP-адреса сайта.</span><span class="sxs-lookup"><span data-stu-id="3cde8-105">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="3cde8-106">Для этого дважды  щелкните сайт, который нужно изменить, на странице "Глобальная топология".</span><span class="sxs-lookup"><span data-stu-id="3cde8-106">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="3cde8-107">Средство планирования отображает топологию выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="3cde8-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="3cde8-108">В нижней части страницы сайта находятся четыре вкладки:</span><span class="sxs-lookup"><span data-stu-id="3cde8-108">At the bottom of the site page are four tabs:</span></span>

![Топология сайта средства планирования](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="3cde8-110">Топология сайта — отображаемая в настоящее время страница с визуальным обзором топологии, как рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="3cde8-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="3cde8-111">Схема сети по краям . На странице схемы сети по краям конструктор делает большую часть работы в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="3cde8-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="3cde8-112">На схеме показана конфигурация сети для рекомендуемой топологии Skype для бизнеса Server 2015 с редактируемыми записями для IP-адресов и FQDNs для серверов, пулов, а также аппаратных и DNS-балансизов.</span><span class="sxs-lookup"><span data-stu-id="3cde8-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="3cde8-113">Отчет об администрировании edge : отчет об администрировании по краям содержит четыре отчета:</span><span class="sxs-lookup"><span data-stu-id="3cde8-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Страница отчета об администрировании edge](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="3cde8-115">Сводный отчет — общий отчет о параметрах конфигурации сети edge.</span><span class="sxs-lookup"><span data-stu-id="3cde8-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="3cde8-116">Если изменить значения на  странице схемы сети в топологию TCP/IP и значения FQDN, которые будут использоваться в фактическом развертывании, эти адреса и имена будут представлены здесь.</span><span class="sxs-lookup"><span data-stu-id="3cde8-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="3cde8-117">В противном случае появится текст по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cde8-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="3cde8-118">Отчет по сертификатам — в отчете по сертификатам перечисляются имена субъектов и альтернативные имена субъектов для сертификатов, необходимых для топологии.</span><span class="sxs-lookup"><span data-stu-id="3cde8-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="3cde8-119">Отчет по брандмауэру. В отчете о брандмауэре перечислены сведения, необходимые для настройки брандмауэров периметра в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="3cde8-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="3cde8-120">К ним относятся IP-адреса (значения по умолчанию или измененные), роль сервера, исходный IP-адрес и порт, ip-адрес назначения и порт, транспортный протокол, протокол приложения и соответствующие примечания.</span><span class="sxs-lookup"><span data-stu-id="3cde8-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="3cde8-121">Отчет DNS . В отчете DNS перечислены важные сведения о записях DNS, которые необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="3cde8-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="3cde8-122">Включаются тип записи, FQDN, IP-адрес и комментарии, необходимые для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="3cde8-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="3cde8-123">Сводка по сайту — в сводке по сайтам представлен обзор выбора, который вы сделали, ответив на вопросы начального собеседования или заполнив значения в **сайте разработки.**</span><span class="sxs-lookup"><span data-stu-id="3cde8-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="3cde8-124">Также представлены сведения о емкости.</span><span class="sxs-lookup"><span data-stu-id="3cde8-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3cde8-125">Сведения на странице сводки сайта настраиваются для каждого проекта и могут содержать не все разделы или сведения, подробные здесь.</span><span class="sxs-lookup"><span data-stu-id="3cde8-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="3cde8-126">Изменение схемы конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="3cde8-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="3cde8-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="3cde8-127"><a name="Edit_Network_diagram"> </a></span></span>

<span data-ttu-id="3cde8-128">Большая часть работы, которую разработчик делает в средстве планирования Skype для бизнеса Server 2015, состоит в определении записей для IP-адресов и полного доменного имени для записей на сетевой схеме.</span><span class="sxs-lookup"><span data-stu-id="3cde8-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="3cde8-129">Информация, введенная на этой странице, передается в отчеты и другие сведения, содержащиеся в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="3cde8-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Схема сети средства планирования](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="3cde8-131">Средство планирования создает сетевую схему с текстом по умолчанию для IP-адресов и FQDNs.</span><span class="sxs-lookup"><span data-stu-id="3cde8-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="3cde8-132">Изменение сетевой схемы и входных значений:</span><span class="sxs-lookup"><span data-stu-id="3cde8-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="3cde8-133">Выберите раздел сети для начала работы.</span><span class="sxs-lookup"><span data-stu-id="3cde8-133">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="3cde8-134">Например, дважды щелкните текст, **access1.contoso.com.**</span><span class="sxs-lookup"><span data-stu-id="3cde8-134">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="3cde8-135">В открываемом диалоговом окне введите фактическое FQDN сервера access1.contoso.com и фактический IP-адрес, заменив 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="3cde8-135">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="3cde8-136">Нажмите **кнопку** "ОК", чтобы сохранить записи.</span><span class="sxs-lookup"><span data-stu-id="3cde8-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="3cde8-137">Продолжайте изменять IP-адреса и FQDNs, предоставляя виртуальные IP-адреса для аппаратных балансировщиков нагрузки или записи серверов для балансировки нагрузки DNS для серверов в пулах.</span><span class="sxs-lookup"><span data-stu-id="3cde8-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="3cde8-138">Полезная функция средства планирования состоит в том, что оно может постепенно назначать диапазон IP-адресов и имен серверов, а не требовать от разработчика изменять каждый отдельный сервер в пуле.</span><span class="sxs-lookup"><span data-stu-id="3cde8-138">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool.</span></span> <span data-ttu-id="3cde8-139">Пример:</span><span class="sxs-lookup"><span data-stu-id="3cde8-139">For example:</span></span>

1. <span data-ttu-id="3cde8-140">Дважды щелкните пульные серверы переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="3cde8-140">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="3cde8-141">Когда откроется диалоговое окно, выберите "Использовать ли вы IPS и FQDN в качестве отправной точки для всех эквивалентных серверов **в этом кластере?".**</span><span class="sxs-lookup"><span data-stu-id="3cde8-141">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="3cde8-142">Например, начальным значением для первого сервера является fe0101.contoso.com IP-адрес 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="3cde8-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="3cde8-143">Введите fe0.contoso.com в **FQDN** сервера переднего сервера, введите 192.168.21.131 в **IP-адресе** сервера переднего сервера, а затем нажмите кнопку **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="3cde8-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="3cde8-144">Функция автоматического приращения обновляет все серверы в пуле до версии fe01–fe06 и все IP-адреса с 192.168.21.131 до 136.</span><span class="sxs-lookup"><span data-stu-id="3cde8-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="3cde8-145">После завершения всех изменений сохраните топологию, выполив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3cde8-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="3cde8-146">Чтобы сохранить проект средства планирования, щелкните **"Файл"** и выберите **"Сохранить** топологию" или "Сохранить **топологию как".**</span><span class="sxs-lookup"><span data-stu-id="3cde8-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="3cde8-147">Если **появится диалоговое** окно "Сохранить средство планирования как", введите имя файла в имени файла **и** нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="3cde8-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cde8-148">См. также</span><span class="sxs-lookup"><span data-stu-id="3cde8-148">See also</span></span>
<span data-ttu-id="3cde8-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="3cde8-149"><a name="Edit_Network_diagram"> </a></span></span>

[<span data-ttu-id="3cde8-150">Редактирование проекта</span><span class="sxs-lookup"><span data-stu-id="3cde8-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
