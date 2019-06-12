---
title: Вопросы и ответы по работе с Lync Server 2013 с помощью средств нагрузки и производительности
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 Stress and Performance Tool FAQ
ms:assetid: a5aff705-320c-4916-8094-23046b2a1b18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945600(v=OCS.15)
ms:contentKeyID: 51541426
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffcfbca3a2cf58e4e7b87619bb78dabbe42b16bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-stress-and-performance-tool-faq"></a><span data-ttu-id="381fd-102">Вопросы и ответы по работе с Lync Server 2013 с помощью средств нагрузки и производительности</span><span class="sxs-lookup"><span data-stu-id="381fd-102">Lync Server 2013 Stress and Performance Tool FAQ</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="381fd-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="381fd-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="frequently-asked-questions"></a><span data-ttu-id="381fd-104">Ответы на часто задаваемые вопросы</span><span class="sxs-lookup"><span data-stu-id="381fd-104">Frequently Asked Questions</span></span>

<span data-ttu-id="381fd-105">Ниже приведены ответы на часто задаваемые вопросы о средстве быстрой и высокопроизводительной нагрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="381fd-105">Here are some frequently asked questions about the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="can-i-run-lyncperftoolexe-in-production"></a><span data-ttu-id="381fd-106">Могу ли я запускать Линкперфтул. exe в рабочей среде?</span><span class="sxs-lookup"><span data-stu-id="381fd-106">Can I run LyncPerfTool.exe in production?</span></span>

<span data-ttu-id="381fd-107">Мы не рекомендуем использовать эту задачу.</span><span class="sxs-lookup"><span data-stu-id="381fd-107">We do not recommend this.</span></span> <span data-ttu-id="381fd-108">Это средство влияет на производительность сервера, безопасность и взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="381fd-108">This tool will impact server performance, security, and user experience.</span></span>

</div>

<div>

## <a name="i-am-logging-on-my-users-for-the-first-time-why-are-the-servers-running-at-such-high-load"></a><span data-ttu-id="381fd-109">Я занимаюсь регистрацией моих пользователей в первый раз.</span><span class="sxs-lookup"><span data-stu-id="381fd-109">I am logging on my users for the first time.</span></span> <span data-ttu-id="381fd-110">Почему серверы работают с такой высокой загрузкой?</span><span class="sxs-lookup"><span data-stu-id="381fd-110">Why are the servers running at such high load?</span></span>

<span data-ttu-id="381fd-111">При первом входе пользователя в систему возникают дополнительные операции.</span><span class="sxs-lookup"><span data-stu-id="381fd-111">The first time the users log on, there are additional operations that occur.</span></span> <span data-ttu-id="381fd-112">В результате производительность серверного сервера Microsoft SQL Server будет снижена.</span><span class="sxs-lookup"><span data-stu-id="381fd-112">As a result, the performance on the Microsoft SQL Server Back End Server will be degraded.</span></span> <span data-ttu-id="381fd-113">Рекомендуется запустить короткий тест для входа на всех пользователей, а затем перезапустить его перед тем, как оценивать результаты.</span><span class="sxs-lookup"><span data-stu-id="381fd-113">We recommend that you run a short test that logs on all of the users, and then restart the clients before you measure results.</span></span> <span data-ttu-id="381fd-114">Мы не поддерживаем более 12 одновременных сеансов входа пользователей в секунду, но это зависит от конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="381fd-114">We do not support more than 12 concurrent user logon sessions per second, but this depends on your hardware configuration.</span></span>

</div>

<div>

## <a name="my-clients-are-running-out-of-memory-what-should-i-do"></a><span data-ttu-id="381fd-115">Недостаточно памяти для моих клиентов.</span><span class="sxs-lookup"><span data-stu-id="381fd-115">My clients are running out of memory.</span></span> <span data-ttu-id="381fd-116">Что мне делать?</span><span class="sxs-lookup"><span data-stu-id="381fd-116">What should I do?</span></span>

<span data-ttu-id="381fd-117">Если на ваших клиентах недостаточно памяти, нужно уменьшить количество пользователей на компьютере.</span><span class="sxs-lookup"><span data-stu-id="381fd-117">If your clients are running out of memory, you need to reduce the number of users per computer.</span></span>

</div>

<div>

## <a name="my-clients-are-at-100-percent-cpu-all-the-time-what-should-i-do"></a><span data-ttu-id="381fd-118">У моих клиентов в 100 процентов ЦП все время.</span><span class="sxs-lookup"><span data-stu-id="381fd-118">My clients are at 100 percent CPU all the time.</span></span> <span data-ttu-id="381fd-119">Что мне делать?</span><span class="sxs-lookup"><span data-stu-id="381fd-119">What should I do?</span></span>

