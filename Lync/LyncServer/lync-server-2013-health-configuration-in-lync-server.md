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
ms.openlocfilehash: 14a4da3ec3f06dfb573ef7e9422bdd6b751db636
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="health-configuration-in-lync-server-2013"></a><span data-ttu-id="69f77-102">Конфигурация работоспособности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f77-102">Health configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f77-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="69f77-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="69f77-104">С помощью различных веб-сайтов, статей базы знаний Майкрософт и средств пакета ресурсов Lync Server администраторы, которые сталкиваются с проблемами при работе с Lync Server, никогда не смогут решить эти проблемы.</span><span class="sxs-lookup"><span data-stu-id="69f77-104">Between various websites, Microsoft Knowledge Base articles, and Lync Server Resource Kit tools, administrators who encounter problems when running Lync Server are never far from a way to solve those problems.</span></span>

<span data-ttu-id="69f77-105">Очевидно, что у вас нет возможности гарантировать отсутствие проблем с Lync Server 2013, так как Lync Server может повлиять на многие вещи, такие как сбои сети и сбои оборудования, которые сам продукт не может контролировать.</span><span class="sxs-lookup"><span data-stu-id="69f77-105">Obviously there is no way to guarantee that you will never encounter problems with Lync Server 2013 because Lync Server can be affected by many things—like network crashes and hardware failures—that the product itself cannot control.</span></span> <span data-ttu-id="69f77-106">Выполнив мониторинг работоспособности, администраторы могут выявить потенциальные проблемы, прежде чем они будут переключаться на реальные проблемы.</span><span class="sxs-lookup"><span data-stu-id="69f77-106">By implementing health monitoring, administrators can identify potential problems before they turn into actual problems.</span></span> <span data-ttu-id="69f77-107">Например, администраторы могут использовать функцию мониторинга сервера Lync Server для выявления тенденций и тенденЦиес.</span><span class="sxs-lookup"><span data-stu-id="69f77-107">For example, administrators can use Lync Server monitoring to identify trends and tendencies.</span></span> <span data-ttu-id="69f77-108">Например, при постоянном увеличении количества аудио-и видеоконференций может возникнуть необходимость добавить емкость, прежде чем система станет перегруженной.</span><span class="sxs-lookup"><span data-stu-id="69f77-108">For example, a steady increase in the number of audio/video conferences might suggest a need to add capacity before the system becomes overloaded.</span></span>

