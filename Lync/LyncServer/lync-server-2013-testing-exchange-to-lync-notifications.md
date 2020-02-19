---
title: 'Lync Server 2013: тестирование обмена сообщениями Exchange с уведомлениями Lync'
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
ms.openlocfilehash: 14f192d71bbe36bd4e417c06e93152858ac761ae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="84f55-102">Тестирование Exchange в уведомления Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84f55-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84f55-103">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="84f55-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84f55-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="84f55-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="84f55-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="84f55-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84f55-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="84f55-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="84f55-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="84f55-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84f55-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="84f55-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="84f55-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="84f55-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="84f55-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsExStorageNotification</strong> .</span><span class="sxs-lookup"><span data-stu-id="84f55-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="84f55-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="84f55-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="84f55-112">Описание</span><span class="sxs-lookup"><span data-stu-id="84f55-112">Description</span></span>

<span data-ttu-id="84f55-113">Командлет **Test-CsExStorageNotification** используется для проверки того, что служба уведомлений Microsoft Exchange Server 2013 может уведомлять Lync Server 2013 о внесении обновлений в список контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="84f55-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="84f55-114">Это командлет доступен только при использовании единого хранилища контактов.</span><span class="sxs-lookup"><span data-stu-id="84f55-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="84f55-115">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="84f55-115">Running the test</span></span>

<span data-ttu-id="84f55-116">Команда, показанная в примере 1, проверяет, может ли служба хранилища Lync Server подключаться к службе уведомлений почтовых ящиков Microsoft Exchange Server для пользователя sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="84f55-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="84f55-117">В данном примере в качестве привязки WCF используется NetNamedPipe.</span><span class="sxs-lookup"><span data-stu-id="84f55-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="84f55-118">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="84f55-118">Determining success or failure</span></span>

<span data-ttu-id="84f55-119">Если интеграция Exchange настроена правильно, вы получите выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **успешное**:</span><span class="sxs-lookup"><span data-stu-id="84f55-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="84f55-120">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="84f55-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="84f55-121">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="84f55-121">Result : Success</span></span>

<span data-ttu-id="84f55-122">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="84f55-122">Latency : 00:00:00</span></span>

<span data-ttu-id="84f55-123">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="84f55-123">Error Message :</span></span>

<span data-ttu-id="84f55-124">Диагност</span><span class="sxs-lookup"><span data-stu-id="84f55-124">Diagnosis :</span></span>

<span data-ttu-id="84f55-125">Если указанный пользователь не может получать уведомления, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="84f55-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="84f55-126">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="84f55-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="84f55-127">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="84f55-127">Result : Failure</span></span>

<span data-ttu-id="84f55-128">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="84f55-128">Latency : 00:00:00</span></span>

<span data-ttu-id="84f55-129">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="84f55-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="84f55-130">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="84f55-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="84f55-131">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="84f55-131">established connection failed because connected host has</span></span>

<span data-ttu-id="84f55-132">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="84f55-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="84f55-133">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="84f55-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="84f55-134">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="84f55-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="84f55-135">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="84f55-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="84f55-136">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="84f55-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="84f55-137">Диагност</span><span class="sxs-lookup"><span data-stu-id="84f55-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="84f55-138">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="84f55-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="84f55-139">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsExStorageNotification** :</span><span class="sxs-lookup"><span data-stu-id="84f55-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="84f55-140">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="84f55-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="84f55-141">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="84f55-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="84f55-142">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="84f55-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="84f55-143">Эта команда завершится с ошибками, если сервер Microsoft Exchange неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="84f55-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84f55-144">См. также</span><span class="sxs-lookup"><span data-stu-id="84f55-144">See Also</span></span>


[<span data-ttu-id="84f55-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="84f55-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

