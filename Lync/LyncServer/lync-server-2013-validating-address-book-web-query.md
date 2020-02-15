---
title: 'Lync Server 2013: Проверка веб-запроса адресной книги'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2db1e1e0a94a73c520a3beb0ea1375688b106cfc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="6ae8b-102">Проверка веб-запроса адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ae8b-102">Validating address book web query in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ae8b-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6ae8b-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ae8b-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="6ae8b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6ae8b-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="6ae8b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ae8b-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="6ae8b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6ae8b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ae8b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ae8b-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="6ae8b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6ae8b-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6ae8b-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="6ae8b-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6ae8b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6ae8b-112">Description</span></span>

<span data-ttu-id="6ae8b-113">Командлет Test-CsAddressBookWebQuery позволяет администраторам проверять, могут ли пользователи использовать службу веб-запросов адресной книги для поиска определенного контакта.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-113">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="6ae8b-114">При выполнении командлета Test-CsAddressBookWebQuery будет сначала подключаться к службе веб-билета, чтобы пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-114">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="6ae8b-115">Если проверка подлинности прошла успешно, командлет будет подключаться к службе веб-запросов адресной книги и искать указанного контакта.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-115">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="6ae8b-116">При нахождении контакта командлет попытается вернуть данные на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-116">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="6ae8b-117">Тест будет помечен как успешный, только если все эти действия можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-117">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="6ae8b-118">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="6ae8b-118">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6ae8b-119">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="6ae8b-119">Running the test</span></span>

<span data-ttu-id="6ae8b-120">Командлет Test-CsAddressBookWebQuery можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-120">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="6ae8b-121">Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя пула Lync Server и SIP-адрес пользователя, выступающего в качестве целевого объекта поиска.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="6ae8b-122">Пример:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-122">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="6ae8b-123">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо создать объект учетных данных Windows PowerShell, который содержит действительное имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-123">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="6ae8b-124">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда код вызывает Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-124">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6ae8b-125">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="6ae8b-125">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6ae8b-126">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="6ae8b-126">Determining success or failure</span></span>

<span data-ttu-id="6ae8b-127">Если указанный пользователь может подключаться к службе адресной книги и получать целевой адрес пользователя, будет выведен результат, подобный следующему, с свойством Result, помеченным как успешно:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-127">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="6ae8b-128">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6ae8b-128">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="6ae8b-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6ae8b-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6ae8b-130">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="6ae8b-130">Result : Success</span></span>

<span data-ttu-id="6ae8b-131">Задержка: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="6ae8b-131">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="6ae8b-132">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="6ae8b-132">Error :</span></span>

<span data-ttu-id="6ae8b-133">Диагност</span><span class="sxs-lookup"><span data-stu-id="6ae8b-133">Diagnosis :</span></span>

<span data-ttu-id="6ae8b-134">Если указанный пользователь не может подключиться или не удается получить целевой адрес пользователя, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-134">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6ae8b-135">TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6ae8b-135">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="6ae8b-136">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6ae8b-136">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6ae8b-137">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="6ae8b-137">Result : Failure</span></span>

<span data-ttu-id="6ae8b-138">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6ae8b-138">Latency : 00:00:00</span></span>

<span data-ttu-id="6ae8b-139">Ошибка: сбой запроса веб-службы адресной книги с кодом отклика</span><span class="sxs-lookup"><span data-stu-id="6ae8b-139">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="6ae8b-140">Ноентрифаунд.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-140">NoEntryFound.</span></span>

<span data-ttu-id="6ae8b-141">Диагност</span><span class="sxs-lookup"><span data-stu-id="6ae8b-141">Diagnosis :</span></span>

<span data-ttu-id="6ae8b-142">Предыдущие выходные данные почтовых состояний не пройдены, так как целевой пользователь не найден.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-142">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="6ae8b-143">Вы можете определить, был ли действительный SIP-адрес передан в Test-CsAddressBookWebQuery, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-143">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="6ae8b-144">Если Test-CsAddressBookWebQuery завершается с ошибкой, вам может потребоваться повторно выполнить проверку, включая параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-144">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="6ae8b-145">Если включен параметр Verbose, Test-CsAddressBookWebQuery будет возвращать пошаговое действие для каждого действия, которое он пытался выполнить, при проверке возможности входа на сервер Lync для указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-145">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="6ae8b-146">Например, эти выходные данные указывают на то, что Test-CsAddressBookWebQuery удалось подключиться к службе адресной книги, но ему не удалось определить целевой SIP-адрес:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-146">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="6ae8b-147">Начато действие "Куеряддрессбуквебсервице".</span><span class="sxs-lookup"><span data-stu-id="6ae8b-147">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="6ae8b-148">Служба веб-запросов к адресной книге вызовов.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-148">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="6ae8b-149">URL-АДРЕС АБВС =</span><span class="sxs-lookup"><span data-stu-id="6ae8b-149">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="6ae8b-150">Исключение запроса адресной книги: сбой запроса веб-службы адресной книги с кодом отклика Ноентрифаунд.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-150">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6ae8b-151">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="6ae8b-151">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="6ae8b-152">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-152">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="6ae8b-153">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-153">You specified an invalid user account.</span></span> <span data-ttu-id="6ae8b-154">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="6ae8b-155">Учетная запись пользователя действительна, но в настоящее время эта учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-155">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="6ae8b-156">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-156">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="6ae8b-157">Если для свойства Enabled задано значение false, то в данный момент пользователь не включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-157">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="6ae8b-158">Целевой пользователь может отсутствовать в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-158">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="6ae8b-159">Возможно, адресная книга не полностью обновлена и не была реплицирована.</span><span class="sxs-lookup"><span data-stu-id="6ae8b-159">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="6ae8b-160">Вы можете принудительно обновить все серверы адресной книги в Организации, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ae8b-160">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

