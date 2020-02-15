---
title: 'Lync Server 2013: Конфигурация узла-наблюдателя тестирования'
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
ms.openlocfilehash: a8d0fe8500bd676ef1a9a33c9197dfeac7783c10
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="19e9e-102">Конфигурация узла-наблюдателя тестирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19e9e-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19e9e-103">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="19e9e-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19e9e-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="19e9e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="19e9e-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="19e9e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19e9e-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="19e9e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="19e9e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="19e9e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19e9e-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="19e9e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="19e9e-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="19e9e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="19e9e-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsWatcherNodeConfiguration</strong> .</span><span class="sxs-lookup"><span data-stu-id="19e9e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="19e9e-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="19e9e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="19e9e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="19e9e-112">Description</span></span>

<span data-ttu-id="19e9e-113">Если вы используете Microsoft System Center Operations Manager для мониторинга Lync Server 2013, то у вас есть возможность настройки "узлы-наблюдатели": компьютеры, периодически и автоматически выполняющие искусственную транзакцию, чтобы убедиться в том, что Lync Server работает. наличие.</span><span class="sxs-lookup"><span data-stu-id="19e9e-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="19e9e-114">Узлы-наблюдатели назначаются пулам и управляются с помощью командлетов **CsWatcherNodeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="19e9e-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="19e9e-115">Следует отметить, что при использовании System Center Operations Manager устанавливать узлы-наблюдатели не обязательно.</span><span class="sxs-lookup"><span data-stu-id="19e9e-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="19e9e-116">Вы по-прежнему можете отслеживать систему без использования узлов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="19e9e-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="19e9e-117">Единственное отличие заключается в том, что все искусственные транзакции, которые требуется запустить, необходимо вызвать вручную, а не автоматически вызывать Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="19e9e-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="19e9e-118">Командлет **Test-CsWatcherNodeConfiguration** позволяет проверить правильность настройки узла-наблюдателя и присвоения действительного пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19e9e-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="19e9e-119">Обратите внимание на то, что командлет **Test-CsWatcherNodeConfiguration** должен быть запущен на самом узле-наблюдателе.</span><span class="sxs-lookup"><span data-stu-id="19e9e-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="19e9e-120">Командлет не может выполняться для удаленных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="19e9e-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="19e9e-121">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="19e9e-121">Running the test</span></span>

<span data-ttu-id="19e9e-122">Следующая команда проверяет параметры конфигурации для каждого узла-наблюдателя, используемого в Организации.</span><span class="sxs-lookup"><span data-stu-id="19e9e-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="19e9e-123">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="19e9e-123">Determining success or failure</span></span>

<span data-ttu-id="19e9e-124">В приведенном ниже примере показана успешная система с четырьмя пограничными серверами.</span><span class="sxs-lookup"><span data-stu-id="19e9e-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="19e9e-125">Проверка целевого пула atl-cs-001.litwareinc.com в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="19e9e-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="19e9e-126">Успех: целевой пул atl-cs-001.litwareinc.com существует в топологии.</span><span class="sxs-lookup"><span data-stu-id="19e9e-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="19e9e-127">Успешно: в целевом пуле atl-cs-001.litwareinc.com установлена роль регистратора.</span><span class="sxs-lookup"><span data-stu-id="19e9e-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="19e9e-128">Успех: целевой пул atl-cs-001.litwareinc.com поддерживаемая версия.</span><span class="sxs-lookup"><span data-stu-id="19e9e-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="19e9e-129">Успех: номер порта для 5061 целевого пула atl-cs-001.litwareinc.com правильный.</span><span class="sxs-lookup"><span data-stu-id="19e9e-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="19e9e-130">Запущена проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="19e9e-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="19e9e-131">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="19e9e-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="19e9e-132">Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.</span><span class="sxs-lookup"><span data-stu-id="19e9e-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="19e9e-133">Выполняется проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="19e9e-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="19e9e-134">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="19e9e-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="19e9e-135">Проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя, завершена.</span><span class="sxs-lookup"><span data-stu-id="19e9e-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="19e9e-136">Обнаруженный тип проверки подлинности — Negotiate.</span><span class="sxs-lookup"><span data-stu-id="19e9e-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="19e9e-137">Успешная проверка существования учетных данных тестового пользователя SIP: user1@ atl-cs-001.litwareinc.com в хранилище управления учетными данными.</span><span class="sxs-lookup"><span data-stu-id="19e9e-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="19e9e-138">Успешная проверка существования учетных данных тестового пользователя SIP: user2@ atl-cs-001.litwareinc.com в хранилище управления учетными данными.</span><span class="sxs-lookup"><span data-stu-id="19e9e-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="19e9e-139">Запущена проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="19e9e-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="19e9e-140">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="19e9e-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="19e9e-141">Предупреждение: atl-cs-001.litwareinc.com пула имеет регистратор</span><span class="sxs-lookup"><span data-stu-id="19e9e-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="19e9e-142">роль установлена, но тестовые пользователи не настроены.</span><span class="sxs-lookup"><span data-stu-id="19e9e-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="19e9e-143">Проверка наличия отсутствующих пулов в конфигурации узла-наблюдателя завершена.</span><span class="sxs-lookup"><span data-stu-id="19e9e-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="19e9e-144">Проверка наличия разделов реестра узла-наблюдателя, созданных при установке узла-наблюдателя, — это</span><span class="sxs-lookup"><span data-stu-id="19e9e-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="19e9e-145">выполняться.</span><span class="sxs-lookup"><span data-stu-id="19e9e-145">started.</span></span> <span data-ttu-id="19e9e-146">Если обнаружена какая-либо ошибка, она будет распечатана.</span><span class="sxs-lookup"><span data-stu-id="19e9e-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="19e9e-147">Test-CsWatcherNodeConfiguration: не удается найти раздел реестра работоспособности в</span><span class="sxs-lookup"><span data-stu-id="19e9e-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="19e9e-148">\\Программное\\обеспечение связи в режиме реального времени Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="19e9e-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="19e9e-149">Убедитесь, что узел наблюдателя. MSI является</span><span class="sxs-lookup"><span data-stu-id="19e9e-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="19e9e-150">правильно установлен.</span><span class="sxs-lookup"><span data-stu-id="19e9e-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="19e9e-151">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="19e9e-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="19e9e-152">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsWatcherNodeConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="19e9e-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="19e9e-153">Узел-наблюдатель установлен неправильно.</span><span class="sxs-lookup"><span data-stu-id="19e9e-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="19e9e-154">Тестовые пользователи не настроены.</span><span class="sxs-lookup"><span data-stu-id="19e9e-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="19e9e-155">См. также</span><span class="sxs-lookup"><span data-stu-id="19e9e-155">See Also</span></span>


[<span data-ttu-id="19e9e-156">Get — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="19e9e-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="19e9e-157">New — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="19e9e-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="19e9e-158">Remove — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="19e9e-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="19e9e-159">Set — CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="19e9e-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

