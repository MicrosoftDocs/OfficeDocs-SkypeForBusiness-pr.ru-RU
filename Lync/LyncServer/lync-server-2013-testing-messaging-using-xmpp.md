---
title: 'Lync Server 2013: тестирование сообщений с помощью КСМПП'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="b7fbb-102">Тестирование сообщений с помощью КСМПП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7fbb-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7fbb-103">_**Тема последнего изменения:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="b7fbb-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7fbb-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="b7fbb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="b7fbb-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="b7fbb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7fbb-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="b7fbb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="b7fbb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7fbb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7fbb-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="b7fbb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="b7fbb-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="b7fbb-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета <strong>Test-ксксмппим</strong> .</span><span class="sxs-lookup"><span data-stu-id="b7fbb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="b7fbb-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b7fbb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="b7fbb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b7fbb-112">Description</span></span>

<span data-ttu-id="b7fbb-113">Расширенный протокол обмена сообщениями (КСМПП) является стандартным протоколом связи (на основе XML), который используется для отправки сообщений через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="b7fbb-114">КСМПП первоначально назывался Жаббер и поддерживается несколькими приложениями для обмена сообщениями в Интернете и общения, например с помощью Google чата и Facebook.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="b7fbb-115">Командлет **Test-ксксмппим** подтверждает, что пользователь может обмениваться мгновенными сообщениями с пользователем в сети КСМПП.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="b7fbb-116">Обратите внимание, что для успешного завершения этого теста необходимо иметь действительный SIP-адрес для пользователя КСМПП, и этот адрес SIP должен находиться в сети, которая была настроена как разрешенная КСМПП партнер.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="b7fbb-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="b7fbb-117">Running the test</span></span>

<span data-ttu-id="b7fbb-118">В следующем примере проверяются возможности обмена мгновенными сообщениями КСМПП для atl-cs-001.litwareinc.com пула.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b7fbb-119">Эта команда будет работать только в том случае, если тестовые пользователи определены для пула atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="b7fbb-120">Если это так, команда определит, может ли первый тестовый пользователь отправить мгновенное сообщение КСМПП пользователю с адресом SIP adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="b7fbb-121">Если тестовые пользователи не заданы, команда завершится сбоем, так как не будет определять, какой пользователь должен войти в систему.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="b7fbb-122">Если вы не определили тестовых пользователей для пула, необходимо включить параметр Усерсипаддресс и учетные данные пользователя, который должна использовать команда при попытке входа в систему.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="b7fbb-123">Команды, показанные в следующем примере, проверяют возможность определенного пользователя (плана litwareinc\\почтового) войти в систему для отправки КСМПП мгновенного сообщения пользователю adelaney@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="b7fbb-124">Для этого в первой команде примера используется командлет Get-Credential для создания объекта учетных данных интерфейса командной строки Windows PowerShell, содержащего имя и пароль пользователя почтового Вронский.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="b7fbb-125">(Поскольку имя для входа в\\плана litwareinc почтового было включено в качестве параметра, в диалоговом окне Запрос учетных данных Windows PowerShell требуется, чтобы администратор введет пароль для учетной записи почтового Вронский). Полученный объект учетных данных затем сохраняется в переменной с именем $cred 1.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="b7fbb-126">Вторая команда проверяет, может ли пользователь войти в atl-cs-001.litwareinc.com пула и отправить мгновенное сообщение КСМПП.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="b7fbb-127">Для выполнения этой задачи вызывается командлет **Test-ксксмппим** , вместе с четырьмя параметрами: таржетфкдн (полное доменное имя пула регистраторов). Получатель (адрес SIP пользователя, которому адресовано сообщение); Усеркредентиал (объект Windows PowerShell, который включает в себя учетные данные пользователя для почтового Вронский); и Усерсипаддресс (SIP-адрес, соответствующий предоставленным учетным данным пользователя).</span><span class="sxs-lookup"><span data-stu-id="b7fbb-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="b7fbb-128">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="b7fbb-128">Determining success or failure</span></span>

<span data-ttu-id="b7fbb-129">Если КСМПП обмен мгновенными сообщениями правильно настроен, вы получите вывод примерно так, чтобы свойство Result пометило **"успешно".**</span><span class="sxs-lookup"><span data-stu-id="b7fbb-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="b7fbb-130">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7fbb-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7fbb-131">Результат: успех</span><span class="sxs-lookup"><span data-stu-id="b7fbb-131">Result : Success</span></span>

