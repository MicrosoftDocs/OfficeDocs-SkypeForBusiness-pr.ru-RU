---
title: 'Lync Server 2013: Установка пакетов управления Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: nstalling the Lync Server 2013 management packs
ms:assetid: b800d4ab-fdc8-4c72-a76a-b78932779fe3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205202(v=OCS.15)
ms:contentKeyID: 48185233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fea443225744bfd0d0e2dfa90a317ffa4cc890ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-management-packs"></a><span data-ttu-id="6438c-102">Установка пакетов управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6438c-102">Installing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6438c-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6438c-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6438c-104">Сама по себе, System Center Operations Manager может отслеживать только небольшую часть операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="6438c-104">By itself, System Center Operations Manager has the ability to monitor only a small portion of the Windows operating system.</span></span> <span data-ttu-id="6438c-105">Однако вы можете расширять возможности System Center Operations Manager, устанавливая пакеты управления, программное обеспечение, которое определяет, какие элементы отслеживается System Center Operations Manager, в том числе сведения о том, как должны отслеживаться эти элементы и как должны быть оповещения. инициировано и отправлено.</span><span class="sxs-lookup"><span data-stu-id="6438c-105">However, you can extend the capabilities of System Center Operations Manager by installing management packs, software that dictates which items System Center Operations Manager can monitor, including how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="6438c-106">Microsoft Lync Server 2013 включает два пакета управления System Center Operations Manager, которые предоставляют следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="6438c-106">Microsoft Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="6438c-107">Пакет управления компонентом и пользовательским интерфейсом (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) отслеживает проблемы Lync Server, записанные счетчиками производительности, которые регистрируются в журналах событий или записываются в записи сведений о звонке (CDR) или в качестве его качества (QoE). баз данных.</span><span class="sxs-lookup"><span data-stu-id="6438c-107">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="6438c-108">Для критических проблем можно настроить System Center Operations Manager для немедленного уведомления администраторов с помощью электронной почты, обмена мгновенными сообщениями или службы коротких сообщений (SMS).</span><span class="sxs-lookup"><span data-stu-id="6438c-108">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="6438c-109">SMS — это технология, используемая для отправки текстовых сообщений с одного мобильного устройства на другое.</span><span class="sxs-lookup"><span data-stu-id="6438c-109">SMS is the technology used to send text messages from one mobile device to another.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6438c-110">Дополнительные сведения о настройке уведомлений Operations Manager можно найти в разделе Настройка уведомлений в библиотеке TechNet <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>по адресу.</span><span class="sxs-lookup"><span data-stu-id="6438c-110">For more information on configuring Operations Manager notification, see Configuring Notification in the TechNet Library at <A class=uri href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?linkid=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="6438c-111">Активный пакет мониторинга (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) проактивно проверяет ключевые компоненты сервера Lync, такие как вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся на коммутируемом телефоне Network (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="6438c-111">The Active Monitoring Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="6438c-112">Эти тесты выполняются с помощью виртуальных командлетов транзакций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6438c-112">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="6438c-113">Например, командлет **Test-CsIM** позволяет смоделировать сеанс обмена мгновенными сообщениями между двумя тестовыми пользователями.</span><span class="sxs-lookup"><span data-stu-id="6438c-113">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="6438c-114">Если имитируемый разговор о сообщениях завершается сбоем, будет создано предупреждение.</span><span class="sxs-lookup"><span data-stu-id="6438c-114">If this simulated messaging conversation fails an alert will be generated.</span></span>

<span data-ttu-id="6438c-115">В число двух пакетов управления, включенных в Lync Server 2013, входит большое количество улучшений по сравнению с пакетами управления, используемыми в Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6438c-115">The two management packs included with Lync Server 2013 include a large number of enhancements over the management packs used with Microsoft Lync Server 2010.</span></span> <span data-ttu-id="6438c-116">Например, пакет управления компонентом Lync Server 2013 не ограничивается только мониторингом сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6438c-116">For example, the Lync Server 2013 Component Management Pack is not limited to monitoring Lync Server itself.</span></span> <span data-ttu-id="6438c-117">В дополнение к мониторингу журналов событий и счетчиков производительности для Lync Server пакет управления компонентом также может отслеживать производительность и уведомления об ошибках, важных элементов, таких как:</span><span class="sxs-lookup"><span data-stu-id="6438c-117">In addition to monitoring event logs and performance counters for Lync Server, the Component Management pack can also track the performance of, and issue alerts for, crucial items such as:</span></span>

  - <span data-ttu-id="6438c-118">\*\*\*\*   Если службы IIS переходят в автономный режим, будут выдаваться оповещения служб Internet Information Services.</span><span class="sxs-lookup"><span data-stu-id="6438c-118">**Internet Information Services (IIS)**   Alerts will be issued if Internet Information Services goes offline.</span></span> <span data-ttu-id="6438c-119">Это важно, поскольку веб-службы Lync Server основываются на службах IIS.</span><span class="sxs-lookup"><span data-stu-id="6438c-119">This is important, because the Lync Server web services rely on IIS.</span></span>

  - <span data-ttu-id="6438c-120">\*\*\*\*   Если ресурсы системы (например, доступная память) начинают работать, выдаются оповещения об использовании процесса.</span><span class="sxs-lookup"><span data-stu-id="6438c-120">**Process usage**   Alerts will be issued if system resources (such as available memory) begin to run low.</span></span> <span data-ttu-id="6438c-121">Эти оповещения будут выпускаться, даже если сервер Lync Server не отвечает за высокое использование системы.</span><span class="sxs-lookup"><span data-stu-id="6438c-121">These alerts will be issued even if Lync Server is not responsible for the high system usage.</span></span>

  - <span data-ttu-id="6438c-122">**Уведомления о сбоях компьютера**будут выдаваться в случае аппаратной или программной проблемы, которая может угрожать жизнеспособности сервера.   </span><span class="sxs-lookup"><span data-stu-id="6438c-122">**Computer failure events**   Alerts will be issued in case of a hardware or software issue that threatens the viability of a server.</span></span> <span data-ttu-id="6438c-123">Например, администраторы сервера Lync Server получат уведомление о том, что сервер не подвержен опасности сбоя жесткого диска.</span><span class="sxs-lookup"><span data-stu-id="6438c-123">For example, Lync Server administrators will be notified if a server appears to be in danger of experiencing a hard disk failure.</span></span>

<span data-ttu-id="6438c-124">Новые пакеты управления также расширяют возможности создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="6438c-124">The new management packs also feature enhanced reporting.</span></span> <span data-ttu-id="6438c-125">Новые отчеты для Lync Server 2013 включают:</span><span class="sxs-lookup"><span data-stu-id="6438c-125">New reports for Lync Server 2013 include:</span></span>

  - <span data-ttu-id="6438c-126">**Отчет о доступности сценария «завершить**   » в этом отчете подробно описана доступность и время работы для основных служб Lync Server, таких как регистрация или присутствие.</span><span class="sxs-lookup"><span data-stu-id="6438c-126">**End to End Scenario Availability Report**   This report details the availability/uptime for key Lync Server services such as registration or presence.</span></span>

  - <span data-ttu-id="6438c-127">**Отчет о емкости**   с использованием данных счетчиков производительности этот отчет показывает тенденции для системных компонентов, таких как доступность памяти и использование процессора.</span><span class="sxs-lookup"><span data-stu-id="6438c-127">**Capacity Report**   Using performance counter information, this report shows trends for system components such as memory availability and processor usage.</span></span>

  - <span data-ttu-id="6438c-128">**Отчет о**   компоненте в этом отчете перечислены Топ генераторов оповещений, сгруппированных по компоненту Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6438c-128">**Component Report**   This report lists the top alert generators grouped by Lync Server component.</span></span>

<span data-ttu-id="6438c-129">Помимо этих предустановленных отчетов, пакеты управления для Lync Server 2013 автоматически сообщают об оповещениях для обеспечения надежности обоих вызовов (метрики, измеряемые сведениями о вызовах) и состояния QoE (показатели измеряются качеством качества).</span><span class="sxs-lookup"><span data-stu-id="6438c-129">In addition to these predesigned reports, the management packs for Lync Server 2013 automatically report alerts for both Call Reliability (metrics measured by Call Detail Recording) and QoE states (metrics measured by Quality of Experience).</span></span> <span data-ttu-id="6438c-130">Если вы включили запись с подробными сведениями о вызовах, вы можете просмотреть оповещения о надежности звонков, выполнив следующую процедуру на консоли System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="6438c-130">If you have enabled Call Detail Recording, you can review Call Reliability alerts by completing the following procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="6438c-131">Разверните раздел **мониторинг**, разверните **Microsoft Lync Server 2013 Health**, разверните элемент **надежность и качество передачи**, а затем выберите пункт **надежность звонка**.</span><span class="sxs-lookup"><span data-stu-id="6438c-131">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then click **Call Reliability**.</span></span>

<span data-ttu-id="6438c-132">Чтобы просмотреть оповещения о QoS, выполните эту процедуру на консоли System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="6438c-132">To view Quality of Experience alerts, complete this procedure from the System Center Operations Manager console:</span></span>

  - <span data-ttu-id="6438c-133">Разверните раздел **мониторинг**, разверните **Microsoft Lync Server 2013 Health**, разверните элемент **надежность и качество цветопередачи**, а затем разверните **качество мультимедиа**.</span><span class="sxs-lookup"><span data-stu-id="6438c-133">Expand **Monitoring**, expand **Microsoft Lync Server 2013 Health**, expand **Call Reliability and Media Quality**, and then expand **Media Quality**.</span></span>

<span data-ttu-id="6438c-134">Пакеты управления для Lync Server 2013 теперь используют обнаружение на уровне компьютера вместо центрального механизма обнаружения, используемого в Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6438c-134">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism used in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="6438c-135">Это означает, что каждый агент System Center, по сути, выводит себя и сообщает о существовании основного сервера управления.</span><span class="sxs-lookup"><span data-stu-id="6438c-135">This means that each System Center agent essentially discovers itself and reports its existence to the Central Management Server.</span></span> <span data-ttu-id="6438c-136">Использование обнаружения на уровне компьютера упрощает администрирование инфраструктуры System Center, а также позволяет другим версиям пакетов управления Lync Server (например, пакеты управления для Lync Server 2010 и пакеты управления для Lync Server 2013). существование.</span><span class="sxs-lookup"><span data-stu-id="6438c-136">Using machine-level discovery simplifies administration of your System Center infrastructure and also allows different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

