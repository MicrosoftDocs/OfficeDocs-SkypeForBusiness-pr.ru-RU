---
title: Вопросы и ответы по средствам нагрузочного тестирования и производительности Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9de9555f9f009558b700a32ca6e58059eb5ea990
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="38be5-102">Вопросы и ответы по средствам нагрузочного тестирования и производительности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38be5-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38be5-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="38be5-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="38be5-104">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="38be5-104">Frequently Asked Questions</span></span>

<span data-ttu-id="38be5-105">Ниже приведены часто задаваемые вопросы о средстве нагрузки и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38be5-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="38be5-106">Можно ли запускать Линкперфтул. exe в рабочей среде?</span><span class="sxs-lookup"><span data-stu-id="38be5-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="38be5-107">Мы не рекомендуем это делать.</span><span class="sxs-lookup"><span data-stu-id="38be5-107">We do not recommend this.</span></span> <span data-ttu-id="38be5-108">Это средство оказывает влияние на производительность сервера, безопасность и взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="38be5-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="38be5-109">Я выполняю вход в систему для пользователей в первый раз.</span><span class="sxs-lookup"><span data-stu-id="38be5-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="38be5-110">Почему серверы работают на такой высокой нагрузке?</span><span class="sxs-lookup"><span data-stu-id="38be5-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="38be5-111">При первом входе пользователей в систему возникают дополнительные операции.</span><span class="sxs-lookup"><span data-stu-id="38be5-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="38be5-112">В результате производительность на внутреннем сервере Microsoft SQL Server будет снижена.</span><span class="sxs-lookup"><span data-stu-id="38be5-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="38be5-113">Мы рекомендуем выполнить короткий тест, который заносится в журнал для всех пользователей, а затем перезапустите клиенты, прежде чем измерять результаты.</span><span class="sxs-lookup"><span data-stu-id="38be5-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="38be5-114">Мы не поддерживаем более 12 одновременных сеансов входа пользователей в секунду, но это зависит от конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="38be5-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="38be5-115">В работе клиентов недостаточно памяти.</span><span class="sxs-lookup"><span data-stu-id="38be5-115">My clients are running out of memory.</span></span> <span data-ttu-id="38be5-116">Что делать?</span><span class="sxs-lookup"><span data-stu-id="38be5-116">What should I do?</span></span>

<span data-ttu-id="38be5-117">Если на ваших клиентах не хватает памяти, необходимо уменьшить количество пользователей на компьютер.</span><span class="sxs-lookup"><span data-stu-id="38be5-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="38be5-118">В каждый момент времени у моих клиентов составляется 100 процентов.</span><span class="sxs-lookup"><span data-stu-id="38be5-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="38be5-119">Что делать?</span><span class="sxs-lookup"><span data-stu-id="38be5-119">What should I do?</span></span>

<span data-ttu-id="38be5-120">Если клиенты работают с очень большим ПРОЦЕССОРом после входа всех пользователей, необходимо уменьшить число пользователей на компьютер.</span><span class="sxs-lookup"><span data-stu-id="38be5-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="38be5-121">Высокие пиковые выгрузки ЦП приемлемы, но если они поддерживаются, необходимо уменьшить нагрузку.</span><span class="sxs-lookup"><span data-stu-id="38be5-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="38be5-122">Можно ли запускать средство на самом сервере?</span><span class="sxs-lookup"><span data-stu-id="38be5-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="38be5-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="38be5-123">No.</span></span> <span data-ttu-id="38be5-124">Этот сценарий не поддерживается и может не работать из-за несовпадения двоичных файлов.</span><span class="sxs-lookup"><span data-stu-id="38be5-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="38be5-125">Кроме того, поскольку точка предназначена для измерения потребления ресурсов на сервере, при запуске средства отображается небессмысленное измерение.</span><span class="sxs-lookup"><span data-stu-id="38be5-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="38be5-126">Можно ли запускать Линкперфтул. exe на виртуальном сервере или на Microsoft Hyper Server V 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="38be5-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="38be5-127">Да.</span><span class="sxs-lookup"><span data-stu-id="38be5-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="38be5-128">Что означает МПОП?</span><span class="sxs-lookup"><span data-stu-id="38be5-128">What does MPOP mean?</span></span>

