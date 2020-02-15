---
title: 'Lync Server 2013: тестирование входа в Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbacccabc98829c90e01dc49099b65b829274c82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="5eb2e-102">Тестирование входа в Lync Phone Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5eb2e-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5eb2e-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5eb2e-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5eb2e-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="5eb2e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5eb2e-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="5eb2e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5eb2e-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="5eb2e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5eb2e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5eb2e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5eb2e-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="5eb2e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5eb2e-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5eb2e-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Ксфонебутстрап.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="5eb2e-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5eb2e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5eb2e-112">Description</span></span>

<span data-ttu-id="5eb2e-113">Командлет Test-Ксфонебутстрап позволяет администраторам выполнять вход в систему с устройства, совместимого с Lync 2013 Phone Edition, с помощью номера телефона и ПИН-кода, назначенного ему.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="5eb2e-114">(На самом деле не требуется никаких устройств для выполнения теста.)</span><span class="sxs-lookup"><span data-stu-id="5eb2e-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="5eb2e-115">Чтобы командлет Test-CsPhoneBootstrap мог выполнить проверку, пул регистратора, в котором размещается учетная запись проверяемого пользователя, должен обнаруживаться по протоколу DHCP.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="5eb2e-116">Чтобы определить, может ли регистратор быть обнаруживаемым таким образом, используйте командлет Get-CsRegistrarConfiguration и проверьте значение свойства Енабледхкпсервер.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="5eb2e-117">Если для этого свойства задано значение false, необходимо использовать Set-CsRegistrarConfiguration, чтобы задать для свойства значение true и сделать регистратор обнаруживаемым с помощью DHCP.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="5eb2e-118">Это также можно сделать с помощью корпоративного DHCP-сервера и настройки параметров, относящихся к Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5eb2e-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="5eb2e-119">Running the test</span></span>

<span data-ttu-id="5eb2e-120">Для запуска командлета Test-Ксфонебутстрап необходимо, как минимум, указать номер телефона и личный идентификационный номер клиента (ПИН-код) для допустимого пользователя Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="5eb2e-121">Например, эта команда проверяет возможность входа в систему для пользователя с номером телефона 12065551219 и ПИН-кодом 0712:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="5eb2e-122">Для более полной проверки можно также включить SIP адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="5eb2e-123">В этом случае телефонный номер, ПИН-код клиента и SIP-адрес должны быть действительными для успешного выполнения проверки:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="5eb2e-124">Дополнительные сведения можно найти в справочной документации по командлету [Test-ксфонебутстрап](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="5eb2e-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5eb2e-125">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="5eb2e-125">Determining success or failure</span></span>

<span data-ttu-id="5eb2e-126">Если указанный пользователь мог подключаться к Lync Server, будут получены выходные данные, аналогичные приведенным ниже, и свойство Result помечено как **Success.**</span><span class="sxs-lookup"><span data-stu-id="5eb2e-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5eb2e-127">TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="5eb2e-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="5eb2e-128">Цертпровисионингсервице. svc</span><span class="sxs-lookup"><span data-stu-id="5eb2e-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="5eb2e-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5eb2e-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5eb2e-130">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="5eb2e-130">Result : Success</span></span>

<span data-ttu-id="5eb2e-131">Задержка: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="5eb2e-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="5eb2e-132">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="5eb2e-132">Error :</span></span>

<span data-ttu-id="5eb2e-133">Диагност</span><span class="sxs-lookup"><span data-stu-id="5eb2e-133">Diagnosis :</span></span>

<span data-ttu-id="5eb2e-134">Если указанный пользователь не смог установить соединение, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5eb2e-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5eb2e-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5eb2e-136">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="5eb2e-136">Result : Failure</span></span>

<span data-ttu-id="5eb2e-137">Задержка: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="5eb2e-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="5eb2e-138">Ошибка: ошибка — не получен ответ для службы веб-билета.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="5eb2e-139">Диагност</span><span class="sxs-lookup"><span data-stu-id="5eb2e-139">Diagnosis :</span></span>

<span data-ttu-id="5eb2e-140">Предыдущие выходные данные подействовали, так как служба веб-билета не ответила.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="5eb2e-141">Это может быть вызвано проблемой с самой службой или из-за того, что адрес SIP, номер телефона или ПИН-код клиента передается в Test-Ксфонебутстрап.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="5eb2e-142">Вы можете проверить SIP адрес и номер телефона пользователя с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="5eb2e-143">Вы также можете убедиться, что у пользователя есть действительный ПИН-код, выполнив команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="5eb2e-144">Если Test-Ксфонебутстрап завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="5eb2e-145">Если включен параметр Verbose, командлет Test-Ксфонебутстрап возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="5eb2e-146">Например, ниже приведена часть выходных данных для неудачного входа в сеанс, в котором был включен неправильный ПИН-код:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="5eb2e-147">Использование проверки подлинности\\ПИН-кода с телефонным телефоном: 12065551219 PIN: 0712</span><span class="sxs-lookup"><span data-stu-id="5eb2e-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="5eb2e-148">Не удалось получить веб-билет</span><span class="sxs-lookup"><span data-stu-id="5eb2e-148">Could not get web ticket</span></span>

<span data-ttu-id="5eb2e-149">ПРОВЕРЯТЬ</span><span class="sxs-lookup"><span data-stu-id="5eb2e-149">CHECK :</span></span>

<span data-ttu-id="5eb2e-150">\-URL-адрес веб-службы является допустимым, а веб-службы функционируют</span><span class="sxs-lookup"><span data-stu-id="5eb2e-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="5eb2e-151">\-Если для проверки\\подлинности используется ПИН-код фонено, убедитесь, что они совпадают с URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="5eb2e-152">\-При использовании проверки\\подлинности NTLM Kerberos убедитесь, что вы предоставили действительные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5eb2e-153">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="5eb2e-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="5eb2e-154">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-Ксфонебутстрап:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="5eb2e-155">Возможно, указан недопустимый SIP-адрес.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="5eb2e-156">Для проверки правильности SIP-адреса можно использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="5eb2e-157">Возможно, указан недопустимый ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="5eb2e-158">Несмотря на то, что вы не можете получить PIN-код пользователя, вы можете убедиться, что у пользователя по крайней мере есть PIN-код, с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="5eb2e-159">Возможно, указан недопустимый номер телефона.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="5eb2e-160">Вы можете проверить телефон пользователя, выполнив команду следующего вида:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="5eb2e-161">Для пула регистратора не включена поддержка DHCP.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="5eb2e-162">Чтобы определить, включен ли для пула регистратора DHCP, выполните командлет Get-CsRegistrarConfiguration и проверьте значение свойства Енабледхкпсервер.</span><span class="sxs-lookup"><span data-stu-id="5eb2e-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="5eb2e-163">Пример:</span><span class="sxs-lookup"><span data-stu-id="5eb2e-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

