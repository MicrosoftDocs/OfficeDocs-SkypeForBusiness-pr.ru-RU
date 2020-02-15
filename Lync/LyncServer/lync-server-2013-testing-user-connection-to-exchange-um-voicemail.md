---
title: 'Lync Server 2013: тестирование подключения пользователя к голосовой почте Exchange единой системы обмена сообщениями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae68b9a5fb2e03fd08fbc7cd06507c54a383197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="5515d-102">Тестирование подключения пользователя к голосовой почте Exchange единой системы обмена сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5515d-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5515d-103">_**Последнее изменение темы:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="5515d-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5515d-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="5515d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5515d-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="5515d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5515d-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="5515d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5515d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5515d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5515d-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5515d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5515d-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5515d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5515d-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsExUMVoiceMail</strong> .</span><span class="sxs-lookup"><span data-stu-id="5515d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="5515d-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5515d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5515d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5515d-112">Description</span></span>

<span data-ttu-id="5515d-113">Командлет **Test-CsExUMVoiceMail** позволяет администраторам убедиться в том, что пользователь может получить доступ к службе единой системы обмена сообщениями Microsoft Exchange Server 2013 и использовать ее.</span><span class="sxs-lookup"><span data-stu-id="5515d-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="5515d-114">Для этого командлет подключается к службе единой системы обмена сообщениями и оставляет голосовое сообщение в нужном почтовом ящике.</span><span class="sxs-lookup"><span data-stu-id="5515d-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="5515d-115">Это может быть системное голосовое сообщение или WAV-файл, записанный самим пользователем.</span><span class="sxs-lookup"><span data-stu-id="5515d-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5515d-116">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="5515d-116">Running the test</span></span>

<span data-ttu-id="5515d-117">В следующем примере показано, как проверить подключение голосовой почты единой системы обмена сообщениями Exchange для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5515d-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5515d-118">Эта команда будет работать только в том случае, если тестовые пользователи были определены для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5515d-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5515d-119">В этом случае команда определит, может ли первый тестовый пользователь использовать голосовую почту единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="5515d-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="5515d-120">Если тестовые пользователи не были настроены для пула, команда завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="5515d-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="5515d-121">Команды, показанные в следующем примере, проверяют подключение голосовой почты единой системы обмена сообщениями\\Exchange для пользователя litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="5515d-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="5515d-122">Для этого первая команда в примере использует командлет **Get – Credential** для создания объекта учетных данных интерфейса командной строки Windows PowerShell для пользователя litwareinc\\kenmyer.</span><span class="sxs-lookup"><span data-stu-id="5515d-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="5515d-123">Обратите внимание, что для этой учетной записи необходимо указать пароль, чтобы создать допустимый объект учетных данных и убедиться, что командлет **Test-CsExUMVoiceMail** может выполнить его проверку.</span><span class="sxs-lookup"><span data-stu-id="5515d-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="5515d-124">Вторая команда в примере использует предоставленный объект учетных данных ($x) и SIP-адрес пользователя litwareinc\\kenmyer, чтобы определить, может ли этот пользователь подключиться к голосовой почте единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="5515d-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="5515d-125">Команда, показанная в следующем примере, является вариантом команды, показанной в примере 1; в этом случае параметр OutLoggerVariable включается для создания подробного журнала каждого шага, выполняемого с помощью **Test-CsExUMVoiceMail** , кмдлетанд успешное или неуспешное выполнение каждого из этих действий.</span><span class="sxs-lookup"><span data-stu-id="5515d-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="5515d-126">Для этого параметр OutLoggerVariable добавляется вместе со значением параметра Ексумтекст; Это приводит к тому, что подробные сведения о ведении журнала хранятся в переменной с именем $ExumTest.</span><span class="sxs-lookup"><span data-stu-id="5515d-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="5515d-127">В завершающей команде в примере метод ToXML () используется для преобразования данных журнала в формат XML.</span><span class="sxs-lookup"><span data-stu-id="5515d-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="5515d-128">После этого XML-данные записываются в файл с именем C:\\Logs\\, воицемаилтест. XML, с помощью командлета Out-File.</span><span class="sxs-lookup"><span data-stu-id="5515d-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5515d-129">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="5515d-129">Determining success or failure</span></span>

<span data-ttu-id="5515d-130">Если интеграция Exchange настроена правильно, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success**.</span><span class="sxs-lookup"><span data-stu-id="5515d-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="5515d-131">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5515d-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5515d-132">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="5515d-132">Result : Success</span></span>

<span data-ttu-id="5515d-133">Задержка: 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="5515d-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="5515d-134">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="5515d-134">Error Message :</span></span>

<span data-ttu-id="5515d-135">Диагност</span><span class="sxs-lookup"><span data-stu-id="5515d-135">Diagnosis :</span></span>

<span data-ttu-id="5515d-136">Если указанный пользователь не может подключаться к голосовой почте, результат будет отображаться как **сбой**, а в свойствах диагностики ошибок и диагностики будет записана дополнительная информация:</span><span class="sxs-lookup"><span data-stu-id="5515d-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5515d-137">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="5515d-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="5515d-138">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5515d-138">domain name (FQDN).</span></span> <span data-ttu-id="5515d-139">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5515d-139">Using default Registrar port number.</span></span> <span data-ttu-id="5515d-140">Возникновения</span><span class="sxs-lookup"><span data-stu-id="5515d-140">Exception:</span></span>

<span data-ttu-id="5515d-141">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="5515d-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="5515d-142">в</span><span class="sxs-lookup"><span data-stu-id="5515d-142">at</span></span>

<span data-ttu-id="5515d-143">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="5515d-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="5515d-144">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="5515d-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="5515d-145">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5515d-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5515d-146">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="5515d-146">Result : Failure</span></span>

<span data-ttu-id="5515d-147">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5515d-147">Latency : 00:00:00</span></span>

<span data-ttu-id="5515d-148">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="5515d-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5515d-149">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="5515d-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5515d-150">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="5515d-150">established connection failed because connected host has</span></span>

<span data-ttu-id="5515d-151">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5515d-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5515d-152">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="5515d-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5515d-153">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="5515d-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5515d-154">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="5515d-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5515d-155">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5515d-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5515d-156">Диагност</span><span class="sxs-lookup"><span data-stu-id="5515d-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5515d-157">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="5515d-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="5515d-158">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsExUMVoiceMail** :</span><span class="sxs-lookup"><span data-stu-id="5515d-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="5515d-159">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="5515d-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5515d-160">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="5515d-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5515d-161">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="5515d-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5515d-162">Эта команда завершится с ошибками, если сервер Exchange неправильно настроен или еще не развернут.</span><span class="sxs-lookup"><span data-stu-id="5515d-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5515d-163">См. также</span><span class="sxs-lookup"><span data-stu-id="5515d-163">See Also</span></span>


[<span data-ttu-id="5515d-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="5515d-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

