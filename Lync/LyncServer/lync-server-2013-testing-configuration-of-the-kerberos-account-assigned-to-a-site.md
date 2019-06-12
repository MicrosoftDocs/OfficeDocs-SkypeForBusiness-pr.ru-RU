---
title: Проверка конфигурации учетной записи Kerberos, назначенной сайту
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e12a780c4c900423b23eff6cdaae15ba15786b6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849403"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="28049-102">Проверка конфигурации учетной записи Kerberos, назначенной сайту, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28049-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28049-103">_**Тема последнего изменения:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="28049-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28049-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="28049-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="28049-105">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="28049-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28049-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="28049-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="28049-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="28049-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28049-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="28049-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="28049-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="28049-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="28049-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-Кскерберосаккаунтассигнмент.</span><span class="sxs-lookup"><span data-stu-id="28049-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="28049-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28049-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="28049-112">Описание</span><span class="sxs-lookup"><span data-stu-id="28049-112">Description</span></span>

<span data-ttu-id="28049-113">Командлет Test-Кскерберосаккаунтассигнмент позволяет удостовериться, что учетная запись Kerberos связана с данным сайтом, что эта учетная запись настроена правильно, а учетная запись работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="28049-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="28049-114">Учетные записи Kerberos — это учетные записи компьютеров, которые могут служить субъектом проверки подлинности для всех компьютеров на сайте, на котором запущен сервер IIS.</span><span class="sxs-lookup"><span data-stu-id="28049-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="28049-115">Поскольку эти учетные записи используют протокол проверки подлинности Kerberos, учетные записи известны как учетные записи Kerberos, а новый процесс проверки подлинности известен как веб-проверка подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="28049-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="28049-116">Это позволяет управлять всеми серверами IIS с помощью одной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="28049-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="28049-117">Дополнительные сведения можно найти в справочной документации по командлету [Test-кскерберосаккаунтассигнмент](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="28049-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="28049-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="28049-118">Running the Test</span></span>

<span data-ttu-id="28049-119">По умолчанию в режиме Test-Кскерберосаккаунтассигнмент отображается очень мало вывода на экран.</span><span class="sxs-lookup"><span data-stu-id="28049-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="28049-120">Вместо этого данные, возвращаемые командлетом, записываются в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="28049-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="28049-121">По этой причине мы рекомендуем включать параметр подробных данных и параметр отчета каждый раз при запуске test-Кскерберосаккаунтассигнмент.</span><span class="sxs-lookup"><span data-stu-id="28049-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="28049-122">Параметр verbose обеспечивает немного более подробный вывод на экран во время выполнения командлета.</span><span class="sxs-lookup"><span data-stu-id="28049-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="28049-123">Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-Кскерберосаккаунтассигнмент.</span><span class="sxs-lookup"><span data-stu-id="28049-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="28049-124">Если параметр отчета не указан, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь такое имя, как: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.</span><span class="sxs-lookup"><span data-stu-id="28049-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="28049-125">Кроме того, необходимо указать удостоверение сайта при запуске test-Кскерберосаккаунтассигнмент.</span><span class="sxs-lookup"><span data-stu-id="28049-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="28049-126">Учетные записи Kerberos назначаются на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="28049-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="28049-127">Следующая команда запускает команду Test-Кскерберосаккаунтассигнмент и сохраняет выходные данные в файл с именем C:\\Logs\\керберостест. HTML:</span><span class="sxs-lookup"><span data-stu-id="28049-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="28049-128">Дополнительные сведения можно найти в справочной документации по командлету [Test-кскерберосаккаунтассигнмент](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="28049-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="28049-129">Определение успеха или сбоя</span><span class="sxs-lookup"><span data-stu-id="28049-129">Determining Success or Failure</span></span>

<span data-ttu-id="28049-130">Командлет Test-Кскерберосаккаунтассигнмент не возвращает простой индикатор успеха или сбоя.</span><span class="sxs-lookup"><span data-stu-id="28049-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="28049-131">Вместо этого вы должны просмотреть созданный HTML-файл с помощью Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="28049-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="28049-132">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="28049-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="28049-133">Ниже приведены некоторые распространенные причины, по которым может произойти сбой Test-Кскерберосаккаунтассигнмент:</span><span class="sxs-lookup"><span data-stu-id="28049-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="28049-134">Возможно, вы указали неверный идентификатор сайта.</span><span class="sxs-lookup"><span data-stu-id="28049-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="28049-135">Чтобы возвратить список допустимых идентификаторов сайта, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28049-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="28049-136">Идентификатор сайта обычно выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="28049-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="28049-137">сайт: Redmond</span><span class="sxs-lookup"><span data-stu-id="28049-137">site:Redmond</span></span>

  - <span data-ttu-id="28049-138">Возможно, для указанного сайта не назначена учетная запись Kerberos.</span><span class="sxs-lookup"><span data-stu-id="28049-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="28049-139">Вы можете определить, назначена ли учетная запись Kerberos сайту, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28049-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="28049-140">Ваша учетная запись Kerberos может иметь Недействительный пароль.</span><span class="sxs-lookup"><span data-stu-id="28049-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="28049-141">Если в отчете появляется следующее сообщение об ошибке, возможно, потребуется сбросить пароль учетной записи Kerberos.</span><span class="sxs-lookup"><span data-stu-id="28049-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="28049-142">Инвалидкерберосконфигуратион: Недопустимая конфигурация Kerberos.</span><span class="sxs-lookup"><span data-stu-id="28049-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="28049-143">Инвалидкерберосконфигуратион: Недопустимая конфигурация Kerberos на atl-cs001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="28049-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="28049-144">Ожидаемой назначенной учетной\\записи является плана litwareinc керберостест.</span><span class="sxs-lookup"><span data-stu-id="28049-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="28049-145">Убедитесь в том, что срок действия учетной записи не истек, и настроенный пароль для компьютера совпадает с паролем учетной записи Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28049-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="28049-146">Вы можете установить пароль с помощью командлета [Set-кскерберосаккаунтпассворд](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="28049-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