<span data-ttu-id="381fd-120">Если ваши клиенты работают с очень высокими ЦП после входа в систему, необходимо уменьшить количество пользователей на компьютере.</span><span class="sxs-lookup"><span data-stu-id="381fd-120">If your clients are running with very high CPU after all the users have logged on, you need to reduce the number of users per computer.</span></span> <span data-ttu-id="381fd-121">Высокие выгрузки ЦП приемлемы, но если они постоянны, вам нужно уменьшить нагрузку.</span><span class="sxs-lookup"><span data-stu-id="381fd-121">High CPU spikes are acceptable, but if it is sustained, you need to reduce the load.</span></span>

</div>

<div>

## <a name="can-i-run-the-tool-on-the-server-itself"></a><span data-ttu-id="381fd-122">Можно ли запускать средство на самом сервере?</span><span class="sxs-lookup"><span data-stu-id="381fd-122">Can I run the tool on the server itself?</span></span>

<span data-ttu-id="381fd-123">№</span><span class="sxs-lookup"><span data-stu-id="381fd-123">No.</span></span> <span data-ttu-id="381fd-124">Этот сценарий не поддерживается и может завершиться сбоем из-за несоответствия двоичного файла.</span><span class="sxs-lookup"><span data-stu-id="381fd-124">This scenario is not supported and may fail due to a binary mismatch.</span></span> <span data-ttu-id="381fd-125">Кроме того, так как точка предназначена для измерения потребления ресурсов на сервере, при запуске этого средства будут вырисовываться небессмысленные измерения.</span><span class="sxs-lookup"><span data-stu-id="381fd-125">Also, because the point is to measure resource consumption on the server, running the tool there would render the measurements meaningless.</span></span>

</div>

<div>

## <a name="can-i-run-lyncperftoolexe-on-a-virtual-server-or-on-microsoft-hyper-v-server-20082012"></a><span data-ttu-id="381fd-126">Можно ли запускать Линкперфтул. exe на виртуальном сервере или на сервере Microsoft Hyper-V 2008/2012?</span><span class="sxs-lookup"><span data-stu-id="381fd-126">Can I run LyncPerfTool.exe on a Virtual Server or on Microsoft Hyper-V Server 2008/2012?</span></span>

<span data-ttu-id="381fd-127">Да.</span><span class="sxs-lookup"><span data-stu-id="381fd-127">Yes.</span></span>

</div>

<div>

## <a name="what-does-mpop-mean"></a><span data-ttu-id="381fd-128">Что означает МПОП?</span><span class="sxs-lookup"><span data-stu-id="381fd-128">What does MPOP mean?</span></span>

<span data-ttu-id="381fd-129">МПОП означает несколько точек присутствия.</span><span class="sxs-lookup"><span data-stu-id="381fd-129">MPOP stands for multiple points of presence.</span></span> <span data-ttu-id="381fd-130">Она предназначена для моделирования ситуации, когда пользователи входят в состав Lync 2013 с нескольких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="381fd-130">It is meant to simulate the scenario where users are logged on to Lync 2013 from multiple machines.</span></span> <span data-ttu-id="381fd-131">Обратите внимание, что в Линкперфтул. exe каждая конечная точка использует профиль по умолчанию (то есть профиль не разбивается между двумя точками присутствия).</span><span class="sxs-lookup"><span data-stu-id="381fd-131">Note that in LyncPerfTool.exe, each endpoint uses the default profile (that is, the profile is not split between the two points of presence).</span></span>

</div>

<div>

## <a name="i-started-lyncperftoolexe-but-nothing-is-happening-whats-going-on"></a><span data-ttu-id="381fd-132">Я начал Линкперфтул. exe, но ничего не происходит.</span><span class="sxs-lookup"><span data-stu-id="381fd-132">I started LyncPerfTool.exe but nothing is happening.</span></span> <span data-ttu-id="381fd-133">Что происходит?</span><span class="sxs-lookup"><span data-stu-id="381fd-133">What’s going on?</span></span>

