---
title: 'Lync Server 2013: Проверка веб-запроса адресной книги'
description: 'Lync Server 2013: Проверка веб-запроса адресной книги.'
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
ms.openlocfilehash: e73c39fc33f8d1851fc89d277333a94aaa137790
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547255"
---
# <a name="validating-address-book-web-query-in-lync-server-2013"></a><span data-ttu-id="6e12b-103">Проверка веб-запроса адресной книги в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e12b-103">Validating address book web query in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e12b-104">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6e12b-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e12b-105">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="6e12b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6e12b-106">Ежедневное</span><span class="sxs-lookup"><span data-stu-id="6e12b-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e12b-107">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="6e12b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6e12b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e12b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e12b-109">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="6e12b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6e12b-110">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6e12b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6e12b-111">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsAddressBookWebQuery.</span><span class="sxs-lookup"><span data-stu-id="6e12b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookWebQuery cmdlet.</span></span> <span data-ttu-id="6e12b-112">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6e12b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6e12b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6e12b-113">Description</span></span>

<span data-ttu-id="6e12b-114">Командлет Test-CsAddressBookWebQuery позволяет администраторам проверить, могут ли пользователи использовать службу веб-запросов адресной книги для поиска определенного контакта.</span><span class="sxs-lookup"><span data-stu-id="6e12b-114">The Test-CsAddressBookWebQuery cmdlet enables administrators to verify that users can use the Address Book Web Query service to search for a specific contact.</span></span> <span data-ttu-id="6e12b-115">При запуске командлета Test-CsAddressBookWebQuery будет сначала подключаться к службе веб-билетов, чтобы пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="6e12b-115">When you run the cmdlet, Test-CsAddressBookWebQuery will first connect to the Web Ticket service to be authenticated.</span></span> <span data-ttu-id="6e12b-116">Если проверка подлинности прошла успешно, командлет будет подключаться к службе веб-запросов адресной книги и искать указанного контакта.</span><span class="sxs-lookup"><span data-stu-id="6e12b-116">If authentication is successful, the cmdlet will then connect to the Address Book Web Query service and search for the specified contact.</span></span> <span data-ttu-id="6e12b-117">При нахождении контакта командлет попытается вернуть данные на локальный компьютер.</span><span class="sxs-lookup"><span data-stu-id="6e12b-117">If that contact is found, the cmdlet will attempt to return that information to the local computer.</span></span> <span data-ttu-id="6e12b-118">Тест будет помечен как успешный, только если все эти действия можно выполнить.</span><span class="sxs-lookup"><span data-stu-id="6e12b-118">The test will be marked a success only if all those steps can be completed.</span></span>

<span data-ttu-id="6e12b-119">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="6e12b-119">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6e12b-120">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="6e12b-120">Running the test</span></span>

<span data-ttu-id="6e12b-121">Командлет Test-CsAddressBookWebQuery можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, для которого включен Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e12b-121">The Test-CsAddressBookWebQuery cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="6e12b-122">Чтобы выполнить эту проверку с помощью тестовой учетной записи, необходимо указать полное доменное имя пула Lync Server и SIP-адрес пользователя, выступающего в качестве целевого объекта поиска.</span><span class="sxs-lookup"><span data-stu-id="6e12b-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool and the SIP address of the user acting as the target of the search.</span></span> <span data-ttu-id="6e12b-123">Например:</span><span class="sxs-lookup"><span data-stu-id="6e12b-123">For example:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="6e12b-124">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо создать объект учетных данных Windows PowerShell, который содержит действительное имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="6e12b-124">To run this check using an actual user account, you must create a Windows PowerShell credentials object that contains a valid user name and password.</span></span> <span data-ttu-id="6e12b-125">Затем необходимо включить этот объект учетных данных и адрес SIP, назначенный учетной записи, когда код вызывает Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="6e12b-125">You must then include that credentials object and the SIP address assigned to the account when the code calls Test-CsAddressBookWebQuery:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6e12b-126">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) .</span><span class="sxs-lookup"><span data-stu-id="6e12b-126">For more information, see the Help documentation for the [Test-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6e12b-127">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="6e12b-127">Determining success or failure</span></span>

<span data-ttu-id="6e12b-128">Если указанный пользователь может подключаться к службе адресной книги и получать целевой адрес пользователя, будет выведен результат, подобный следующему, с свойством Result, помеченным как успешно:</span><span class="sxs-lookup"><span data-stu-id="6e12b-128">If the specified user can connect to the Address Book Service and retrieve the targeted user address, you'll return output similar to this with the Result property marked as Success:</span></span>

<span data-ttu-id="6e12b-129">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6e12b-129">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="6e12b-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6e12b-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6e12b-131">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="6e12b-131">Result : Success</span></span>

<span data-ttu-id="6e12b-132">Задержка: 00:00:06.2611356</span><span class="sxs-lookup"><span data-stu-id="6e12b-132">Latency : 00:00:06.2611356</span></span>

<span data-ttu-id="6e12b-133">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="6e12b-133">Error :</span></span>

