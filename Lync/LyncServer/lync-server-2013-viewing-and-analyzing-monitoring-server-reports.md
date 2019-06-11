---
title: 'Lync Server 2013: Просмотр и анализ отчетов сервера мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a><span data-ttu-id="a73da-102">Просмотр и анализ отчетов сервера мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a73da-102">Viewing and analyzing monitoring server reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a73da-103">_**Тема последнего изменения:** 2014-05-19_</span><span class="sxs-lookup"><span data-stu-id="a73da-103">_**Topic Last Modified:** 2014-05-19_</span></span>

<span data-ttu-id="a73da-104">Мониторинг серверных отчетов предоставляет несколько разных показателей качества голоса для наблюдения за QoE, которые доставляются конечным пользователям.</span><span class="sxs-lookup"><span data-stu-id="a73da-104">Monitoring Server reports provides several different measures of voice quality to monitor the QoE that is being delivered to end-users.</span></span> <span data-ttu-id="a73da-105">Кроме того, сервер мониторинга включает несколько встроенных отчетов, которые ваша организация может использовать для отслеживания использования и тенденций качества мультимедиа в сети организации, а также для устранения проблем с качеством мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="a73da-105">Additionally, Monitoring Server includes several built-in reports that your organization can use to watch usage and media quality trends on your organization's network and troubleshoot media quality issues that arise.</span></span>

<span data-ttu-id="a73da-106">Основная часть хранения серверных отчетов, представляющих собой ежедневные и еженедельные операции, — просмотр и анализ отчетов о качестве мультимедиа в частности:</span><span class="sxs-lookup"><span data-stu-id="a73da-106">A primary part of keeping Monitoring Server Reports interesting for daily and weekly operations is viewing and analyzing Media Quality Reports, in particular:</span></span>

  - <span data-ttu-id="a73da-107">QoE/отчеты о тенденциях</span><span class="sxs-lookup"><span data-stu-id="a73da-107">QoE Summary/Trend Reports</span></span>

  - <span data-ttu-id="a73da-108">Отчеты о производительности QoE</span><span class="sxs-lookup"><span data-stu-id="a73da-108">QoE Performance Reports</span></span>

<div>

## <a name="view-reports-from-the-monitoring-server"></a><span data-ttu-id="a73da-109">Просмотр отчетов на сервере мониторинга</span><span class="sxs-lookup"><span data-stu-id="a73da-109">View reports from the monitoring server</span></span>

1.  <span data-ttu-id="a73da-110">В веб-браузере найдите серверы, на которых размещены службы отчетов SQL.</span><span class="sxs-lookup"><span data-stu-id="a73da-110">From a web browser, locate your servers hosting the SQL reporting services.</span></span>

2.  <span data-ttu-id="a73da-111">Просмотрите необходимые отчеты в окне браузера.</span><span class="sxs-lookup"><span data-stu-id="a73da-111">View the required reports from the browser screen.</span></span>

3.  <span data-ttu-id="a73da-112">Необязательно Экспортируйте отчет, выбрав параметр Экспорт и требуемый выходной формат.</span><span class="sxs-lookup"><span data-stu-id="a73da-112">(Optional) Export a report by selecting the export option and the required output format.</span></span>

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a><span data-ttu-id="a73da-113">Настройка записи сведений о звонке (CDR)</span><span class="sxs-lookup"><span data-stu-id="a73da-113">Configure call detail recording (CDR)</span></span>

1.  <span data-ttu-id="a73da-114">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные разрешения) либо назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a73da-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent permissions), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="a73da-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a73da-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="a73da-116">В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.</span><span class="sxs-lookup"><span data-stu-id="a73da-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="a73da-117">На странице **Регистрация вызовов** в таблице щелкните необходимый сайт, щелкните **Правка**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="a73da-117">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="a73da-118">Чтобы включить очистку, установите флажок **включить очистку для серверов мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="a73da-118">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="a73da-119">В разделе **хранить подробные сведения о вызове (в днях)** выберите максимальное количество дней, в течение которых следует хранить записи с подробными сведениями о звонке.</span><span class="sxs-lookup"><span data-stu-id="a73da-119">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>

7.  <span data-ttu-id="a73da-120">В параметре **Хранить сведения отчетов об ошибках максимум в течение (дней):** выберите максимальное число дней, в течение которых должны храниться данные отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a73da-120">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>

