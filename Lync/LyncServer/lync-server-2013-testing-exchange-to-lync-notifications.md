---
title: 'Lync Server 2013: проверка Exchange на уведомления Lync'
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
ms.openlocfilehash: 37f163d5a43dce9672535ec3d78f360bcec8d926
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a><span data-ttu-id="5d125-102">Проверка Exchange для уведомлений Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d125-102">Testing Exchange to Lync notifications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d125-103">_**Тема последнего изменения:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="5d125-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d125-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="5d125-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5d125-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="5d125-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d125-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="5d125-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5d125-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5d125-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d125-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="5d125-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5d125-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="5d125-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5d125-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксексстораженотификатион</strong> .</span><span class="sxs-lookup"><span data-stu-id="5d125-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExStorageNotification</strong> cmdlet.</span></span> <span data-ttu-id="5d125-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5d125-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5d125-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5d125-112">Description</span></span>

<span data-ttu-id="5d125-113">Командлет **Test-ксексстораженотификатион** используется для подтверждения того, что служба уведомлений сервера Microsoft Exchange Server 2013 может уведомлять Lync Server 2013 о внесении обновлений в список контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="5d125-113">The **Test-CsExStorageNotification** cmdlet is used to verify that the Microsoft Exchange Server 2013 notification service can notify Lync Server 2013 any time updates are made to a user's Contact List.</span></span> <span data-ttu-id="5d125-114">Этот командлет действует только в том случае, если вы используете единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="5d125-114">This cmdlet is valid only if you are using the unified contact store.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5d125-115">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="5d125-115">Running the test</span></span>

<span data-ttu-id="5d125-116">Команда, показанная в примере 1, проверяет, может ли служба хранилища Lync Server подключиться к службе уведомлений почтового ящика сервера Microsoft Exchange Server для пользователя sip:kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5d125-116">The command shown in Example 1 tests to see whether the Lync Server Storage Service can connect to the Microsoft Exchange Server mailbox notification service for the user sip:kenmyer@litwareinc.com.</span></span> <span data-ttu-id="5d125-117">В этом примере Нетнамедпипе используется в качестве привязки WCF.</span><span class="sxs-lookup"><span data-stu-id="5d125-117">In this example, NetNamedPipe is used as the WCF binding.</span></span>

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5d125-118">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="5d125-118">Determining success or failure</span></span>

<span data-ttu-id="5d125-119">Если интеграция с Exchange настроена правильно, вы получите вывод примерно так, чтобы свойство Result пометило " **успешно**".</span><span class="sxs-lookup"><span data-stu-id="5d125-119">If Exchange integration is configured correctly , you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="5d125-120">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5d125-120">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5d125-121">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="5d125-121">Result : Success</span></span>

<span data-ttu-id="5d125-122">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5d125-122">Latency : 00:00:00</span></span>

<span data-ttu-id="5d125-123">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="5d125-123">Error Message :</span></span>

<span data-ttu-id="5d125-124">Диагностик</span><span class="sxs-lookup"><span data-stu-id="5d125-124">Diagnosis :</span></span>

<span data-ttu-id="5d125-125">Если указанный пользователь не может получать уведомления, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="5d125-125">If the specified user can't receive notifications, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5d125-126">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5d125-126">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5d125-127">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="5d125-127">Result : Failure</span></span>

<span data-ttu-id="5d125-128">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5d125-128">Latency : 00:00:00</span></span>

<span data-ttu-id="5d125-129">Сообщение об ошибке: 10060, не удалось установить соединение из-за того, что подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="5d125-129">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5d125-130">не отвечает на запросы в течение определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="5d125-130">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5d125-131">не удалось установить соединение, так как подключенный узел имеет</span><span class="sxs-lookup"><span data-stu-id="5d125-131">established connection failed because connected host has</span></span>

<span data-ttu-id="5d125-132">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5d125-132">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5d125-133">Внутреннее исключение: сбой при попытке подключения из-за того, что</span><span class="sxs-lookup"><span data-stu-id="5d125-133">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5d125-134">связь с абонентом завершилась неправильно после определенного периода</span><span class="sxs-lookup"><span data-stu-id="5d125-134">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5d125-135">время или соединение не удалось установить, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="5d125-135">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5d125-136">не удалось ответить 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5d125-136">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5d125-137">Диагностик</span><span class="sxs-lookup"><span data-stu-id="5d125-137">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5d125-138">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="5d125-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="5d125-139">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксексстораженотификатион** :</span><span class="sxs-lookup"><span data-stu-id="5d125-139">Here are some common reasons why **Test-CsExStorageNotification** might fail:</span></span>

  - <span data-ttu-id="5d125-140">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="5d125-140">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5d125-141">Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="5d125-141">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5d125-142">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="5d125-142">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5d125-143">Эта команда завершится сбоем, если сервер Microsoft Exchange неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="5d125-143">This command will fail if the Microsoft Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5d125-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5d125-144">See Also</span></span>


[<span data-ttu-id="5d125-145">Test-CsExStorageConnectivity</span><span class="sxs-lookup"><span data-stu-id="5d125-145">Test-CsExStorageConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

