---
title: 'Lync Server 2013: тестирование обмена сообщениями Exchange с уведомлениями Lync'
description: 'Lync Server 2013: тестирование Exchange с уведомлениями Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdf453bfdaab7e7b6bdaae8b67ac7759c0d55af4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560625"
---
# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="e93e6-103">Тестирование Exchange в уведомления Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e93e6-103">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e93e6-104">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="e93e6-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e93e6-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="e93e6-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e93e6-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="e93e6-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e93e6-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="e93e6-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e93e6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e93e6-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e93e6-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="e93e6-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e93e6-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e93e6-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e93e6-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="e93e6-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="e93e6-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e93e6-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e93e6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e93e6-113">Description</span></span>

<span data-ttu-id="e93e6-114">Командлет **Test-CsExStorageNotification** используется для проверки того, что служба уведомлений Microsoft Exchange Server 2013 может уведомлять Lync Server 2013 о внесении обновлений в список контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="e93e6-114">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="e93e6-115">Это командлет доступен только при использовании единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="e93e6-115">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e93e6-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="e93e6-116">Running the test</span></span>

<span data-ttu-id="e93e6-117">Команда, показанная в примере 1, проверяет, может ли служба хранилища Lync Server подключаться к службе уведомлений почтовых ящиков Microsoft Exchange Server для пользователя sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="e93e6-117">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="e93e6-118">В данном примере в качестве привязки WCF используется NetNamedPipe.</span><span class="sxs-lookup"><span data-stu-id="e93e6-118">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e93e6-119">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="e93e6-119">Determining success or failure</span></span>

<span data-ttu-id="e93e6-120">Если интеграция Exchange настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное**:</span><span class="sxs-lookup"><span data-stu-id="e93e6-120">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="e93e6-121">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e93e6-121">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e93e6-122">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="e93e6-122">Result : Success</span></span>

<span data-ttu-id="e93e6-123">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e93e6-123">Latency : 00:00:00</span></span>

<span data-ttu-id="e93e6-124">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="e93e6-124">Error Message :</span></span>

<span data-ttu-id="e93e6-125">Диагност</span><span class="sxs-lookup"><span data-stu-id="e93e6-125">Diagnosis :</span></span>

<span data-ttu-id="e93e6-126">Если указанный пользователь не может получать уведомления, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="e93e6-126">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e93e6-127">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e93e6-127">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e93e6-128">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="e93e6-128">Result : Failure</span></span>

<span data-ttu-id="e93e6-129">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="e93e6-129">Latency : 00:00:00</span></span>

<span data-ttu-id="e93e6-130">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="e93e6-130">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="e93e6-131">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="e93e6-131">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="e93e6-132">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="e93e6-132">established connection failed because connected host has</span></span>

<span data-ttu-id="e93e6-133">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="e93e6-133">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="e93e6-134">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="e93e6-134">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="e93e6-135">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="e93e6-135">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="e93e6-136">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="e93e6-136">time, or established connection failed because connected host</span></span>

<span data-ttu-id="e93e6-137">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="e93e6-137">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="e93e6-138">Диагност</span><span class="sxs-lookup"><span data-stu-id="e93e6-138">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e93e6-139">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="e93e6-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="e93e6-140">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsExStorageNotification** :</span><span class="sxs-lookup"><span data-stu-id="e93e6-140">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="e93e6-141">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="e93e6-141">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e93e6-142">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="e93e6-142">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e93e6-143">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="e93e6-143">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e93e6-144">Эта команда завершится с ошибками, если сервер Microsoft Exchange неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="e93e6-144">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e93e6-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e93e6-145">See Also</span></span>


[<span data-ttu-id="e93e6-146">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="e93e6-146">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

