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
ms.openlocfilehash: 264cd8f1495840eb6dd86879f279110cd4de4784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="8a649-102">Использование пакетов управления Lync Server 2010 в сценарии сосуществования</span><span class="sxs-lookup"><span data-stu-id="8a649-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a649-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8a649-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8a649-104">Многие пользователи принимают программу выпуска в рамках своей организации, в которой пользователи последовательно переносятся из Microsoft Lync Server 2010 в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8a649-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="8a649-105">Администраторы в этих компаниях будут следить за тем, как выступают обе версии Lync Server, чтобы обеспечить максимально возможное взаимодействие между всеми конечными пользователями.</span><span class="sxs-lookup"><span data-stu-id="8a649-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="8a649-106">В этом сценарии пакет управления Lync Server 2013 поддерживает параллельный путь миграции с пакетом управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8a649-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="8a649-107">В Lync Server 2010 компьютеры Lync Server были обнаружены с помощью документа Topology, хранящегося в хранилище Центрального управления.</span><span class="sxs-lookup"><span data-stu-id="8a649-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="8a649-108">В этой конфигурации один компьютер сообщает о существовании всех компьютеров Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a649-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="8a649-109">Пакеты управления для Lync Server 2013 теперь используют обнаружение на уровне компьютера вместо центрального механизма обнаружения, который использовался в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8a649-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="8a649-110">Это означает, что каждый агент System Center, в сущности, будет самостоятельно обнаруживаться и сообщать о его существовании System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="8a649-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="8a649-111">Использование обнаружения на уровне компьютера упрощает администрирование инфраструктуры System Center, а также включает различные версии пакетов управления Lync Server (например, пакеты управления для Lync Server 2010 и пакеты управления для Lync Server 2013). для упрощения совместного существования.</span><span class="sxs-lookup"><span data-stu-id="8a649-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="8a649-112">Для поддержки этой миграции вам потребуется обновить имеющийся монитор Lync Server 2010, чтобы избежать пропусков в объеме.</span><span class="sxs-lookup"><span data-stu-id="8a649-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="8a649-113">Для этого выберите существующий компьютер Lync Server 2010 для обслуживания сценария центра обнаружения для Lync Server 2010 перед обновлением хранилища центрального управления до Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8a649-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="8a649-114">Это процесс с четырьмя шагами:</span><span class="sxs-lookup"><span data-stu-id="8a649-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="8a649-115">Обновите пакеты управления Lync Server 2010 до накопительного обновления 7.</span><span class="sxs-lookup"><span data-stu-id="8a649-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="8a649-116">Попросите сервера Lync Server 2010 запустить сценарий центрального обнаружения.</span><span class="sxs-lookup"><span data-stu-id="8a649-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="8a649-117">Переопределение кандидата на центральное обнаружение в пакете управления Microsoft Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8a649-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="8a649-118">Убедитесь в том, что новый кандидат на обнаружение в центре обнаружен.</span><span class="sxs-lookup"><span data-stu-id="8a649-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="8a649-119">Указание компьютера Lync Server 2010 для запуска сценария центрального обнаружения</span><span class="sxs-lookup"><span data-stu-id="8a649-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="8a649-120">Чтобы присвоить нецентрализованному хранилищу (например, внешнему серверу Lync) сервер для обработки центрального обнаружения, вам потребуется создать следующий раздел реестра на сервере хранилища, не являющегося центральным для управления.</span><span class="sxs-lookup"><span data-stu-id="8a649-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="8a649-121">Программа\\\\HKLM,\\Централдисковерикандидате исправность\\\\связи в режиме реального времени</span><span class="sxs-lookup"><span data-stu-id="8a649-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="8a649-122">Вы можете создать этот раздел реестра, выполнив описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8a649-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="8a649-123">Нажмите кнопку **Пуск** и выберите команду **выполнить**.</span><span class="sxs-lookup"><span data-stu-id="8a649-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="8a649-124">В диалоговом окне " **выполнить** " введите **regedit** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8a649-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="8a649-125">В редакторе реестра разверните раздел **hKey\_локальный\_компьютер**, разверните раздел **программы**, а затем разверните раздел **Microsoft**, а затем — **взаимодействие в режиме реального времени**.</span><span class="sxs-lookup"><span data-stu-id="8a649-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="8a649-126">Щелкните правой кнопкой мыши **работоспособность**, выберите команду **создать**, а затем — **раздел**.</span><span class="sxs-lookup"><span data-stu-id="8a649-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="8a649-127">Если ключ **работоспособности** не существует, щелкните правой кнопкой мыши в **режиме реального времени**и выберите пункт **создать**, а затем — **раздел**.</span><span class="sxs-lookup"><span data-stu-id="8a649-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="8a649-128">После создания нового ключа введите Health и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8a649-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="8a649-129">После создания нового ключа введите **централдисковерикандидате** и нажмите КЛАВИШу ввод, чтобы переименовать раздел.</span><span class="sxs-lookup"><span data-stu-id="8a649-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="8a649-130">Для выбора этого изменения может потребоваться несколько часов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="8a649-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="8a649-131">Чтобы изменения вступили в силу немедленно, остановите и перезапустите службу агента работоспособности.</span><span class="sxs-lookup"><span data-stu-id="8a649-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="8a649-132">Чтобы перезапустить службу агента работоспособности, выполните описанные ниже действия на компьютере Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8a649-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="8a649-133">Нажмите кнопку **Пуск**, **выберите все программы**, затем **стандартные**, щелкните правой кнопкой мыши **Командная строка**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8a649-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="8a649-134">В окне консоли введите указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8a649-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="8a649-135">Появится сообщение об ошибке "Служба управления System Center останавливается", после чего появится второе сообщение о том, что служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="8a649-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="8a649-136">После того как служба остановлена, вы можете перезапустить ее, введя следующую команду и нажав клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8a649-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="8a649-137">Переопределение кандидата на центральное обнаружение в пакете управления Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8a649-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="8a649-138">После уведомления компьютера Lync Server 2010 о том, что вы можете сообщить об этом изменении на компьютерах Lync Server 2010, вам также нужно будет сообщить пакет управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8a649-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="8a649-139">Для этого вам необходимо будет создать переопределение в пакете управления.</span><span class="sxs-lookup"><span data-stu-id="8a649-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="8a649-140">Это можно сделать, выполнив описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8a649-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="8a649-141">На консоли Operations Manager щелкните элемент **Разработка**.</span><span class="sxs-lookup"><span data-stu-id="8a649-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="8a649-142">На вкладке Разработка разверните **объекты пакета управления**, нажмите кнопку **Обнаружение объектов**, а затем выберите пункт **область**.</span><span class="sxs-lookup"><span data-stu-id="8a649-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="8a649-143">В диалоговом окне **объекты пакета управления областью** выберите нужный элемент с помощью целевого **кандидата обнаружения Ls** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8a649-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="8a649-144">Обратите внимание, что кандидат на обнаружение LS появится только в том случае, если вы установили пакет управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8a649-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="8a649-145">На консоли Operations Manager щелкните правой кнопкой мыши компонент- **кандидат обнаружения Ls**, наведите указатель на пункт **переопределения**, наведите указатель на пункт **Переопределить обнаружение объектов**, а затем выберите **для всех объектов класса: кандидат на обнаружение Ls**.</span><span class="sxs-lookup"><span data-stu-id="8a649-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="8a649-146">В диалоговом окне **Переопределение свойств** установите флажок **reoverride (переопределение** ) рядом с **ватчерноде FQDN (центр обнаружения параметров)**.</span><span class="sxs-lookup"><span data-stu-id="8a649-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="8a649-147">Введите полное доменное имя компьютера Lync Server 2010 в поля **переопределить значение** и **действующие значения** .</span><span class="sxs-lookup"><span data-stu-id="8a649-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="8a649-148">Установите флажок **принудительно** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8a649-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="8a649-149">После создания переопределения необходимо перезапустить службу работоспособности на корневом сервере управления.</span><span class="sxs-lookup"><span data-stu-id="8a649-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="8a649-150">Чтобы перезапустить службу работоспособности, выполните описанные ниже действия на корневом сервере управления.</span><span class="sxs-lookup"><span data-stu-id="8a649-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="8a649-151">Нажмите кнопку **Пуск**, **выберите все программы**, затем **стандартные**, щелкните правой кнопкой мыши **Командная строка**и выберите пункт **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="8a649-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="8a649-152">В окне консоли введите указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8a649-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="8a649-153">Вы увидите сообщение о том, что служба управления System Center останавливается, а вторая появляется сообщение о том, что обслуживание остановлено.</span><span class="sxs-lookup"><span data-stu-id="8a649-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="8a649-154">После того как служба остановлена, вы можете перезапустить ее, введя следующую команду и нажав клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="8a649-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="8a649-155">Проверка того, что обнаружен новый кандидат на центральное обнаружение</span><span class="sxs-lookup"><span data-stu-id="8a649-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="8a649-156">Последним шагом перед обновлением центрального хранилища управления является проверка того, что новый кандидат на центральное обнаружение обнаружен в пакете управления Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8a649-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="8a649-157">Для этого откройте консоль Operations Manager и выберите пункт наблюдение.</span><span class="sxs-lookup"><span data-stu-id="8a649-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="8a649-158">На вкладке Наблюдение разверните **Microsoft Lync Server 2010 Health**, разверните узел **Обнаружение топологии**и выберите **представление состояние обнаружения**.</span><span class="sxs-lookup"><span data-stu-id="8a649-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="8a649-159">Убедитесь в том, что в строке на дисплее указан **путь** , который содержит полное доменное имя для основного поиска-кандидата.</span><span class="sxs-lookup"><span data-stu-id="8a649-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="8a649-160">Кроме того, необходимо убедиться, что состояние компьютера отображается как **Исправен**.</span><span class="sxs-lookup"><span data-stu-id="8a649-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

