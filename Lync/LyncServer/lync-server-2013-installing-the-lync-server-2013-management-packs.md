---
title: 'Lync Server 2013: Установка пакетов управления Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2a6cd3ca0c58a6101d6e46e253e3edf09dec025
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="46892-102">Установка пакетов управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46892-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46892-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="46892-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="46892-104">У System Center Operations Manager есть возможность отслеживать только небольшую часть операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="46892-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="46892-105">Однако вы можете расширить возможности System Center Operations Manager, устанавливая пакеты управления, программное обеспечение, которое определяет, какие элементы будут отслеживаться с помощью System Center Operations Manager, в том числе способ отслеживания этих элементов и способ оповещения активировано и отправлено.</span><span class="sxs-lookup"><span data-stu-id="46892-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="46892-106">Microsoft Lync Server 2013 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="46892-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="46892-107">Пакет управления компонентом и пользовательским пакетом (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) отслеживает проблемы Lync Server, записанные в журналах событий, зарегистрированные счетчиками производительности или записанные в записи сведений о вызовах (CDR) или качества взаимодействия (QoE). базы.</span><span class="sxs-lookup"><span data-stu-id="46892-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="46892-108">Для критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов с помощью электронной почты, обмена мгновенными сообщениями или обмена сообщениями в службе коротких сообщений (SMS).</span><span class="sxs-lookup"><span data-stu-id="46892-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="46892-109">(SMS или Short Message Service — это технология, которая используется для отправки текстовых сообщений с одного мобильного устройства на другое.)</span><span class="sxs-lookup"><span data-stu-id="46892-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46892-110">Дополнительные сведения о настройке уведомлений Operations Manager содержатся в разделе Настройка уведомлений в библиотеке TechNet по <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>адресу.</span><span class="sxs-lookup"><span data-stu-id="46892-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="46892-111">Активный пакет мониторинга (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) проактивно тестирует ключевые компоненты Lync Server, такие как вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся на телефон общедоступной коммутации сеть (PSTN).</span><span class="sxs-lookup"><span data-stu-id="46892-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="46892-112">Эти тесты выполняются с помощью командлетов искусственной транзакции Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46892-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="46892-113">Например, командлет **Test-CsIM** имитирует сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="46892-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="46892-114">Если тестовый сеанс заканчивается с ошибкой, то создается оповещение.</span><span class="sxs-lookup"><span data-stu-id="46892-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="46892-115">В число двух пакетов управления, включенных в Lync Server 2013, входит большое количество улучшений по сравнению с пакетами управления, используемыми с Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="46892-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="46892-116">Например, пакет управления Lync Server 2013 Component не ограничивается только мониторингом сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46892-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="46892-117">В дополнение к мониторингу журналов событий и счетчиков производительности для Lync Server пакет управления Components также может отслеживать производительность и выдачу оповещений для критически важных элементов, таких как:</span><span class="sxs-lookup"><span data-stu-id="46892-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="46892-118">\*\*\*\*   Если службы IIS переводятся в автономный режим, будут выдаваться оповещения служб IIS.</span><span class="sxs-lookup"><span data-stu-id="46892-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="46892-119">Это важно, так как веб-службы Lync Server основываются на службах IIS.</span><span class="sxs-lookup"><span data-stu-id="46892-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="46892-120">**Оповещения об использовании**   процессов будут выдаваться, если системные ресурсы (например, доступная память) начинают работать с нехваткой.</span><span class="sxs-lookup"><span data-stu-id="46892-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="46892-121">Эти оповещения будут выдаваться, даже если Lync Server не отвечает за высокую загрузку системы.</span><span class="sxs-lookup"><span data-stu-id="46892-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="46892-122">**События сбоя компьютера**   оповещения будут выдаваться в случае проблемы аппаратного или программного обеспечения, которая может угрожать жизнеспособность сервера.</span><span class="sxs-lookup"><span data-stu-id="46892-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="46892-123">Например, администраторы Lync Server будут уведомлены, если на сервере возникла опасность сбоя жесткого диска.</span><span class="sxs-lookup"><span data-stu-id="46892-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="46892-124">В новых пакетах управления также были расширены функции создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="46892-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="46892-125">Новые отчеты для Lync Server 2013 включают:</span><span class="sxs-lookup"><span data-stu-id="46892-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="46892-126">**Отчет о доступности сценария**   "до конца" в этом отчете подробно описывается доступность и время работы для ключевых служб Lync Server, таких как регистрация или присутствие.</span><span class="sxs-lookup"><span data-stu-id="46892-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="46892-127">**Отчет о емкости**   с использованием данных счетчиков производительности этот отчет показывает тенденции для компонентов системы, таких как доступность памяти и загрузка процессора.</span><span class="sxs-lookup"><span data-stu-id="46892-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="46892-128">**Отчет о**   компонентах в этом отчете перечислены Топ генераторов оповещений, сгруппированных по компонентам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="46892-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="46892-129">В дополнение к этим предназначенным отчетам пакеты управления для Lync Server 2013 автоматически отчитываются об оповещениях для надежности (метрики, измеряемые при регистрации вызовов) и состояния QoE (метрики измеряются качеством взаимодействия).</span><span class="sxs-lookup"><span data-stu-id="46892-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="46892-130">Если вы включили запись сведений о вызовах, вы можете просмотреть оповещения о надежности вызовов, выполнив следующую процедуру в консоли System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="46892-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="46892-131">Последовательно разверните узлы **Monitoring**, **Microsoft Lync Server 2013 Health** (Работоспособность Microsoft Lync Server 2013), **Call Reliability and Media Quality** (Стабильность звонков и качество медиаданных) и щелкните **Call Reliability** (Стабильность звонков).</span><span class="sxs-lookup"><span data-stu-id="46892-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="46892-132">Чтобы просмотреть оповещения о качестве качества взаимодействия, выполните эту процедуру в консоли System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="46892-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="46892-133">Последовательно разверните узлы **Monitoring**, **Microsoft Lync Server 2013 Health**, **Call Reliability and Media Quality** и **Media Quality** (Качество медиаданных).</span><span class="sxs-lookup"><span data-stu-id="46892-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="46892-134">Пакеты управления для Lync Server 2013 теперь используют обнаружение на уровне компьютера вместо централизованного механизма обнаружения, используемого в Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="46892-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="46892-135">Это означает, что каждый агент System Center в основном обнаруживает себя и сообщает о существовании сервера центрального управления.</span><span class="sxs-lookup"><span data-stu-id="46892-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="46892-136">Использование обнаружения на уровне компьютера упрощает администрирование инфраструктуры System Center, а также позволяет различным версиям пакетов управления Lync Server (например, пакетов управления для Lync Server 2010 и пакетов управления для Lync Server 2013). совместим.</span><span class="sxs-lookup"><span data-stu-id="46892-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

