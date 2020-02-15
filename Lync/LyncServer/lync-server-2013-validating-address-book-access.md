---
title: 'Lync Server 2013: Проверка доступа к адресной книге'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f18651cd75df62cf1d5f8c543d0e5c11361c7db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a><span data-ttu-id="f8951-102">Проверка доступа к адресной книге в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8951-102">Validating address book access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8951-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="f8951-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8951-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="f8951-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f8951-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="f8951-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8951-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="f8951-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f8951-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8951-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8951-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="f8951-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f8951-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f8951-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f8951-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsAddressBookService.</span><span class="sxs-lookup"><span data-stu-id="f8951-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsAddressBookService cmdlet.</span></span> <span data-ttu-id="f8951-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="f8951-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f8951-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f8951-112">Description</span></span>

<span data-ttu-id="f8951-113">Командлет Test-CsAddressBookService предоставляет способ проверки возможности подключения пользователя к веб-службе загрузки адресной книги.</span><span class="sxs-lookup"><span data-stu-id="f8951-113">The Test-CsAddressBookService cmdlet provides a way for you to verify that a user can connect to the Address Book Download Web service.</span></span> <span data-ttu-id="f8951-114">При выполнении командлета Test-CsAddressBookService подключается к веб-службе загрузки адресной книги в указанном пуле и запрашивает расположение файлов адресной книги.</span><span class="sxs-lookup"><span data-stu-id="f8951-114">When you run the cmdlet, Test-CsAddressBookService connects to the Address Book Download Web service on the specified pool and requests the location of the Address Book files.</span></span> <span data-ttu-id="f8951-115">Если веб-служба загрузки адресной книги предоставляет это расположение, проверка считается успешной.</span><span class="sxs-lookup"><span data-stu-id="f8951-115">If the Address Book Download Web service supplies that location, the test is considered successful.</span></span> <span data-ttu-id="f8951-116">Если такой запрос отклоняется, то тест считается непройденным.</span><span class="sxs-lookup"><span data-stu-id="f8951-116">If the request is denied, then the test is considered a failure.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f8951-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="f8951-117">Running the test</span></span>