<span data-ttu-id="69f77-109">Аналогичным образом, администраторы могут использовать System Center Operations Manager для выполнения таких задач, как выявление предупреждений в реальном времени при возникновении указанных событий, а также выполнение искусственных транзакций для упреждающего тестирования системы.</span><span class="sxs-lookup"><span data-stu-id="69f77-109">In a similar fashion, administrators can use System Center Operations Manager to do such things as issue real-time alerts when specified events occur, and to run synthetic transactions that proactively test the system.</span></span> <span data-ttu-id="69f77-110">Синтетические транзакции используются в Lync Server, чтобы убедиться в том, что пользователи смогут успешно выполнять типичные задачи, такие как вход в систему, Обмен мгновенными сообщениями и звонки на телефоны, находящиеся в коммутируемой телефонной сети с открытым коммутируемым подключением (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="69f77-110">Synthetic transactions are used in Lync Server to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="69f77-111">Например, периодические выполнение этих тестов может оповещать вас о потенциальных проблемах с входом в Lync Server, а также о том, как устранить проблему, прежде чем служба поддержки будет передаваться с вызовами пользователей, которые не смогут установить соединение.</span><span class="sxs-lookup"><span data-stu-id="69f77-111">For example, periodically running these tests can alert you to potential problems with users logging on to Lync Server, and give you a chance to correct the problem before your support team is flooded with calls from users unable to make a connection.</span></span> <span data-ttu-id="69f77-112">С помощью System Center Operations Manager для выполнения этих искусственных транзакций администраторы могут регулярно отслеживать развертывание Lync Server в течение 24 часов в каждый день, не требуя от них каких-либо действий, Кроме того, чтобы отвечать на любые оповещения, которые могут будет выдан.</span><span class="sxs-lookup"><span data-stu-id="69f77-112">By using System Center Operations Manager to run these synthetic transactions, administrators can routinely monitor their deployment of Lync Server continuously for 24 hours every day without having to do much of anything beyond responding to any alerts that might be issued.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69f77-113">Для Lync Server 2013 пакет управления System Center Operations Manager также может выявить проблемы внешнего сервера, которые могут негативно сказаться на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69f77-113">For Lync Server 2013, the Management Pack for System Center Operations Manager is also able to detect "external" issues that can adversely affect Lync Server.</span></span> <span data-ttu-id="69f77-114">Например, администраторы могут получать уведомления о том, что службы IIS переходят в автономный режим, системные ресурсы на компьютере Lync Server делятся ниже заданной величины, или на сервере Lync Server происходит сбой оборудования.</span><span class="sxs-lookup"><span data-stu-id="69f77-114">For example, administrators can be notified if Internet Information Services (IIS) goes offline, system resources on a Lync Server computer fall below a specified amount, or a Lync Server computer experiences a hardware failure.</span></span>



</div>

<span data-ttu-id="69f77-115">Конфигурация работоспособности в Lync Server 2013 встроена в System Center Operations Manager и использует пакеты управления Lync Server Management.</span><span class="sxs-lookup"><span data-stu-id="69f77-115">Health configuration in Lync Server 2013 is built around System Center Operations Manager and the use of Lync Server Management Packs.</span></span> <span data-ttu-id="69f77-116">Эти пакеты управления включают ряд новых функций и улучшений, в том числе:</span><span class="sxs-lookup"><span data-stu-id="69f77-116">These Management Packs include a number of new features and enhancements, including:</span></span>

  - <span data-ttu-id="69f77-117">**Доступность сценария из любого места.**</span><span class="sxs-lookup"><span data-stu-id="69f77-117">**Scenario availability from any location.**</span></span> <span data-ttu-id="69f77-118">В пакете управления Lync Server 2010 представлена концепция мониторинга доступности сценариев конечных пользователей с помощью искусственных транзакций.</span><span class="sxs-lookup"><span data-stu-id="69f77-118">The Lync Server 2010 Management Pack introduced the concept of monitoring end user scenario availability with synthetic transactions.</span></span> <span data-ttu-id="69f77-119">В Lync Server 2013 эти агенты содержат больше искусственных транзакций, и их можно запускать из различных расположений внутри предприятия, из удаленных географических расположений за пределами Организации, от устройств с офисом филиала и с Lync Server 2010 развертывание, чтобы добавить покрытие в развертывания устаревшего края.</span><span class="sxs-lookup"><span data-stu-id="69f77-119">In Lync Server 2013, these agents have more synthetic transactions and can be run from a variety of locations inside the enterprise, from remote geographic locations outside of the enterprise, against branch office appliances and against Lync Server 2010 deployments to add coverage to legacy Edge deployments.</span></span>

  - <span data-ttu-id="69f77-120">**Журналы виртуальных транзакций.**</span><span class="sxs-lookup"><span data-stu-id="69f77-120">**Synthetic transaction logs.**</span></span> <span data-ttu-id="69f77-121">Если виртуальная транзакция завершается сбоем, администраторы имеют доступ к журналам HTML, чтобы определить, что не удалось.</span><span class="sxs-lookup"><span data-stu-id="69f77-121">When a synthetic transaction fails, administrators have access to HTML logs to help determine what failed.</span></span> <span data-ttu-id="69f77-122">Сюда входит определение того, какое действие завершилось сбоем, задержка каждого действия, Командная строка, используемая для выполнения теста, и обнаружена ошибка.</span><span class="sxs-lookup"><span data-stu-id="69f77-122">This includes understanding which action failed, the latency of each action, the command-line used to run the test, and the error that was encountered.</span></span>

  - <span data-ttu-id="69f77-123">**Повышенная надежность звонков.**</span><span class="sxs-lookup"><span data-stu-id="69f77-123">**Increased call reliability coverage.**</span></span> <span data-ttu-id="69f77-124">Пакет управления Lync Server 2010 предлагает уведомления о надежности звонков для обнаружения проблем с серьезным подключением, которые влияют на голосовые звонки конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="69f77-124">The Lync Server 2010 Management Pack introduced call reliability alerting to detect severe connectivity issues that affect the audio calls of end users.</span></span> <span data-ttu-id="69f77-125">В пакетах управления Lync Server 2013 вы можете добавлять сведения о том, как обмениваться мгновенными сообщениями в одноранговой сети и другим простыми возможностями конференции, обеспечивая более высокое качество и уменьшая шум.</span><span class="sxs-lookup"><span data-stu-id="69f77-125">The Lync Server 2013 Management Packs add coverage for peer-to-peer instant messaging (IM) and other basic conferencing features to maximize coverage while reducing noise.</span></span>

  - <span data-ttu-id="69f77-126">**Мониторинг зависимостей.**</span><span class="sxs-lookup"><span data-stu-id="69f77-126">**Dependency monitoring.**</span></span> <span data-ttu-id="69f77-127">Сценарии Lync Server могут завершаться сбоем из-за различных внешних факторов, таких как IIS, которые не подключены к сети, ограниченные ресурсы процессора и памяти, а также проблемы с диском.</span><span class="sxs-lookup"><span data-stu-id="69f77-127">Lync Server scenarios can fail due to a variety of external factors such as IIS being offline, limited CPU and memory resources, and disk issues.</span></span> <span data-ttu-id="69f77-128">Новые пакеты управления проверяют несколько критических зависимостей, чтобы администраторы могли узнать их влияние.</span><span class="sxs-lookup"><span data-stu-id="69f77-128">The new management packs check several critical dependencies to ensure administrators are aware of their impact.</span></span>

  - <span data-ttu-id="69f77-129">**Расширенные возможности создания отчетов.**</span><span class="sxs-lookup"><span data-stu-id="69f77-129">**Enhanced reporting.**</span></span> <span data-ttu-id="69f77-130">Набор отчетов, помогающих администраторам оценить доступность сценария, спланировать емкость и узнать, какие компоненты сталкиваются с наибольшим количеством проблем.</span><span class="sxs-lookup"><span data-stu-id="69f77-130">A set of reports to help administrators estimate scenario availability, plan for capacity, and see which components are experiencing the most issues.</span></span>

<span data-ttu-id="69f77-131">Пакеты управления включают в себя множество функций, помогающих найти и диагностировать, обеспечивая доступность в режиме реального времени для развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="69f77-131">The Management Packs also include a variety of features to help detect and diagnose provide real-time visibility into the health your Lync Server deployment.</span></span> <span data-ttu-id="69f77-132">Эти функции перечислены в приведенной ниже таблице.</span><span class="sxs-lookup"><span data-stu-id="69f77-132">These features are listed in the following table.</span></span>

### <a name="management-pack-features"></a><span data-ttu-id="69f77-133">Функции пакета управления</span><span class="sxs-lookup"><span data-stu-id="69f77-133">Management Pack Features</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69f77-134">Функция</span><span class="sxs-lookup"><span data-stu-id="69f77-134">Feature</span></span></th>
<th><span data-ttu-id="69f77-135">Описание</span><span class="sxs-lookup"><span data-stu-id="69f77-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69f77-136">Искусственные транзакции</span><span class="sxs-lookup"><span data-stu-id="69f77-136">Synthetic Transactions</span></span></p></td>
<td><p><span data-ttu-id="69f77-137">Командлеты Windows PowerShell, которые можно запускать из различных местоположений, чтобы конечные пользователи могли использовать сценарии конечного пользователя, такие как вход, присутствие, мгновенные сообщения и конференции.</span><span class="sxs-lookup"><span data-stu-id="69f77-137">Windows PowerShell cmdlets that can be run from various locations to ensure that end user scenarios such as sign-in, presence, IM, and conferencing are readily available to end users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f77-138">Оповещения о надежности звонков</span><span class="sxs-lookup"><span data-stu-id="69f77-138">Call Reliability Alerts</span></span></p></td>
<td><p><span data-ttu-id="69f77-139">Запросы к базе данных для записей с подробными сведениями о звонке (CDR).</span><span class="sxs-lookup"><span data-stu-id="69f77-139">Database queries for Call Detail Records (CDR).</span></span> <span data-ttu-id="69f77-140">Эти записи записываются серверами переднего плана, чтобы показать, удалось ли конечным пользователям подключаться к звонку или почему звонок был прерван.</span><span class="sxs-lookup"><span data-stu-id="69f77-140">These records are written by Front End Servers to reflect whether end users were able to connect to a call or why a call was terminated.</span></span> <span data-ttu-id="69f77-141">В этих запросах выводятся оповещения о том, что при подключении к одноранговой сети или основных функциях конференц-связи с большим количеством конечных пользователей возникают проблемы с подключением.</span><span class="sxs-lookup"><span data-stu-id="69f77-141">These queries result in alerts that indicate when a wide range of end users are experiencing connectivity issues for peer-to-peer calls or basic conferencing functionality.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f77-142">Уведомления о качестве мультимедиа</span><span class="sxs-lookup"><span data-stu-id="69f77-142">Media Quality Alerts</span></span></p></td>
<td><p><span data-ttu-id="69f77-143">Запросы к базам данных, которые проявляются отчетами качества взаимодействия (QoE), опубликованными клиентами в конце каждого звонка.</span><span class="sxs-lookup"><span data-stu-id="69f77-143">Database queries that look at Quality of Experience (QoE) reports published by clients at the end of each call.</span></span> <span data-ttu-id="69f77-144">В этих запросах выводятся уведомления о том, что при звонках и конференциях пользователи могут столкнуться с низким качеством мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="69f77-144">These queries result in alerts that pinpoint scenarios where users are likely to be experiencing poor media quality during calls and conferences.</span></span> <span data-ttu-id="69f77-145">Данные строятся на основе метрик ключа, таких как задержка и потери пакетов, метрики, которые непосредственно влияют на качество связи.</span><span class="sxs-lookup"><span data-stu-id="69f77-145">The data is built upon key metrics such as packet latency and loss, metrics that are known to directly contribute to call quality.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69f77-146">Работоспособность компонента</span><span class="sxs-lookup"><span data-stu-id="69f77-146">Component Health</span></span></p></td>
<td><p><span data-ttu-id="69f77-147">Отдельные серверные компоненты создают оповещения с помощью журналов событий и счетчиков производительности.</span><span class="sxs-lookup"><span data-stu-id="69f77-147">Individual server components raise alerts by using event logs and performance counters.</span></span> <span data-ttu-id="69f77-148">Эти оповещения указывают на ошибки, которые могут значительно повлиять на один или несколько сценариев конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="69f77-148">These alerts indicate failure conditions that can severely impact one or more end user scenarios.</span></span> <span data-ttu-id="69f77-149">Эти оповещения также могут указывать на различные другие условия сбоя, в том числе на незапущенные службы, высокую частоту сбоев, высокую задержку сообщений или проблемы с подключением.</span><span class="sxs-lookup"><span data-stu-id="69f77-149">These alerts can also indicate a variety of other failure conditions, including services not running, high failure rates, high message latency, or connectivity issues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69f77-150">Состояние зависимостей</span><span class="sxs-lookup"><span data-stu-id="69f77-150">Dependency Health</span></span></p></td>
<td><p><span data-ttu-id="69f77-151">Ошибки могут возникать по нескольким внешним причинам.</span><span class="sxs-lookup"><span data-stu-id="69f77-151">Failures can occur for a variety of external reasons.</span></span> <span data-ttu-id="69f77-152">Пакеты управления теперь отслеживают и собирают данные для некоторых критических внешних зависимостей, которые могут указывать на серьезные проблемы, в том числе сведения о доступности, ЦП и использовании памяти серверами, процессами и метриками дисков.</span><span class="sxs-lookup"><span data-stu-id="69f77-152">The management packs now monitor and collect data for some of the critical external dependencies that might indicate severe issues, including IIS availability, CPU and memory usage of servers and processes, and disk metrics.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69f77-153">Оповещения, выданные системой, отнесены на три основные категории:</span><span class="sxs-lookup"><span data-stu-id="69f77-153">The alerts issued by the system have been classified into three general categories:</span></span>

  - <span data-ttu-id="69f77-154">**Оповещения с высоким приоритетом.**</span><span class="sxs-lookup"><span data-stu-id="69f77-154">**High-priority Alerts.**</span></span> <span data-ttu-id="69f77-155">Эти оповещения указывают условия, которые приводят к сбою обслуживания для больших групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="69f77-155">These alerts indicate conditions that will cause service outages for large groups of users.</span></span> <span data-ttu-id="69f77-156">Например, сбой компонента на одном компьютере не является предупреждением высокого приоритета, так как Lync Server 2013 имеет встроенные функции высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="69f77-156">For example, a component failure on a single machine is not a high-priority alert because Lync Server 2013 has built-in high availability features.</span></span> <span data-ttu-id="69f77-157">Вместо этого оповещения с высоким приоритетом представляют проблемы, достаточно важные для администраторов по ночам.</span><span class="sxs-lookup"><span data-stu-id="69f77-157">Instead, high-priority alerts represent problems serious enough “to wake up administrators at night.”</span></span> <span data-ttu-id="69f77-158">Сообщения о нарушениях, обнаруженных искусственными транзакциями и автономными службами (например, аудио-и видеоконференцией), определяются как высокоприоритетные оповещения.</span><span class="sxs-lookup"><span data-stu-id="69f77-158">Outages detected by synthetic transactions and offline services (for example, audio/video conferencing) qualify as high-priority alerts.</span></span>

  - <span data-ttu-id="69f77-159">**Оповещения среднего приоритета.**..</span><span class="sxs-lookup"><span data-stu-id="69f77-159">**Medium-priority alerts.**.</span></span> <span data-ttu-id="69f77-160">Эти оповещения определяют условия, влияющие на подмножество пользователей или означающие снижение качества связи.</span><span class="sxs-lookup"><span data-stu-id="69f77-160">These alerts indicate conditions that affect a subset of users or indicate call quality degradation.</span></span> <span data-ttu-id="69f77-161">, В том числе проблемы, такие как сбои компонентов, задержка при звонке или снижение качества звука во время звонка.</span><span class="sxs-lookup"><span data-stu-id="69f77-161">That includes problems such as component failures, latency in call establishment, or degraded audio quality in call.</span></span> <span data-ttu-id="69f77-162">Оповещения в этой категории представляют собой состояние, которое указывает на текущее состояние ошибки.</span><span class="sxs-lookup"><span data-stu-id="69f77-162">Alerts in this category are stateful and indicate the current status of the issue.</span></span> <span data-ttu-id="69f77-163">Например, предположим, что срок вашего звонка превышает порог оповещения.</span><span class="sxs-lookup"><span data-stu-id="69f77-163">For example, suppose your call establishment times exceed the alert threshold.</span></span> <span data-ttu-id="69f77-164">Если при установленном звонке возвращаются значения Normal, эти оповещения будут автоматически устранены в System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="69f77-164">If call establishment times return to normal, these alerts will be auto-resolved in System Center Operations Manager.</span></span> <span data-ttu-id="69f77-165">Ожидание этих оповещений заключается в том, что администратор будет просматривать их в одном и том же деловом дне.</span><span class="sxs-lookup"><span data-stu-id="69f77-165">The expectation for these alerts is that an administrator will look at them on the same business day.</span></span>

  - <span data-ttu-id="69f77-166">**Другие оповещения.**</span><span class="sxs-lookup"><span data-stu-id="69f77-166">**Other alerts.**</span></span> <span data-ttu-id="69f77-167">Это оповещения от компонентов, которые могут повлиять на определенного пользователя или на подмножество пользователей.</span><span class="sxs-lookup"><span data-stu-id="69f77-167">These are alerts from components that might affect a specific user or subset of users.</span></span> <span data-ttu-id="69f77-168">Например, возможно, службе адресной книги не удалось проанализировать запись Active Directory для определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="69f77-168">For example, perhaps the Address Book service could not parse the Active Directory entry of a given user.</span></span> <span data-ttu-id="69f77-169">Ожидание этих оповещений заключается в том, что администраторы получают доступ к ним, когда они доступны.</span><span class="sxs-lookup"><span data-stu-id="69f77-169">The expectation for these alerts is that administrators will get to them when they have time available.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69f77-170">Содержание</span><span class="sxs-lookup"><span data-stu-id="69f77-170">In This Section</span></span>

  - [<span data-ttu-id="69f77-171">Настройка Lync Server 2013 для работы с System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="69f77-171">Configuring Lync Server 2013 to work with System Center Operations Manager</span></span>](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [<span data-ttu-id="69f77-172">Использование расширенного ведения журнала для виртуальных транзакций в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f77-172">Using rich logging for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [<span data-ttu-id="69f77-173">Использование Microsoft SQL Server 2008 R2 в качестве базы данных System Center Operations Manager для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f77-173">Using Microsoft SQL Server 2008 R2 as your System Center Operations Manager database for Lync Server 2013</span></span>](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