8.  <span data-ttu-id="a73da-121">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a73da-121">Click **Commit**.</span></span>

</div>

<div>

## <a name="configure-qoe"></a><span data-ttu-id="a73da-122">Настройка QoE</span><span class="sxs-lookup"><span data-stu-id="a73da-122">Configure QoE</span></span>

1.  <span data-ttu-id="a73da-123">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a73da-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a73da-124">Дополнительные сведения см. в разделе Delegate Setup Permissions.</span><span class="sxs-lookup"><span data-stu-id="a73da-124">For details, see Delegate Setup Permissions.</span></span>

2.  <span data-ttu-id="a73da-125">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a73da-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="a73da-126">На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="a73da-126">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="a73da-127">На странице **Данные о качестве взаимодействия** выберите требуемый сайт в таблице, нажмите **Изменить** и выберите **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a73da-127">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5.  <span data-ttu-id="a73da-128">Чтобы включить очистку, установите флажок **включить очистку для серверов мониторинга**.</span><span class="sxs-lookup"><span data-stu-id="a73da-128">To turn on purging, select **Enable Purging for Monitoring Servers**.</span></span>

6.  <span data-ttu-id="a73da-129">В разделе **хранить сведения о звонке для максимальной длительности (дни):** выберите максимальное количество дней, в течение которых QoE данные должны оставаться на удержании.</span><span class="sxs-lookup"><span data-stu-id="a73da-129">In **Keep call detail recordings for maximum duration (days):** select the maximum number of days that QoE data should be retained.</span></span>

7.  <span data-ttu-id="a73da-130">Нажмите Исполнить.</span><span class="sxs-lookup"><span data-stu-id="a73da-130">Click Commit.</span></span>

</div>

<div>

## <a name="change-the-archiving-policy"></a><span data-ttu-id="a73da-131">Изменение политики архивации</span><span class="sxs-lookup"><span data-stu-id="a73da-131">Change the archiving policy</span></span>

1.  <span data-ttu-id="a73da-132">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a73da-132">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a73da-133">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a73da-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="a73da-134">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.</span><span class="sxs-lookup"><span data-stu-id="a73da-134">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="a73da-135">Нажмите пункт **Глобальная** в списке политик, выберите **Изменить**, затем **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a73da-135">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a73da-136">На странице **Изменить политику архивации — глобальная** выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a73da-136">In **Edit Archiving Policy - Global**, do the following:</span></span>

6.  <span data-ttu-id="a73da-137">Чтобы включить или отключить внутреннее архивирование для развертывания, установите или снимите флажок **Архивировать внутреннюю связь** .</span><span class="sxs-lookup"><span data-stu-id="a73da-137">To enable or disable internal archiving for the deployment, select or clear the **Archive internal communications** check box.</span></span>

7.  <span data-ttu-id="a73da-138">Чтобы включить или отключить внешнее архивирование для развертывания, установите или снимите флажок **Архивировать внешние связи** .</span><span class="sxs-lookup"><span data-stu-id="a73da-138">To enable or disable external archiving for the deployment, select or clear the **Archive external communications** check box.</span></span>

8.  <span data-ttu-id="a73da-139">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a73da-139">Click **Commit**.</span></span>

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a><span data-ttu-id="a73da-140">Применение к пользователю политики архивации</span><span class="sxs-lookup"><span data-stu-id="a73da-140">Apply an archiving policy to a user</span></span>

1.  <span data-ttu-id="a73da-141">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a73da-141">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a73da-142">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a73da-142">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="a73da-143">В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="a73da-143">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="a73da-144">В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a73da-144">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="a73da-145">В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика архивации**выберите политику архивации пользователей, которую вы хотите применить.</span><span class="sxs-lookup"><span data-stu-id="a73da-145">In **Edit Lync Server User** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>

6.  <span data-ttu-id="a73da-146">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="a73da-146">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a73da-147">См. также</span><span class="sxs-lookup"><span data-stu-id="a73da-147">See Also</span></span>


[<span data-ttu-id="a73da-148">Использование отчетов мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a73da-148">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
[<span data-ttu-id="a73da-149">Отчет о производительности сервера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a73da-149">Server Performance Report in Lync Server 2013</span></span>](lync-server-2013-server-performance-report.md)  
[<span data-ttu-id="a73da-150">Отчет о сравнении качества мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a73da-150">Media Quality Comparison Report in Lync Server 2013</span></span>](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

