---
title: Использование пакетов управления Lync Server 2010 в сценарии сосуществования
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc198abe47d76abae2ae49f426ac433c29129790
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="7657d-102">Использование пакетов управления Lync Server 2010 в сценарии сосуществования</span><span class="sxs-lookup"><span data-stu-id="7657d-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7657d-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7657d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7657d-104">Многие клиенты принимают программу развертывания внутри своих предприятий, в которых пользователи последовательно переносятся из Microsoft Lync Server 2010 в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7657d-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="7657d-105">Администраторы в этих компаниях будут следить за мониторингом обеих версий Lync Server, чтобы гарантировать, что все их конечные пользователи получат лучшие возможности для общения.</span><span class="sxs-lookup"><span data-stu-id="7657d-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="7657d-106">В этом сценарии пакет управления Lync Server 2013 поддерживает параллельный путь миграции с пакетом управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7657d-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="7657d-107">В Lync Server 2010 компьютеры Lync Server были обнаружены с помощью документа топологии, хранящегося в центральном хранилище управления.</span><span class="sxs-lookup"><span data-stu-id="7657d-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="7657d-108">В этой конфигурации один компьютер сообщает о существовании всех остальных компьютеров Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7657d-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="7657d-109">Пакеты управления для Lync Server 2013 теперь используют обнаружение на уровне компьютера, а не центральный механизм обнаружения, который использовался в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7657d-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="7657d-110">Это значит, что каждый агент System Center обнаруживает себя и сообщает о своем существовании System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="7657d-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="7657d-111">Использование обнаружения на уровне компьютера упрощает администрирование инфраструктуры System Center, а также поддерживает различные версии пакетов управления Lync Server (например, пакеты управления для Lync Server 2010 и пакеты управления для Lync Server 2013) для упрощения совместного сосуществования.</span><span class="sxs-lookup"><span data-stu-id="7657d-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="7657d-112">Для поддержки этой миграции сначала необходимо обновить имеющийся мониторинг Lync Server 2010, чтобы избежать пропусков в объеме.</span><span class="sxs-lookup"><span data-stu-id="7657d-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="7657d-113">Для этого выберите существующий компьютер Lync Server 2010 для обслуживания сценария центрального обнаружения для Lync Server 2010 перед обновлением центрального хранилища управления до Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7657d-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="7657d-114">Это процесс из четырех шагов:</span><span class="sxs-lookup"><span data-stu-id="7657d-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="7657d-115">Обновите пакеты управления Lync Server 2010 до накопительного пакета обновления 7.</span><span class="sxs-lookup"><span data-stu-id="7657d-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="7657d-116">Предписывает компьютеру Lync Server 2010 запустить сценарий центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="7657d-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="7657d-117">Переопределите потенциальный вариант центрального обнаружения в пакете управления Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7657d-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="7657d-118">Убедитесь, что кандидат центрального обнаружения был обнаружен.</span><span class="sxs-lookup"><span data-stu-id="7657d-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="7657d-119">Выполнение скрипта центрального обнаружения на компьютере Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7657d-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="7657d-120">Чтобы назначить компьютер, не являющийся центральному хранилищу управления (например, сервер переднего плана Lync Server) для обработки центрального обнаружения, необходимо создать следующий раздел реестра на сервере, не являющемся центральным хранилищем управления:</span><span class="sxs-lookup"><span data-stu-id="7657d-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="7657d-121">Программа\\\\HKLM централдисковерикандидате\\работоспособности\\\\связи в реальном времени Майкрософт</span><span class="sxs-lookup"><span data-stu-id="7657d-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="7657d-122">Этот раздел реестра можно создать с помощью следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="7657d-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="7657d-123">В меню **Пуск** щелкните **Выполнить**.</span><span class="sxs-lookup"><span data-stu-id="7657d-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="7657d-124">В диалоговом окне **Выполнить** введите **regedit**, затем нажмите ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7657d-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="7657d-125">В редакторе реестра разверните узел **hKey\_Local\_Machine**, разверните **программное обеспечение**, разверните **Майкрософт**, а затем — **связь в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="7657d-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="7657d-p105">Щелкните правой кнопкой пункт **Health**, выберите **Создать**, затем щелкните **Раздел**. Если раздел **Health** не существует, щелкните правой кнопкой **Real-Time Communications**, выберите пункт **Создать** и щелкните **Раздел**. После создания раздел введите "Health" и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="7657d-p105">Right-click **Health**, click **New**, and then click **Key**. If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**. When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="7657d-129">После создания нового раздела введите **CentralDiscoveryCandidate** и нажмите клавишу ВВОД, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="7657d-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="7657d-130">Для вступления этого изменения в силу может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="7657d-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="7657d-131">Чтобы это произошло незамедлительно остановите и перезапустите службу агента работоспособности.</span><span class="sxs-lookup"><span data-stu-id="7657d-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="7657d-132">Чтобы перезапустить службу агента работоспособности, выполните следующую процедуру на компьютере Lync Server 2010:</span><span class="sxs-lookup"><span data-stu-id="7657d-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="7657d-133">Нажмите кнопку **Пуск**, последовательно щелкните пункты **Все программы**, **Стандартные**, щелкните правой кнопкой мыши значок **Командная строка** и в контекстном меню выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="7657d-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="7657d-134">В окне консоли введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7657d-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="7657d-p107">Появится сообщение: "Выполняется остановка службы System Center Management", после чего отображается второе сообщение об остановке службы. После этого в можете перезапустить службу, введя следующую команду и нажав клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7657d-p107">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="7657d-137">Переопределение кандидата центрального обнаружения в пакете управления Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7657d-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="7657d-138">После указания компьютеру Lync Server 2010 сообщить о компьютерах Lync Server 2010 необходимо сообщить пакет управления Lync Server 2010 также об этом изменении.</span><span class="sxs-lookup"><span data-stu-id="7657d-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="7657d-139">Для этого необходимо создать переопределение в этом пакете управления.</span><span class="sxs-lookup"><span data-stu-id="7657d-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="7657d-140">Это можно сделать посредством следующей процедуры:</span><span class="sxs-lookup"><span data-stu-id="7657d-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="7657d-141">В консоли Operations Manager щелкните **Создание**.</span><span class="sxs-lookup"><span data-stu-id="7657d-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="7657d-142">На вкладке "Создание" разверните узел **Объекты пакета управления**, щелкните **Обнаружения объекта** и выберите **Область**.</span><span class="sxs-lookup"><span data-stu-id="7657d-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="7657d-143">В диалоговом окне **Определение области объектов пакета управления** выберите элемент с конечным объектом **Кандидат обнаружения LS** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7657d-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="7657d-144">Обратите внимание, что кандидат на обнаружение LS отображается только в том случае, если установлен пакет управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7657d-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="7657d-145">В консоли Operations Manager щелкните правой кнопкой **Кандидат обнаружения LS** выберите пункт **Переопределения**, наведите указатель на параметр **Переопределить обнаружение объектов** и щелкните **Для всех объектов класса: кандидат обнаружения LS**.</span><span class="sxs-lookup"><span data-stu-id="7657d-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="7657d-146">В диалоговом окне **Переопределение свойств** установите флажок **Переопределить** рядом с параметром **WatcherNode Fqdn центрального обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="7657d-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="7657d-147">Введите полное доменное имя компьютера Lync Server 2010 в поля **переопределить значение** и **эффективное значение** .</span><span class="sxs-lookup"><span data-stu-id="7657d-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="7657d-148">Установите флажок **Принудительный** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7657d-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="7657d-p111">После создания переопределения нужно перезапустить службу работоспособности на корневом сервере управления. Для этого выполните следующие действия на корневом сервере управления:</span><span class="sxs-lookup"><span data-stu-id="7657d-p111">After you have created the override, you need to restart the health service on the Root Management Server. To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="7657d-151">Нажмите кнопку **Пуск**, последовательно щелкните пункты **Все программы**, **Стандартные**, щелкните правой кнопкой мыши значок **Командная строка** и в контекстном меню выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="7657d-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="7657d-152">В окне консоли введите следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7657d-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="7657d-p112">Появится сообщение: "Выполняется остановка службы System Center Management", после чего отображается второе сообщение об остановке службы. После этого в можете перезапустить службу, введя следующую команду и нажав клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="7657d-p112">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped. After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="7657d-155">Проверка того, что кандидат центрального обнаружения был обнаружен</span><span class="sxs-lookup"><span data-stu-id="7657d-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="7657d-156">Последним шагом перед обновлением центрального хранилища управления является обеспечение обнаружения нового кандидата центра управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="7657d-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="7657d-157">Для этого откройте консоль Operations Manager и щелкните "Мониторинг".</span><span class="sxs-lookup"><span data-stu-id="7657d-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="7657d-158">На вкладке "Мониторинг" разверните узел **Работоспособность Microsoft Lync Server 2010**, разверните **Обнаружение топологии**, а затем щелкните **Просмотр состояния обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="7657d-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="7657d-159">Убедитесь, что в строке есть **путь**, в котором указано полное доменное имя кандидата центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="7657d-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="7657d-160">Вы также должны убедиться, что состояние компьютера указано как **Работоспособен**.</span><span class="sxs-lookup"><span data-stu-id="7657d-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