<span data-ttu-id="b7fbb-132">Задержка: 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="b7fbb-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="b7fbb-133">Сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="b7fbb-133">Error Message :</span></span>

<span data-ttu-id="b7fbb-134">Диагностик</span><span class="sxs-lookup"><span data-stu-id="b7fbb-134">Diagnosis :</span></span>

<span data-ttu-id="b7fbb-135">Если указанные пользователи не могут использовать КСМПП обмен мгновенными сообщениями, результат будет показан как **сбой**, а дополнительные сведения будут записаны в свойствах Error и диагноз.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="b7fbb-136">Предупреждение: не удалось прочитать номер порта регистратора для заданного полного имени</span><span class="sxs-lookup"><span data-stu-id="b7fbb-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="b7fbb-137">доменное имя (FQDN).</span><span class="sxs-lookup"><span data-stu-id="b7fbb-137">domain name (FQDN).</span></span> <span data-ttu-id="b7fbb-138">С помощью номера порта регистратора по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-138">Using default Registrar port number.</span></span> <span data-ttu-id="b7fbb-139">Ошибка</span><span class="sxs-lookup"><span data-stu-id="b7fbb-139">Exception:</span></span>

<span data-ttu-id="b7fbb-140">System. InvalidOperationException: в топологии не обнаружены подходящие кластеры.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="b7fbb-141">скорость</span><span class="sxs-lookup"><span data-stu-id="b7fbb-141">at</span></span>

<span data-ttu-id="b7fbb-142">Microsoft. RTC. Management. Синсетиктрансактионс. Сипсинсетиктрансактион. Триретри</span><span class="sxs-lookup"><span data-stu-id="b7fbb-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="b7fbb-143">Еверегистрарпортфромтопологи (Int32& Регистрарпортнумбер)</span><span class="sxs-lookup"><span data-stu-id="b7fbb-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="b7fbb-144">Целевое полное доменное имя: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="b7fbb-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="b7fbb-145">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="b7fbb-145">Result : Failure</span></span>

<span data-ttu-id="b7fbb-146">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="b7fbb-146">Latency : 00:00:00</span></span>

<span data-ttu-id="b7fbb-147">Сообщение об ошибке: 10060, не удалось установить соединение из-за того, что подключенная сторона</span><span class="sxs-lookup"><span data-stu-id="b7fbb-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="b7fbb-148">не отвечает на запросы в течение определенного периода времени или</span><span class="sxs-lookup"><span data-stu-id="b7fbb-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="b7fbb-149">не удалось установить соединение, так как подключенный узел имеет</span><span class="sxs-lookup"><span data-stu-id="b7fbb-149">established connection failed because connected host has</span></span>

<span data-ttu-id="b7fbb-150">не удалось ответить на 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b7fbb-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b7fbb-151">Внутреннее исключение: сбой при попытке подключения из-за того, что</span><span class="sxs-lookup"><span data-stu-id="b7fbb-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="b7fbb-152">связь с абонентом завершилась неправильно после определенного периода</span><span class="sxs-lookup"><span data-stu-id="b7fbb-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="b7fbb-153">время или соединение не удалось установить, так как подключенный узел</span><span class="sxs-lookup"><span data-stu-id="b7fbb-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="b7fbb-154">не удалось ответить 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="b7fbb-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="b7fbb-155">Диагностик</span><span class="sxs-lookup"><span data-stu-id="b7fbb-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="b7fbb-156">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="b7fbb-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="b7fbb-157">Ниже приведены некоторые распространенные причины, по которым может произойти сбой **Test-ксксмппим** :</span><span class="sxs-lookup"><span data-stu-id="b7fbb-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="b7fbb-158">Предоставлено неправильное значение параметра.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="b7fbb-159">Если используется, необязательные параметры необходимо настроить правильно, или тест завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="b7fbb-160">Повторите выполнение команды без дополнительных параметров и проверьте, выполняется ли это успешно.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="b7fbb-161">Эта команда завершится сбоем, если конфигурация шлюза КСМПП неправильно настроена или еще не развернута.</span><span class="sxs-lookup"><span data-stu-id="b7fbb-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b7fbb-162">См. также</span><span class="sxs-lookup"><span data-stu-id="b7fbb-162">See Also</span></span>


[<span data-ttu-id="b7fbb-163">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="b7fbb-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

