---
title: Изменение топологии в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: После ответа на вопросы начального опроса вы можете изменить полное доменное имя и IP-адреса сайта. Для этого на странице Global Topology (Глобальная топология) дважды щелкните сайт, который хотите изменить.
ms.openlocfilehash: 9dcc8f2f69843de5d824ad3df614631ea0d50c20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915061"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a><span data-ttu-id="ed210-104">Edit the topology in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ed210-104">Edit the topology in Skype for Business Server 2015</span></span>

<span data-ttu-id="ed210-p102">После ответа на вопросы начального опроса вы можете изменить полное доменное имя и IP-адреса сайта. Для этого на странице **Global Topology** (Глобальная топология) дважды щелкните сайт, который хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="ed210-p102">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="ed210-107">Средство планирования отображает топологии сайтов для выбранного сайта.</span><span class="sxs-lookup"><span data-stu-id="ed210-107">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="ed210-108">At the bottom of the site page are four tabs:</span><span class="sxs-lookup"><span data-stu-id="ed210-108">At the bottom of the site page are four tabs:</span></span>

![Топология узлов в средстве планирования](../../media/Planning_Tool_Site_Topology.png)

- <span data-ttu-id="ed210-110">Топология сайта — текущей отображаемой страницы с визуальный Обзор топологии, в соответствии с рекомендациями.</span><span class="sxs-lookup"><span data-stu-id="ed210-110">Site Topology - The currently displayed page with a visual overview of the topology as recommended.</span></span>

- <span data-ttu-id="ed210-111">Edge сетевой график - страница сетевой график пограничного сервера, где конструктор выполняет большую часть работы в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="ed210-111">Edge Network Diagram - The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="ed210-112">Редактируемые записи для IP-адресов адреса и полные доменные имена серверов, пул и как оборудования и доменных имен (DNS) загрузки подсистемы балансировки, схему конфигурация сети для рекомендуемые Скайп для топологии Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ed210-112">The diagram displays the network configuration for a recommended Skype for Business Server 2015 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

- <span data-ttu-id="ed210-113">Отчет администратора пограничного сервера - отчет для администратора пограничного сервера содержит всего четыре отчета:</span><span class="sxs-lookup"><span data-stu-id="ed210-113">Edge Admin Report - The Edge Admin Report contains a total of four reports:</span></span>

     ![Страница отчета по пограничным серверам для администратора](../../media/Planning_Tool_Summary_Report.png)

  - <span data-ttu-id="ed210-115">Сводный отчет - отчете Общие параметры для сетевой конфигурации пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="ed210-115">Summary Report - A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="ed210-116">Если вы измените значения на странице **Схема сети периметра** на значения TCP/IP и полного доменного имени топологии, которые будут использоваться в фактическом развертывании, эти адреса и имена будут представлены здесь.</span><span class="sxs-lookup"><span data-stu-id="ed210-116">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="ed210-117">В противном случае отображается стандартный текст.</span><span class="sxs-lookup"><span data-stu-id="ed210-117">Otherwise, the default text will appear.</span></span>

  - <span data-ttu-id="ed210-118">О сертификат - отчет сертификата будут перечислены имя субъекта и альтернативные имена субъекта для сертификатов, которые необходимы для создания топологии.</span><span class="sxs-lookup"><span data-stu-id="ed210-118">Certificate Report - The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>

  - <span data-ttu-id="ed210-119">Отчет брандмауэра - отчет брандмауэра приведены сведения, необходимые для настройки брандмауэров периметра в инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="ed210-119">Firewall Report - The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="ed210-120">Сюда относятся IP-адреса (со значениями по умолчанию или измененными значениями), роль сервера, исходный IP-адрес и порт, конечный IP-адрес и порт, транспортный протокол, протокол приложений и соответствующие заметки.</span><span class="sxs-lookup"><span data-stu-id="ed210-120">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>

  - <span data-ttu-id="ed210-121">Отчет по DNS - отчет DNS приведены соответствующие сведения для записи DNS, которые необходимо создать.</span><span class="sxs-lookup"><span data-stu-id="ed210-121">DNS Report - The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="ed210-122">В эту информацию входит тип записи, полное доменное имя, IP-адрес, а также комментарии, касающиеся обеспечения правильной работы.</span><span class="sxs-lookup"><span data-stu-id="ed210-122">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

- <span data-ttu-id="ed210-123">Сводка по веб - сайта Сводка содержит обзор выбором, внесенных путем ответы на вопросы начальной собеседования или заполнение значений на **Сайтах разработки**.</span><span class="sxs-lookup"><span data-stu-id="ed210-123">Site Summary - The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="ed210-124">Кроме того, приводится информация о мощности.</span><span class="sxs-lookup"><span data-stu-id="ed210-124">Capacity information is also presented.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ed210-125">Информация на странице "Site Summary" (Сводка сайта) настраивается для каждой конкретной структуры и может не содержать всех тех разделов или сведений, которые перечислены здесь.</span><span class="sxs-lookup"><span data-stu-id="ed210-125">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