<span data-ttu-id="381fd-134">Установите флажок Общий счетчик активных конечных точек на клиентах, чтобы проверить, подключаются ли пользователи.</span><span class="sxs-lookup"><span data-stu-id="381fd-134">Check the Total Active Endpoints counter on the clients to see if the users are connecting.</span></span> <span data-ttu-id="381fd-135">Если пользователи не подключаются, проверьте конфигурацию Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="381fd-135">If users are not connecting, verify your Lync Server 2013 configuration.</span></span> <span data-ttu-id="381fd-136">Как правило, эта проблема возникает из-за того, что имя сервера, префикс пользователя или пароль неверны.</span><span class="sxs-lookup"><span data-stu-id="381fd-136">This issue usually occurs because the server name, the user prefix, or the password is incorrect.</span></span> <span data-ttu-id="381fd-137">Обратите внимание, что внешние клиенты должны указать прокси-сервер доступа в качестве значения Таржетсервер.</span><span class="sxs-lookup"><span data-stu-id="381fd-137">Note that external clients should specify the Access Proxy as the TargetServer value.</span></span> <span data-ttu-id="381fd-138">Проверьте порт в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="381fd-138">Verify the port in the configuration file.</span></span>

</div>

<div>

## <a name="how-do-i-know-something-is-happening"></a><span data-ttu-id="381fd-139">Как узнать, что происходит?</span><span class="sxs-lookup"><span data-stu-id="381fd-139">How do I know something is happening?</span></span>

<span data-ttu-id="381fd-140">Различные счетчики производительности Линкперфтул указывают, нужно ли пользователям подключаться к ним и выполнять действия.</span><span class="sxs-lookup"><span data-stu-id="381fd-140">The various LyncPerfTool performance counters indicate whether or not users are connecting and performing actions.</span></span> <span data-ttu-id="381fd-141">Однако простой способ проверки — войти в одну из учетных записей с помощью Lync 2013 и выполнить нужное действие.</span><span class="sxs-lookup"><span data-stu-id="381fd-141">However, an easy way to check is to log on to one of the accounts by using Lync 2013 and performing the action you want.</span></span>

</div>

<div>

## <a name="i-have-live-communications-server-2007-r2-capacity-planning-tools-andor-lync-server-2010-installed-is-that-ok"></a><span data-ttu-id="381fd-142">У меня установлено средство планирования производительности Live Communications Server 2007 R2 и/или Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="381fd-142">I have Live Communications Server 2007 R2 Capacity Planning Tools and/or Lync Server 2010 installed.</span></span> <span data-ttu-id="381fd-143">Это нормально?</span><span class="sxs-lookup"><span data-stu-id="381fd-143">Is that OK?</span></span>

<span data-ttu-id="381fd-144">№</span><span class="sxs-lookup"><span data-stu-id="381fd-144">No.</span></span> <span data-ttu-id="381fd-145">Возникли проблемы с совместимостью, и вы должны удалить все предыдущие версии этого продукта.</span><span class="sxs-lookup"><span data-stu-id="381fd-145">There are interoperability issues, and you must uninstall all previous versions of this product.</span></span>

</div>

<div>

## <a name="will-the-stress-and-performance-tools-set-up-the-caa-call-information-server-topology"></a><span data-ttu-id="381fd-146">Настроили ли средства для работы с загрузкой и производительностью топология сервера информации о звонке Каа?</span><span class="sxs-lookup"><span data-stu-id="381fd-146">Will the Stress and Performance tools set up the CAA Call Information server topology?</span></span>

<span data-ttu-id="381fd-147">№</span><span class="sxs-lookup"><span data-stu-id="381fd-147">No.</span></span> <span data-ttu-id="381fd-148">Средства создают только пользователи, контакты и списки рассылки, а также имитируют нагрузку пользователей.</span><span class="sxs-lookup"><span data-stu-id="381fd-148">The tools only create users, contacts, and distribution lists, and simulate user load.</span></span>

</div>

<div>

## <a name="what-is-the-maximum-number-of-users-that-the-tools-support"></a><span data-ttu-id="381fd-149">Каково максимальное число пользователей, которые поддерживаются средствами?</span><span class="sxs-lookup"><span data-stu-id="381fd-149">What is the maximum number of users that the tools support?</span></span>

<span data-ttu-id="381fd-150">С помощью этих средств мы создали общее количество пользователей 80 000 и выполнили тестирование с учетом всех пользователей 30 000.</span><span class="sxs-lookup"><span data-stu-id="381fd-150">We have created up to a total of 80,000 users and executed tests totaling 30,000 users, using these tools.</span></span> <span data-ttu-id="381fd-151">Мы рекомендуем использовать не более 120 000 пользователей, хотя в соответствии с техническими ограничениями допускают более высокие значения (в зависимости от того, какое оборудование доступно для клиента и сервера).</span><span class="sxs-lookup"><span data-stu-id="381fd-151">We suggest a maximum of 120,000 users, although the technical limitations allow for a higher value, depending on the client and server hardware available.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

