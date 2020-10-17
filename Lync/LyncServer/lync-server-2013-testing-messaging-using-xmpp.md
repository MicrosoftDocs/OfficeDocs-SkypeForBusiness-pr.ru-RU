---
title: 'Lync Server 2013: тестирование системы обмена сообщениями с помощью XMPP'
description: 'Lync Server 2013: тестирование системы обмена сообщениями с помощью XMPP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556305"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="5ac98-103">Тестирование системы обмена сообщениями с помощью XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5ac98-103">Testing messaging using XMPP in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ac98-104">_**Последнее изменение темы:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="5ac98-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ac98-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="5ac98-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5ac98-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="5ac98-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac98-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="5ac98-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5ac98-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ac98-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac98-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5ac98-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5ac98-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5ac98-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5ac98-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-CsXmppIM</strong> .</span><span class="sxs-lookup"><span data-stu-id="5ac98-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="5ac98-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5ac98-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5ac98-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5ac98-113">Description</span></span>

<span data-ttu-id="5ac98-114">XMPP — это протокол стандартных коммуникаций (основанный на XML), который используется для отправки сообщений в Интернете.</span><span class="sxs-lookup"><span data-stu-id="5ac98-114">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="5ac98-115">XMPP изначально назывался Jabber и поддерживается несколькими приложениями для обмена сообщениями и обмена сообщениями в Интернете, такими как Google Chat и Facebook Chat.</span><span class="sxs-lookup"><span data-stu-id="5ac98-115">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="5ac98-116">Командлет **Test-CsXmppIM** проверяет, может ли пользователь обмениваться мгновенными сообщениями с пользователем в сети XMPP.</span><span class="sxs-lookup"><span data-stu-id="5ac98-116">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="5ac98-117">Обратите внимание, что для успешного выполнения этой проверки необходимо иметь действительный SIP-адрес для пользователя XMPP, и этот SIP-адрес должен находиться в сети, настроенной в качестве разрешенного XMPP партнера.</span><span class="sxs-lookup"><span data-stu-id="5ac98-117">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5ac98-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="5ac98-118">Running the test</span></span>

<span data-ttu-id="5ac98-119">В следующем примере проверяется возможность обмена мгновенными сообщениями XMPP для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5ac98-119">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5ac98-120">Эта команда будет работать только в том случае, если тестовые пользователи определены для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="5ac98-120">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="5ac98-121">В этом случае команда определит, может ли первый тестовый пользователь отправить мгновенное сообщение XMPP пользователю с адресом SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5ac98-121">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="5ac98-122">Если тестовые пользователи не определены, команда завершится с ошибками, так как не будет определять, какой пользователь должен войти в систему.</span><span class="sxs-lookup"><span data-stu-id="5ac98-122">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="5ac98-123">Если тестовые пользователи не определены для пула, необходимо включить параметр UserSipAddress и учетные данные пользователя, который должна использовать команда при попытке входа в систему.</span><span class="sxs-lookup"><span data-stu-id="5ac98-123">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="5ac98-124">Команды, показанные в следующем примере, проверяют способность конкретного пользователя (litwareinc \\ Pilar) войти в систему для отправки XMPP мгновенного сообщения пользователю adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5ac98-124">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="5ac98-125">Для этого первая команда в примере использует командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="5ac98-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="5ac98-126">(Так как имя для входа litwareinc \\ Pilar было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell необходимо только ввести пароль для учетной записи Pilar Ackerman). Полученный объект учетных данных сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="5ac98-126">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="5ac98-127">Вторая команда проверяет, может ли этот пользователь войти в пул atl-cs-001.litwareinc.com и отправить мгновенное сообщение XMPP.</span><span class="sxs-lookup"><span data-stu-id="5ac98-127">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="5ac98-128">Для запуска этой задачи вызывается командлет **Test-CsXmppIm** , а также четыре параметра: TargetFqdn (полное доменное имя пула регистратора). Получатель (SIP-адрес пользователя, которому адресовано сообщение); UserCredential (объект Windows PowerShell, содержащий учетные данные пользователя Pilar Ackerman); и UserSipAddress (SIP-адрес, соответствующий предоставленным учетным данным пользователя).</span><span class="sxs-lookup"><span data-stu-id="5ac98-128">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5ac98-129">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="5ac98-129">Determining success or failure</span></span>