## <a name="edit-the-network-configuration-diagram"></a><span data-ttu-id="ed210-126">Изменение схемы конфигурации сети</span><span class="sxs-lookup"><span data-stu-id="ed210-126">Edit the network configuration diagram</span></span>
<span data-ttu-id="ed210-127"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="ed210-127"></span></span>

<span data-ttu-id="ed210-128">Большая часть работы, которая выполняет конструктор в Скайп для средство планирования Business Server 2015 состоит в определении записи для IP-адресов и полные доменные имена (FQDN) для записи сетевого графика.</span><span class="sxs-lookup"><span data-stu-id="ed210-128">Most of the work that a designer does in the Skype for Business Server 2015 Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="ed210-129">Сведения, введенные на этой странице переносится в отчеты и другие сведения, содержащиеся в средстве планирования.</span><span class="sxs-lookup"><span data-stu-id="ed210-129">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

![Сеть в средстве планирования (схема)](../../media/Planning_Tool_Network_Diagram.png)

<span data-ttu-id="ed210-131">Средство планирования создается сетевой график с текст по умолчанию для IP-адресов и полных доменных имен.</span><span class="sxs-lookup"><span data-stu-id="ed210-131">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="ed210-132">Изменение схемы сети и входных значений:</span><span class="sxs-lookup"><span data-stu-id="ed210-132">To edit the network diagram and input values:</span></span>

1. <span data-ttu-id="ed210-p110">Выберите раздел сети, работу над которым хотите начать. Например, дважды щелкните текст **access1.contoso.com**. В открывшемся диалоговом окне введите фактическое полное доменное имя сервера access1.contoso.com и фактически IP-адрес, заменив значение 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="ed210-p110">Choose a section of the network to begin working on. For example, double-click the text, **access1.contoso.com**. In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2. <span data-ttu-id="ed210-136">Нажмите кнопку **OK** (ОК), чтобы сохранить записи.</span><span class="sxs-lookup"><span data-stu-id="ed210-136">Click **OK** to save the entries.</span></span>

3. <span data-ttu-id="ed210-137">Продолжайте изменять IP-адреса и полные доменные имена, указывая виртуальные IP-адреса для устройств балансировки нагрузки или записи сервера для подсистемы балансировки нагрузки службы доменных имен (DNS) для серверов в пулах.</span><span class="sxs-lookup"><span data-stu-id="ed210-137">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="ed210-p111">Удобной особенность средства планирования является то, что оно может поэтапно назначать диапазон IP-адресов и имен узла сервера, не требуя от проектировщика изменения каждого отдельного сервера в пуле. Например:</span><span class="sxs-lookup"><span data-stu-id="ed210-p111">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1. <span data-ttu-id="ed210-p112">Дважды щелкните входящие в состав пула серверы переднего плана. После открытия диалогового окна выберите элемент **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?** (Использовать IP-адреса и полное доменное имя в качестве исходных точек для всех эквивалентных серверов в этом кластере?).</span><span class="sxs-lookup"><span data-stu-id="ed210-p112">Double-click the pooled Front End Servers. When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2. <span data-ttu-id="ed210-142">Например, начальное значение для первого сервера: fe0101.contoso.com и IP-адрес 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="ed210-142">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3. <span data-ttu-id="ed210-143">Введите значение fe0.contoso.com в поле **Front End Server FQDN** (Полное доменное имя сервера переднего плана), введите значение 192.168.21.131 в поле **Front End Server IP address** (IP-адрес сервера переднего плана), а затем нажмите кнопку **OK** (ОК).</span><span class="sxs-lookup"><span data-stu-id="ed210-143">Type fe0.contoso.com in **Front End Server FQDN**, type 192.168.21.131 in **Front End Server IP address**, and then click **OK**.</span></span>

4. <span data-ttu-id="ed210-144">Компонент автоматического приращения обновляет все серверы в пуле с fe01 по fe06 и все IP-адреса с 192.168.21.131 по 136.</span><span class="sxs-lookup"><span data-stu-id="ed210-144">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="ed210-145">После внесения всех правок сохраните топологию, выполнив следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ed210-145">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="ed210-146">Чтобы сохранить средство планирования проекта, откройте меню **файл**и нажмите кнопку **Топологии сохранить** или **Сохранить топологию как**.</span><span class="sxs-lookup"><span data-stu-id="ed210-146">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="ed210-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="ed210-147">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed210-148">См. также</span><span class="sxs-lookup"><span data-stu-id="ed210-148">See also</span></span>
<span data-ttu-id="ed210-149"><a name="Edit_Network_diagram"> </a></span><span class="sxs-lookup"><span data-stu-id="ed210-149"></span></span>

[<span data-ttu-id="ed210-150">Editing the Design</span><span class="sxs-lookup"><span data-stu-id="ed210-150">Editing the Design</span></span>](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
