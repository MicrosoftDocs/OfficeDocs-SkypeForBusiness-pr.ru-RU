---
title: 'Lync Server 2013: Конфигурация узла-наблюдателя тестирования'
description: 'Lync Server 2013: Конфигурация узла-наблюдателя тестирования.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1eeb141eee011d7e06f5dd49e483e026484d733
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546845"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="0994d-103">Конфигурация узла-наблюдателя тестирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0994d-103">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0994d-104">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="0994d-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0994d-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="0994d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0994d-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="0994d-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0994d-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="0994d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0994d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0994d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0994d-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="0994d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0994d-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0994d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0994d-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="0994d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="0994d-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0994d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0994d-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0994d-113">Description</span></span>

<span data-ttu-id="0994d-114">Если вы используете Microsoft System Center Operations Manager для мониторинга Lync Server 2013, то у вас есть возможность настройки "узлов-наблюдателей": компьютеры, которые периодически и автоматически выполняют искусственные транзакции, чтобы убедиться, что Lync Server работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="0994d-114">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="0994d-115">Узлы-наблюдатели назначаются пулам и управляются с помощью командлетов **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0994d-115">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="0994d-116">Следует отметить, что при использовании System Center Operations Manager устанавливать узлы-наблюдатели не обязательно.</span><span class="sxs-lookup"><span data-stu-id="0994d-116">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="0994d-117">Вы по-прежнему можете отслеживать систему без использования узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="0994d-117">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="0994d-118">Единственное отличие заключается в том, что все искусственные транзакции, которые требуется запустить, необходимо вызвать вручную, а не автоматически вызывать Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="0994d-118">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="0994d-119">Командлет **Test-CsWatcherNodeConfiguration** позволяет проверить правильность настройки узла-наблюдателя и присвоения действительного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0994d-119">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="0994d-120">Обратите внимание на то, что командлет **Test-CsWatcherNodeConfiguration** должен быть запущен на самом узле-наблюдателе.</span><span class="sxs-lookup"><span data-stu-id="0994d-120">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="0994d-121">Командлет не может выполняться для удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="0994d-121">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0994d-122">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="0994d-122">Running the test</span></span>

<span data-ttu-id="0994d-123">Следующая команда проверяет параметры конфигурации для каждого узла-наблюдателя, используемого в Организации.</span><span class="sxs-lookup"><span data-stu-id="0994d-123">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0994d-124">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="0994d-124">Determining success or failure</span></span>

<span data-ttu-id="0994d-125">В приведенном ниже примере показана успешная система с четырьмя пограничными серверами.</span><span class="sxs-lookup"><span data-stu-id="0994d-125">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="0994d-126">Проверка целевого пула atl-cs-001.litwareinc.com в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="0994d-126">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="0994d-127">Успех: целевой пул atl-cs-001.litwareinc.com существует в топологии.</span><span class="sxs-lookup"><span data-stu-id="0994d-127">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="0994d-128">Успешно: в целевом пуле atl-cs-001.litwareinc.com установлена роль регистратора.</span><span class="sxs-lookup"><span data-stu-id="0994d-128">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="0994d-129">Успех: целевой пул atl-cs-001.litwareinc.com поддерживаемая версия.</span><span class="sxs-lookup"><span data-stu-id="0994d-129">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="0994d-130">Успех: номер порта для 5061 целевого пула atl-cs-001.litwareinc.com правильный.</span><span class="sxs-lookup"><span data-stu-id="0994d-130">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="0994d-131">Запущена проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="0994d-131">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="0994d-132">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="0994d-132">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="0994d-133">Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.</span><span class="sxs-lookup"><span data-stu-id="0994d-133">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="0994d-134">Выполняется проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="0994d-134">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="0994d-135">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="0994d-135">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="0994d-136">Проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя, завершена.</span><span class="sxs-lookup"><span data-stu-id="0994d-136">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="0994d-137">Обнаруженный тип проверки подлинности — Negotiate.</span><span class="sxs-lookup"><span data-stu-id="0994d-137">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="0994d-138">Успешная проверка существования учетных данных тестового пользователя SIP: user1@ atl-cs-001.litwareinc.com в хранилище управления учетными данными.</span><span class="sxs-lookup"><span data-stu-id="0994d-138">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="0994d-139">Успешная проверка существования учетных данных тестового пользователя SIP: user2@ atl-cs-001.litwareinc.com в хранилище управления учетными данными.</span><span class="sxs-lookup"><span data-stu-id="0994d-139">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="0994d-140">Запущена проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="0994d-140">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="0994d-141">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="0994d-141">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="0994d-142">Предупреждение: atl-cs-001.litwareinc.com пула имеет регистратор</span><span class="sxs-lookup"><span data-stu-id="0994d-142">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="0994d-143">роль установлена, но тестовые пользователи не настроены.</span><span class="sxs-lookup"><span data-stu-id="0994d-143">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="0994d-144">Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.</span><span class="sxs-lookup"><span data-stu-id="0994d-144">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="0994d-145">Проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя, — это</span><span class="sxs-lookup"><span data-stu-id="0994d-145">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="0994d-146">выполняться.</span><span class="sxs-lookup"><span data-stu-id="0994d-146">started.</span></span> <span data-ttu-id="0994d-147">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="0994d-147">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="0994d-148">Test-CsWatcherNodeConfiguration: не удается найти раздел реестра работоспособности в</span><span class="sxs-lookup"><span data-stu-id="0994d-148">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="0994d-149">Программное обеспечение \\ \\ связи в режиме реального времени Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0994d-149">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="0994d-150">Убедитесь, что узел наблюдателя. MSI является</span><span class="sxs-lookup"><span data-stu-id="0994d-150">Make sure watcher node .msi is</span></span>

<span data-ttu-id="0994d-151">правильно установлен.</span><span class="sxs-lookup"><span data-stu-id="0994d-151">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0994d-152">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="0994d-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="0994d-153">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsWatcherNodeConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="0994d-153">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="0994d-154">Узел-наблюдатель установлен неправильно.</span><span class="sxs-lookup"><span data-stu-id="0994d-154">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="0994d-155">Тестовые пользователи не настроены.</span><span class="sxs-lookup"><span data-stu-id="0994d-155">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0994d-156">См. также</span><span class="sxs-lookup"><span data-stu-id="0994d-156">See Also</span></span>


[<span data-ttu-id="0994d-157">Get — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0994d-157">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="0994d-158">New — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0994d-158">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="0994d-159">Remove — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0994d-159">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="0994d-160">Set — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0994d-160">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