<span data-ttu-id="f8951-118">Командлет Test-CsAddressBookService можно выполнить с помощью предварительно настроенной тестовой учетной записи (см. Настройка тестовых учетных записей для выполнения тестов Lync Server) или учетной записи любого пользователя, который был включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8951-118">The Test-CsAddressBookService cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who has been enabled for Lync Server.</span></span> <span data-ttu-id="f8951-119">Для выполнения этой проверки с помощью тестовой учетной записи все, что необходимо сделать, — указать полное доменное имя (FQDN) тестируемого пула Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8951-119">To run this check using a test account, all you need to do is specify the fully qualified domain name (FQDN) of the Lync Server pool being tested.</span></span> <span data-ttu-id="f8951-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="f8951-120">For example:</span></span>

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="f8951-121">Чтобы выполнить эту проверку с использованием реальной учетной записи пользователя, необходимо сначала создать объект учетных данных Windows PowerShell, который содержит имя и пароль учетной записи.</span><span class="sxs-lookup"><span data-stu-id="f8951-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="f8951-122">Затем необходимо добавить этот объект учетных данных и адрес SIP, назначенный учетной записи при вызове Test-CsAddressBookService:</span><span class="sxs-lookup"><span data-stu-id="f8951-122">You must then include that credentials object and the SIP address assigned to the account when calling Test-CsAddressBookService:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f8951-123">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) .</span><span class="sxs-lookup"><span data-stu-id="f8951-123">For more information, see the Help documentation for the [Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f8951-124">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="f8951-124">Determining success or failure</span></span>

<span data-ttu-id="f8951-125">Если указанный пользователь может подключаться к службе адресной книги, будет выведен результат, подобный следующему, при этом свойство Result помечается как **успешное**:</span><span class="sxs-lookup"><span data-stu-id="f8951-125">If the specified user is able to connect to the Address Book Service you will get back output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="f8951-126">TargetUrihttps://lync-se.fabrikam.com:443/abs/handler</span><span class="sxs-lookup"><span data-stu-id="f8951-126">TargetUri : https://lync-se.fabrikam.com:443/abs/handler</span></span>

<span data-ttu-id="f8951-127">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f8951-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f8951-128">Результат: успешное выполнение</span><span class="sxs-lookup"><span data-stu-id="f8951-128">Result : Success</span></span>

<span data-ttu-id="f8951-129">Задержка: 00:00:06.2260399</span><span class="sxs-lookup"><span data-stu-id="f8951-129">Latency : 00:00:06.2260399</span></span>

<span data-ttu-id="f8951-130">Ошибкой</span><span class="sxs-lookup"><span data-stu-id="f8951-130">Error :</span></span>

<span data-ttu-id="f8951-131">Диагност</span><span class="sxs-lookup"><span data-stu-id="f8951-131">Diagnosis :</span></span>

<span data-ttu-id="f8951-132">Если указанный пользователь не может сделать это подключение, результат будет отображаться как сбой, а дополнительные сведения будут записаны в свойствах Error и диагноз:</span><span class="sxs-lookup"><span data-stu-id="f8951-132">If the specified user is not able to make this connection, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="f8951-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="f8951-133">TargetUri :</span></span>

<span data-ttu-id="f8951-134">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f8951-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f8951-135">Результат: сбой</span><span class="sxs-lookup"><span data-stu-id="f8951-135">Result : Failure</span></span>

<span data-ttu-id="f8951-136">Задержка: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="f8951-136">Latency : 00:00:00</span></span>

<span data-ttu-id="f8951-137">Диагностика: ErrorCode = 4005, Source = ATL – CS – 001.litwareinc.com,</span><span class="sxs-lookup"><span data-stu-id="f8951-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="f8951-138">Reason = конечный URI либо не включен для SIP, либо не</span><span class="sxs-lookup"><span data-stu-id="f8951-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="f8951-139">есть.</span><span class="sxs-lookup"><span data-stu-id="f8951-139">exist.</span></span>

<span data-ttu-id="f8951-140">Microsoft. RTC. Signal. Диагностичеадер</span><span class="sxs-lookup"><span data-stu-id="f8951-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="f8951-141">Например, предыдущие выходные состояния не удалось выполнить тест, так как указанный пользователь (то есть "конечный URI") не существует или не включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8951-141">For example, the preceding output states that the test failed because the specified user (that is, the “Destination URI”) either does not exist or has not been enabled for Lync Server.</span></span> <span data-ttu-id="f8951-142">Вы можете проверить, является ли учетная запись пользователя допустимой, и убедиться, что указан правильный SIP-адрес, выполнив команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="f8951-142">You can verify whether or not a user account is valid, and verify that you supplied the correct SIP address, by running a command like this one:</span></span>

<span data-ttu-id="f8951-143">Get – CsUser — Identity "sip:kenmyer@litwareinc.com" | Select — объект SipAddress, включен</span><span class="sxs-lookup"><span data-stu-id="f8951-143">Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled</span></span>

<span data-ttu-id="f8951-144">Если не удается выполнить команду Test-CsAddressBookService, вам может потребоваться повторить проверку, в том числе параметр verbose:</span><span class="sxs-lookup"><span data-stu-id="f8951-144">If Test-CsAddressBookService fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="f8951-145">Test-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-verbose</span><span class="sxs-lookup"><span data-stu-id="f8951-145">Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="f8951-146">Если параметр verbose включен, командлет Test-CsAddressBookService возвращает пошаговые учетные записи каждого выполняемого действия при проверке возможности указанного пользователя выполнить вход на сервер Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8951-146">When the Verbose parameter is included Test-CsAddressBookService will return a step-by-step account of each action it attempted when checking the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="f8951-147">Например, в приведенном ниже примере показана проверка того, что в этом примере кода CsAddressBookService, по крайней мере, в этом примере была возможность скачать файл адресной книги:</span><span class="sxs-lookup"><span data-stu-id="f8951-147">For example, this sample output shows that Test-CsAddressBookService, at least in this example, was able to download the Address Book file:</span></span>

<span data-ttu-id="f8951-148">Отправка HTTP-запроса GET.</span><span class="sxs-lookup"><span data-stu-id="f8951-148">Sending Http GET Request.</span></span>

<span data-ttu-id="f8951-149">Путь к файлу =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="f8951-149">File Path = https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

<span data-ttu-id="f8951-150">Номер попытки = 1</span><span class="sxs-lookup"><span data-stu-id="f8951-150">Attempt Number = 1</span></span>

<span data-ttu-id="f8951-151">Время ожидания (МС) = 60000</span><span class="sxs-lookup"><span data-stu-id="f8951-151">TimeOut (msec) = 60000</span></span>

<span data-ttu-id="f8951-152">Файл ABS успешно скачанhttps://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span><span class="sxs-lookup"><span data-stu-id="f8951-152">Successfully Downloaded the ABS file https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f8951-153">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="f8951-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="f8951-154">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsAddressBookService:</span><span class="sxs-lookup"><span data-stu-id="f8951-154">Here are some common reasons why Test-CsAddressBookService might fail:</span></span>

  - <span data-ttu-id="f8951-155">Вы указали недопустимую учетную запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="f8951-155">You specified an invalid user account.</span></span> <span data-ttu-id="f8951-156">Чтобы убедиться, что учетная запись пользователя существует, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f8951-156">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="f8951-157">Учетная запись пользователя действительна, но в настоящее время эта учетная запись не включена для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8951-157">The user account is valid, but the account is not currently enabled for Lync Server.</span></span> <span data-ttu-id="f8951-158">Чтобы убедиться в том, что учетная запись пользователя включена для Lync Server, выполните команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="f8951-158">To verify that a user account has been enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="f8951-159">Если для свойства Enabled задано значение false, то в данный момент пользователь не включен для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f8951-159">If the Enabled property is set to False that means that the user is not currently enabled for Lync Server.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f8951-160">См. также</span><span class="sxs-lookup"><span data-stu-id="f8951-160">See Also</span></span>


[<span data-ttu-id="f8951-161">Test-CsAddressBookService</span><span class="sxs-lookup"><span data-stu-id="f8951-161">Test-CsAddressBookService</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