<span data-ttu-id="6e12b-134">Диагност</span><span class="sxs-lookup"><span data-stu-id="6e12b-134">Diagnosis :</span></span>

<span data-ttu-id="6e12b-135">Если указанный пользователь не может подключиться или не удается получить целевой адрес пользователя, результат будет отображаться как сбой, а в свойствах диагностики ошибок и диагностики будут записаны дополнительные сведения:</span><span class="sxs-lookup"><span data-stu-id="6e12b-135">If the specified user can't connect or if the target user address cannot be retrieved, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6e12b-136">TargetUri https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="6e12b-136">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="6e12b-137">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6e12b-137">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6e12b-138">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="6e12b-138">Result : Failure</span></span>

<span data-ttu-id="6e12b-139">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="6e12b-139">Latency : 00:00:00</span></span>

<span data-ttu-id="6e12b-140">Ошибка: сбой запроса веб-службы адресной книги с кодом отклика</span><span class="sxs-lookup"><span data-stu-id="6e12b-140">Error : Address Book Web service request has failed with response code</span></span>

<span data-ttu-id="6e12b-141">Ноентрифаунд.</span><span class="sxs-lookup"><span data-stu-id="6e12b-141">NoEntryFound.</span></span>

<span data-ttu-id="6e12b-142">Диагност</span><span class="sxs-lookup"><span data-stu-id="6e12b-142">Diagnosis :</span></span>

<span data-ttu-id="6e12b-143">Предыдущие выходные данные почтовых состояний не пройдены, так как целевой пользователь не найден.</span><span class="sxs-lookup"><span data-stu-id="6e12b-143">The previous output states that the test failed because the target user couldn't be found.</span></span> <span data-ttu-id="6e12b-144">Можно определить, был ли действительный SIP адрес передан Test-CsAddressBookWebQuery, выполнив команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="6e12b-144">You can determine whether or not a valid SIP address was passed to Test-CsAddressBookWebQuery by running a command similar to the following:</span></span>

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

<span data-ttu-id="6e12b-145">Если Test-CsAddressBookWebQuery завершается с ошибкой, может потребоваться повторный запуск теста, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="6e12b-145">If Test-CsAddressBookWebQuery fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

<span data-ttu-id="6e12b-146">Если включен параметр Verbose, Test-CsAddressBookWebQuery будет возвращать пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e12b-146">When the Verbose parameter is included, Test-CsAddressBookWebQuery will return a step-by-step account of each action it tried while checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="6e12b-147">Например, эти выходные данные указывают на то, что Test-CsAddressBookWebQuery удалось подключиться к службе адресной книги, но ей не удалось определить конечный SIP адрес:</span><span class="sxs-lookup"><span data-stu-id="6e12b-147">For example, this output indicates that Test-CsAddressBookWebQuery was able to connect to the Address Book Service, but was not able to locate the target SIP address:</span></span>

<span data-ttu-id="6e12b-148">Начато действие "Куеряддрессбуквебсервице".</span><span class="sxs-lookup"><span data-stu-id="6e12b-148">'QueryAddressBookWebService' activity started.</span></span>

<span data-ttu-id="6e12b-149">Служба веб-запросов к адресной книге вызовов.</span><span class="sxs-lookup"><span data-stu-id="6e12b-149">Calling Address Book Web Query Service.</span></span> <span data-ttu-id="6e12b-150">URL-АДРЕС АБВС =</span><span class="sxs-lookup"><span data-stu-id="6e12b-150">ABWS URL =</span></span>

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

<span data-ttu-id="6e12b-151">Исключение запроса адресной книги: сбой запроса веб-службы адресной книги с кодом отклика Ноентрифаунд.</span><span class="sxs-lookup"><span data-stu-id="6e12b-151">Address book query exception : Address Book Web service request has failed with response code NoEntryFound.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6e12b-152">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="6e12b-152">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="6e12b-153">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsAddressBookWebQuery:</span><span class="sxs-lookup"><span data-stu-id="6e12b-153">Here are some common reasons why Test-CsAddressBookWebQuery might fail:</span></span>

  - <span data-ttu-id="6e12b-154">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="6e12b-154">You specified an invalid user account.</span></span> <span data-ttu-id="6e12b-155">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6e12b-155">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="6e12b-156">Учетная запись пользователя действительна, но в настоящее время эта учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e12b-156">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="6e12b-157">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="6e12b-157">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="6e12b-158">Если для свойства Enabled задано значение false, то в данный момент пользователь не включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6e12b-158">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

  - <span data-ttu-id="6e12b-159">Целевой пользователь может отсутствовать в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="6e12b-159">The target user might not be in the Address Book.</span></span>

  - <span data-ttu-id="6e12b-160">Возможно, адресная книга не полностью обновлена и не была реплицирована.</span><span class="sxs-lookup"><span data-stu-id="6e12b-160">The Address Book might not have fully updated and replicated.</span></span> <span data-ttu-id="6e12b-161">Вы можете принудительно обновить все серверы адресной книги в Организации, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6e12b-161">You can force an update of all the Address Book Servers in your organization by running the following command:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

