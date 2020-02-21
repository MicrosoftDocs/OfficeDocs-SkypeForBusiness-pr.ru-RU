---
title: 'Lync Server 2013: Проверка проверки подлинности клиента Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 490068a9c9eec3e582471d9ff228b9bbccad43bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194092"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="a0020-102">Тестирование проверки подлинности клиента Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0020-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0020-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="a0020-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a0020-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="a0020-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a0020-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="a0020-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a0020-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="a0020-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a0020-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0020-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a0020-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="a0020-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a0020-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="a0020-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a0020-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="a0020-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="a0020-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a0020-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a0020-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a0020-112">Description</span></span>

<span data-ttu-id="a0020-113">Командлет Test-CsClientAuth позволяет определить, может ли пользователь войти на сервер Lync с помощью сертификата клиента, можно запустить командлет Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="a0020-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="a0020-114">После вызова командлета Test-CsClientAuth командлет свяжется со службой подготовки сертификатов и загрузит копию всех клиентских сертификатов для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0020-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="a0020-115">Если сертификат клиента можно найти и скачать, Test-CsClientAuth будет пытаться войти в систему с помощью этого сертификата.</span><span class="sxs-lookup"><span data-stu-id="a0020-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="a0020-116">Если вход выполнен успешно, то Test-CsClientAuth выйдет из системы и сообщит о том, что тест успешно выполнен.</span><span class="sxs-lookup"><span data-stu-id="a0020-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="a0020-117">Если сертификат клиента не удается обнаружить или загрузить, или командлет не может войти с его помощью в систему, Test-CsClientAuth сообщает о неудачном завершении проверки.</span><span class="sxs-lookup"><span data-stu-id="a0020-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a0020-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="a0020-118">Running the test</span></span>

<span data-ttu-id="a0020-119">Командлет Test-CsClientAuth запускается с помощью учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0020-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="a0020-120">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="a0020-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="a0020-121">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда система вызывает Test-CsClientAuth:</span><span class="sxs-lookup"><span data-stu-id="a0020-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="a0020-122">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="a0020-122">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a0020-123">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="a0020-123">Determining success or failure</span></span>

<span data-ttu-id="a0020-124">Если указанный пользователь может войти на сервер Lync Server с помощью клиентского сертификата, будет выведен результат, подобный следующему, при этом свойство Result помечается как **успешное:**</span><span class="sxs-lookup"><span data-stu-id="a0020-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="a0020-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a0020-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a0020-126">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="a0020-126">Result : Success</span></span>

<span data-ttu-id="a0020-127">Задержка: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="a0020-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="a0020-128">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="a0020-128">Error :</span></span>

<span data-ttu-id="a0020-129">Диагност</span><span class="sxs-lookup"><span data-stu-id="a0020-129">Diagnosis :</span></span>

<span data-ttu-id="a0020-130">Если указанный пользователь не может выполнить вход в систему, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="a0020-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a0020-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a0020-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a0020-132">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="a0020-132">Result : Failure</span></span>

<span data-ttu-id="a0020-133">Задержка: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="a0020-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="a0020-134">Ошибка: не удалось скачать сертификат CS для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0020-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="a0020-135">Проверка наличия</span><span class="sxs-lookup"><span data-stu-id="a0020-135">Check if</span></span>

<span data-ttu-id="a0020-136">предоставлены правильные URI и учетные данные.</span><span class="sxs-lookup"><span data-stu-id="a0020-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="a0020-137">Диагност</span><span class="sxs-lookup"><span data-stu-id="a0020-137">Diagnosis :</span></span>

<span data-ttu-id="a0020-138">Например, в предыдущем выходном состоянии не удалось выполнить тест, так как не удалось найти действительный сертификат клиента для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0020-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="a0020-139">Вы можете получить список сертификатов клиентов, выданных пользователю, выполнив команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a0020-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="a0020-140">Если Test-CsClientAuth завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="a0020-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="a0020-141">Если включен параметр Verbose, командлет Test-CsClientAuth возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0020-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="a0020-142">Например:</span><span class="sxs-lookup"><span data-stu-id="a0020-142">For example:</span></span>

<span data-ttu-id="a0020-143">Попытка скачать сертификат CS для пользователя: kenmyer@litwareinc.com конечная точка: Степид</span><span class="sxs-lookup"><span data-stu-id="a0020-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="a0020-144">URL-адрес веб-службы:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="a0020-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="a0020-145">Не удалось скачать сертификат CS из веб-службы.</span><span class="sxs-lookup"><span data-stu-id="a0020-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="a0020-146">ПРОВЕРЯТЬ</span><span class="sxs-lookup"><span data-stu-id="a0020-146">CHECK:</span></span>

<span data-ttu-id="a0020-147">\-URL-адрес веб-службы является допустимым, а веб-службы функционируют</span><span class="sxs-lookup"><span data-stu-id="a0020-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="a0020-148">\-Если для проверки\\\\подлинности используется ПИН-код фонено, убедитесь, что они совпадают с URI пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0020-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="a0020-149">\-При использовании проверки\\подлинности NTLM Kerberos убедитесь, что вы предоставили действительные учетные данные.</span><span class="sxs-lookup"><span data-stu-id="a0020-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a0020-150">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="a0020-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="a0020-151">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsClientAuth:</span><span class="sxs-lookup"><span data-stu-id="a0020-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="a0020-152">Указана недопустимая учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0020-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="a0020-153">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a0020-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="a0020-154">Учетная запись пользователя действительна, но в настоящее время учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0020-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="a0020-155">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="a0020-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="a0020-156">Если свойство Enabled имеет значение false, это означает, что в настоящее время у пользователя не включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a0020-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="a0020-157">Тестовый пользователь может не иметь действительный сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="a0020-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="a0020-158">Сведения о сертификатах клиентов, назначенных пользователю, можно получить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="a0020-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