<span data-ttu-id="38be5-129">МПОП означает несколько точек присутствия.</span><span class="sxs-lookup"><span data-stu-id="38be5-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="38be5-130">Это предназначено для имитации сценария, в котором пользователи выполнили вход в Lync 2013 с нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="38be5-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="38be5-131">Обратите внимание, что в Линкперфтул. exe каждая конечная точка использует профиль по умолчанию (то есть профиль не разбивается между двумя точками присутствия).</span><span class="sxs-lookup"><span data-stu-id="38be5-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="38be5-132">Я начал Линкперфтул. exe, но ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="38be5-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="38be5-133">Почему?</span><span class="sxs-lookup"><span data-stu-id="38be5-133">What’s going on?</span></span>

<span data-ttu-id="38be5-134">Проверьте счетчик всех активных конечных точек на клиентах, чтобы проверить, подключаются ли пользователи.</span><span class="sxs-lookup"><span data-stu-id="38be5-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="38be5-135">Если пользователи не подключаются, проверьте конфигурацию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38be5-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="38be5-136">Эта проблема обычно возникает из-за неправильного имени сервера, префикса пользователя или пароля.</span><span class="sxs-lookup"><span data-stu-id="38be5-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="38be5-137">Обратите внимание на то, что внешние клиенты должны указать прокси доступа в качестве значения Таржетсервер.</span><span class="sxs-lookup"><span data-stu-id="38be5-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="38be5-138">Проверьте порт в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="38be5-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="38be5-139">Как узнать, что происходит?</span><span class="sxs-lookup"><span data-stu-id="38be5-139">How do I know something is happening?</span></span>

<span data-ttu-id="38be5-140">Различные счетчики производительности Линкперфтул указывают, поддаются ли пользователи для подключения и выполнения действий.</span><span class="sxs-lookup"><span data-stu-id="38be5-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="38be5-141">Тем не менее, простой способ проверки заключается в входе в одну из учетных записей с помощью Lync 2013 и выполнения требуемого действия.</span><span class="sxs-lookup"><span data-stu-id="38be5-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="38be5-142">У меня установлены средства планирования емкости Live Communications Server 2007 R2 и/или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="38be5-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="38be5-143">Это нормально?</span><span class="sxs-lookup"><span data-stu-id="38be5-143">Is that OK?</span></span>

<span data-ttu-id="38be5-144">Нет.</span><span class="sxs-lookup"><span data-stu-id="38be5-144">No.</span></span> <span data-ttu-id="38be5-145">Существуют проблемы с взаимодействием, поэтому необходимо удалить все предыдущие версии этого продукта.</span><span class="sxs-lookup"><span data-stu-id="38be5-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="38be5-146">Настроила или не повлияет на топологию сервера информации о вызовах CAA?</span><span class="sxs-lookup"><span data-stu-id="38be5-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="38be5-147">Нет.</span><span class="sxs-lookup"><span data-stu-id="38be5-147">No.</span></span> <span data-ttu-id="38be5-148">Средства создают только пользователей, контакты и списки рассылки, а также имитируют нагрузку пользователей.</span><span class="sxs-lookup"><span data-stu-id="38be5-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="38be5-149">Каково максимальное количество пользователей, поддерживаемых средствами?</span><span class="sxs-lookup"><span data-stu-id="38be5-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="38be5-150">Мы создали до 80 000 пользователей и выполнили тестирование с учетом всего 30 000 пользователей, используя эти средства.</span><span class="sxs-lookup"><span data-stu-id="38be5-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="38be5-151">Мы рекомендуем не более 120 000 пользователей, несмотря на то, что технические ограничения допускают более высокое значение, в зависимости от того, какое аппаратное обеспечение доступно для клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="38be5-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

