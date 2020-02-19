---
title: 'Lync Server 2013: Настройка работоспособности в Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee193ba28b10e8f209513d5bd6c8b58ae8c4fff9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135456"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="44211-102">Конфигурация работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44211-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44211-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="44211-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="44211-104">С помощью различных веб-сайтов, статей базы знаний Майкрософт и средств набора ресурсов Lync Server администраторы, которые сталкиваются с проблемами при использовании Lync Server, никогда не смогут решить эти проблемы.</span><span class="sxs-lookup"><span data-stu-id="44211-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="44211-105">Очевидно, что вы не можете гарантировать, что у вас не будет проблем с Lync Server 2013, так как Lync Server может зависеть от многих вещей, таких как сбои сети и сбои оборудования, что сам продукт не может управлять.</span><span class="sxs-lookup"><span data-stu-id="44211-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="44211-106">Реализуя мониторинг работоспособности, администраторы могут определить потенциальные проблемы до того, как они станут действительными.</span><span class="sxs-lookup"><span data-stu-id="44211-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="44211-107">Например, администраторы могут использовать функцию мониторинга Lync Server для определения тенденций и тенденЦиес.</span><span class="sxs-lookup"><span data-stu-id="44211-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="44211-108">Например, устойчивое увеличение числа голосовых и видеоконференций может говорить о том, что необходимо увеличить мощность до того, как система окажется перегруженной.</span><span class="sxs-lookup"><span data-stu-id="44211-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="44211-109">Подобным образом администраторы могут использовать System Center Operations Manager для выполнения таких задач, как выдача оповещений в режиме реального времени при возникновении определенных событий, а также для выполнения искусственных транзакций, которые проверяют систему в активном состоянии.</span><span class="sxs-lookup"><span data-stu-id="44211-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="44211-110">Искусственные транзакции используются в Lync Server, чтобы убедиться в том, что пользователи могут успешно выполнять типичные задачи, такие как вход в систему, Обмен мгновенными сообщениями и звонки на телефон, находящийся в телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="44211-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="44211-111">Например, периодическое выполнение этих тестов может привести к возникновению потенциальных проблем для пользователей, входящих в состав Lync Server, и предоставить возможность устранить проблему до того, как группа поддержки передается вызовам от пользователей, которые не могут установить соединение.</span><span class="sxs-lookup"><span data-stu-id="44211-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="44211-112">С помощью System Center Operations Manager для запуска этих искусственных транзакций администраторы могут постоянно отслеживать развертывание Lync Server в течение 24 часов, не требуя от них каких-либо действий, не относящихся к оповещениям, которые могут будут выдаваться.</span><span class="sxs-lookup"><span data-stu-id="44211-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="44211-113">Для Lync Server 2013 пакет управления для System Center Operations Manager также может обнаруживать проблемы внешнего сервера, которые могут негативно повлиять на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44211-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="44211-114">Например, администраторы могут получать уведомления, если службы IIS переходят в автономный режим, системные ресурсы на компьютере Lync Server делятся ниже указанной величины, или на сервере Lync Server произошел сбой оборудования.</span><span class="sxs-lookup"><span data-stu-id="44211-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="44211-115">Конфигурация работоспособности в Lync Server 2013 создана на основе System Center Operations Manager и с использованием пакетов управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44211-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="44211-116">В эти пакеты управления входит множество новых функций и усовершенствований, включая следующие.</span><span class="sxs-lookup"><span data-stu-id="44211-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="44211-117">**Доступность сценария из любого расположения.**</span><span class="sxs-lookup"><span data-stu-id="44211-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="44211-118">В пакете управления Lync Server 2010 появилась концепция мониторинга доступности сценариев конечных пользователей с помощью искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="44211-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="44211-119">В Lync Server 2013 эти агенты имеют больше искусственных транзакций и могут запускаться из различных расположений внутри предприятия, от удаленных географических расположений за пределами предприятия, от устройств филиала и от Lync Server 2010 развертывания, чтобы добавить покрытие в развертывания прежних версий пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="44211-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="44211-120">**Журналы искусственных транзакций.**</span><span class="sxs-lookup"><span data-stu-id="44211-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="44211-121">При сбое искусственной транзакции администратор имеет доступ к журналам HTML, помогающим определить причину сбоя.</span><span class="sxs-lookup"><span data-stu-id="44211-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="44211-122">Можно понять, какое именно действие завершилось неудачно, определить задержку каждого действия, команды, использовавшиеся для запуска теста, и возникшую ошибку.</span><span class="sxs-lookup"><span data-stu-id="44211-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="44211-123">**Увеличенная зона стабильности вызовов.**</span><span class="sxs-lookup"><span data-stu-id="44211-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="44211-124">Пакет управления Lync Server 2010 появился оповещение о надежности вызовов для обнаружения проблем с серьезным подключением, влияющих на голосовые вызовы конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="44211-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="44211-125">Пакет управления Lync Server 2013 позволяет расширить возможности обмена мгновенными сообщениями с помощью однорангового обмена мгновенными сообщениями и других базовых функций конференц-связи в целях повышения производительности и снижения шума.</span><span class="sxs-lookup"><span data-stu-id="44211-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="44211-126">**Мониторинг зависимостей.**</span><span class="sxs-lookup"><span data-stu-id="44211-126">**Dependency monitoring.**</span></span> <span data-ttu-id="44211-127">Сценарии Lync Server могут не работать из-за множества внешних факторов, таких как автономный режим IIS, ограниченные ресурсы ЦП и памяти, а также дисковые проблемы.</span><span class="sxs-lookup"><span data-stu-id="44211-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="44211-128">Новые пакеты управления проверяют несколько особенно важных зависимостей, чтобы администраторы знали об их влиянии.</span><span class="sxs-lookup"><span data-stu-id="44211-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="44211-129">**Улучшенные отчеты.**</span><span class="sxs-lookup"><span data-stu-id="44211-129">**Enhanced reporting.**</span></span> <span data-ttu-id="44211-130">Ряд отчетов помогает администраторам оценивать доступность сценариев, планировать мощность, а также видеть наиболее проблемные компоненты.</span><span class="sxs-lookup"><span data-stu-id="44211-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="44211-131">В пакеты управления также входят различные функции, помогающие обнаруживать и диагностировать в режиме реального времени для обеспечения работоспособности развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44211-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="44211-132">Эти функции приведены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="44211-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="44211-133">Функции пакетов управления</span><span class="sxs-lookup"><span data-stu-id="44211-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44211-134">Возможность</span><span class="sxs-lookup"><span data-stu-id="44211-134">Feature</span></span></th>
<th><span data-ttu-id="44211-135">Описание</span><span class="sxs-lookup"><span data-stu-id="44211-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44211-136">Искусственные транзакции</span><span class="sxs-lookup"><span data-stu-id="44211-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="44211-137">Командлеты Windows PowerShell, которые можно запускать из различных расположений, чтобы обеспечить доступность конечных пользователей сценариев конечных пользователей, таких как вход, присутствие, IM и конференц-связь.</span><span class="sxs-lookup"><span data-stu-id="44211-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44211-138">Оповещения о стабильности вызовов</span><span class="sxs-lookup"><span data-stu-id="44211-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="44211-139">Запросы записей регистрации вызовов (CDR) в базе данных.</span><span class="sxs-lookup"><span data-stu-id="44211-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="44211-140">Эти записи записываются на серверах переднего плана, чтобы показать, могут ли конечные пользователи подключаться к вызову или причин завершения вызова.</span><span class="sxs-lookup"><span data-stu-id="44211-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="44211-141">Эти запросы приводят к оповещениям, которые указывают, когда у многих конечных пользователей возникают проблемы с подключением при одноранговых вызовах или с основными функциональными возможностями конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="44211-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44211-142">Оповещения о качестве мультимедиа</span><span class="sxs-lookup"><span data-stu-id="44211-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="44211-p112">Запросы баз данных, которые ищут отчеты о качестве взаимодействия (QoE), публикуемые клиентами в конце каждого вызова. Эти запросы приводят к оповещениям, указывающим сценарии, в которых пользователи, вероятно, сталкивались с плохим качеством мультимедиа во время вызовов и конференций. Эти данные строятся на основных метриках, таких как задержка и потеря пакетов, метриках, которые вносят непосредственный вклад в качество связи.</span><span class="sxs-lookup"><span data-stu-id="44211-p112">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call. These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences. The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44211-146">Работоспособность компонентов</span><span class="sxs-lookup"><span data-stu-id="44211-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="44211-p113">Отдельные серверные компоненты выдают оповещения, используя журналы событий и счетчики производительности. Такие оповещения указывают условия сбоя, которые могут серьезно повлиять хотя бы на один сценарий конечных пользователей. Эти оповещения также могут указывать множество других условий сбоя, включая незапущенные службы, высокий уровень сбоев, высокую задержку сообщений и проблемы подключения.</span><span class="sxs-lookup"><span data-stu-id="44211-p113">Individual server components raise alerts by using event logs and performance counters. These alerts indicate failure conditions that can severely impact one or more end user scenarios. These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44211-150">Работоспособность зависимостей</span><span class="sxs-lookup"><span data-stu-id="44211-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="44211-151">Сбои могут происходить по разным внешним причинам.</span><span class="sxs-lookup"><span data-stu-id="44211-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="44211-152">Теперь пакеты управления выполняют мониторинг и сбор данных для некоторых особенно важных внешних зависимостей, могущих указать на серьезные проблемы, включая доступность служб IIS, использование ЦП и памяти серверами и процессорами и метрики дисков.</span><span class="sxs-lookup"><span data-stu-id="44211-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="44211-153">Оповещения, выдаваемые системой, разделяются на три основные категории.</span><span class="sxs-lookup"><span data-stu-id="44211-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="44211-154">**Оповещения высокой важности.**</span><span class="sxs-lookup"><span data-stu-id="44211-154">**High-priority Alerts.**</span></span> <span data-ttu-id="44211-155">Эти оповещения указывают условия, которые могут привести к отказу служб для больших групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="44211-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="44211-156">Например, сбой компонента на отдельном компьютере не является высокоприоритетным предупреждением, так как Lync Server 2013 содержит встроенные функции обеспечения высокого уровня доступности.</span><span class="sxs-lookup"><span data-stu-id="44211-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="44211-157">Оповещения высокой важности представляют проблемы, достаточно серьезные, чтобы "разбудить администраторов ночью".</span><span class="sxs-lookup"><span data-stu-id="44211-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="44211-158">Отказы, обнаруженные искусственными транзакциями и автономными службами (например, аудио- и видеоконференций), квалифицируются как оповещения высокой важности.</span><span class="sxs-lookup"><span data-stu-id="44211-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="44211-159">**Оповещения среднего приоритета.**.</span><span class="sxs-lookup"><span data-stu-id="44211-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="44211-160">Эти оповещения указывают условия, которые влияют на ряд пользователей или свидетельствуют о снижении качества вызовов.</span><span class="sxs-lookup"><span data-stu-id="44211-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="44211-161">Сюда входят такие проблемы, как сбои компонентов, задержка в установке вызова или снижение качества звука в вызове.</span><span class="sxs-lookup"><span data-stu-id="44211-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="44211-162">Оповещения в этой категории сохраняют историю состояний и указывают текущее состояние проблемы.</span><span class="sxs-lookup"><span data-stu-id="44211-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="44211-163">Например, предположим, что время установки вызова превышает порог оповещения.</span><span class="sxs-lookup"><span data-stu-id="44211-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="44211-164">Если во время установки вызовов возвращается обычный, эти оповещения будут автоматически разрешены в System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="44211-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="44211-165">Предполагается, что администратор будет просматривать такие оповещения в один и тот же рабочий день.</span><span class="sxs-lookup"><span data-stu-id="44211-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="44211-166">**Прочие оповещения.**</span><span class="sxs-lookup"><span data-stu-id="44211-166">**Other alerts.**</span></span> <span data-ttu-id="44211-167">Это оповещения от компонентов, которые могут оказать воздействие на конкретного пользователя или на ряд пользователей.</span><span class="sxs-lookup"><span data-stu-id="44211-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="44211-168">Например, возможно, служба адресной книги не может выполнять анализ записи Active Directory конкретного пользователя.</span><span class="sxs-lookup"><span data-stu-id="44211-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="44211-169">Предполагается, что администраторы будут приниматься за эти оповещения, когда у них есть время.</span><span class="sxs-lookup"><span data-stu-id="44211-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="44211-170">Содержание</span><span class="sxs-lookup"><span data-stu-id="44211-170">In This Section</span></span>

  - [<span data-ttu-id="44211-171">Настройка Lync Server 2013 для работы с System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="44211-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="44211-172">Использование расширенного ведения журнала для искусственных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44211-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="44211-173">Использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44211-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