<span data-ttu-id="5ac98-130">Если вы правильно настроили обмен мгновенными сообщениями XMPP, вы получите выходные данные, аналогичные приведенным ниже, со свойством Result, помеченным как **успешно.**</span><span class="sxs-lookup"><span data-stu-id="5ac98-130">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5ac98-131">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5ac98-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5ac98-132">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="5ac98-132">Result : Success</span></span>

<span data-ttu-id="5ac98-133">Задержка: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="5ac98-133">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="5ac98-134">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="5ac98-134">Error Message :</span></span>

<span data-ttu-id="5ac98-135">Диагност</span><span class="sxs-lookup"><span data-stu-id="5ac98-135">Diagnosis :</span></span>

<span data-ttu-id="5ac98-136">Если указанные пользователи не могут использовать XMPP обмен мгновенными сообщениями, результат будет отображаться как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="5ac98-136">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5ac98-137">Предупреждение: не удалось считать номер порта регистратора для данного полного имени</span><span class="sxs-lookup"><span data-stu-id="5ac98-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="5ac98-138">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="5ac98-138">domain name (FQDN).</span></span> <span data-ttu-id="5ac98-139">Использование номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ac98-139">Using default Registrar port number.</span></span> <span data-ttu-id="5ac98-140">Возникновения</span><span class="sxs-lookup"><span data-stu-id="5ac98-140">Exception:</span></span>

<span data-ttu-id="5ac98-141">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="5ac98-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="5ac98-142">в</span><span class="sxs-lookup"><span data-stu-id="5ac98-142">at</span></span>

<span data-ttu-id="5ac98-143">Microsoft. RTC. Management. SyntheticTransactions. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="5ac98-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="5ac98-144">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="5ac98-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="5ac98-145">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5ac98-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5ac98-146">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="5ac98-146">Result : Failure</span></span>

<span data-ttu-id="5ac98-147">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5ac98-147">Latency : 00:00:00</span></span>

<span data-ttu-id="5ac98-148">Сообщение об ошибке: 10060, попытка подключения не удалась, так как подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="5ac98-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="5ac98-149">не ответил должным образом по истечении определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="5ac98-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="5ac98-150">не удалось установить подключение, так как у подключенного узла есть</span><span class="sxs-lookup"><span data-stu-id="5ac98-150">established connection failed because connected host has</span></span>

<span data-ttu-id="5ac98-151">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5ac98-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5ac98-152">Внутреннее исключение: сбой попытки подключения, так как</span><span class="sxs-lookup"><span data-stu-id="5ac98-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="5ac98-153">подключенная сторона не ответила должным образом после периода</span><span class="sxs-lookup"><span data-stu-id="5ac98-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="5ac98-154">время или установленное подключение не выполнено, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="5ac98-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="5ac98-155">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="5ac98-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="5ac98-156">Диагност</span><span class="sxs-lookup"><span data-stu-id="5ac98-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5ac98-157">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="5ac98-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="5ac98-158">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка **Test-CsXmppIM** :</span><span class="sxs-lookup"><span data-stu-id="5ac98-158">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="5ac98-159">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="5ac98-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="5ac98-160">Если используется, необязательные параметры должны быть настроены правильно или тест завершится с ошибками.</span><span class="sxs-lookup"><span data-stu-id="5ac98-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="5ac98-161">Выполните команду без необязательных параметров и проверьте, успешно ли это сделано.</span><span class="sxs-lookup"><span data-stu-id="5ac98-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="5ac98-162">Эта команда завершится с ошибками, если конфигурация шлюза XMPP неправильно настроена или еще не развернута.</span><span class="sxs-lookup"><span data-stu-id="5ac98-162">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ac98-163">См. также</span><span class="sxs-lookup"><span data-stu-id="5ac98-163">See Also</span></span>


[<span data-ttu-id="5ac98-164">Set — Ксксмппгатевайконфигуратион</span><span class="sxs-lookup"><span data-stu-id="5ac98-164">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

