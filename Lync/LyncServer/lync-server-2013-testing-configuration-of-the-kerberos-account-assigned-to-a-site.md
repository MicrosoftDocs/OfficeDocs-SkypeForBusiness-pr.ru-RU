---
title: Тестирование конфигурации учетной записи Kerberos, назначенной сайту
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d916ba2123f6a34150a9fe5c9c3977d75743dae0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="1f395-102">Тестирование конфигурации учетной записи Kerberos, назначенной сайту, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f395-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f395-103">_**Последнее изменение темы:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1f395-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f395-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="1f395-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1f395-105">Daily (Ежедневный)</span><span class="sxs-lookup"><span data-stu-id="1f395-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f395-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="1f395-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1f395-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f395-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f395-108">Необходимые разрешения</span><span class="sxs-lookup"><span data-stu-id="1f395-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1f395-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1f395-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1f395-110">При выполнении с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="1f395-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="1f395-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните следующую команду в командной консоли Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1f395-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1f395-112">Описание</span><span class="sxs-lookup"><span data-stu-id="1f395-112">Description</span></span>

<span data-ttu-id="1f395-113">Командлет Test-CsKerberosAccountAssignment позволяет убедиться, что учетная запись Kerberos связана с определенным сайтом, что эта учетная запись настроена правильно, а учетная запись работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="1f395-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="1f395-114">Учетные записи Kerberos — это учетные записи компьютеров, которые могут выступать в качестве субъекта проверки подлинности для всех компьютеров сайта, на котором работает сервер IIS.</span><span class="sxs-lookup"><span data-stu-id="1f395-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="1f395-115">Так как эти учетные записи используют протокол проверки подлинности Kerberos, учетные записи называются учетными записями Kerberos, а новый процесс проверки подлинности называется проверкой подлинности Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1f395-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="1f395-116">Это позволяет управлять всеми серверами IIS с помощью одной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="1f395-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="1f395-117">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="1f395-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1f395-118">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="1f395-118">Running the Test</span></span>

<span data-ttu-id="1f395-119">По умолчанию test-CsKerberosAccountAssignment отображает очень маленький вывод на экран.</span><span class="sxs-lookup"><span data-stu-id="1f395-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="1f395-120">Вместо этого сведения, возвращаемые командлетом, записываются в HTML-файл.</span><span class="sxs-lookup"><span data-stu-id="1f395-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="1f395-121">Из-за этого мы рекомендуем включить параметр Verbose и параметр отчета каждый раз при запуске test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="1f395-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="1f395-122">Параметр verbose предоставит немного более подробный вывод на экран при выполнении командлета.</span><span class="sxs-lookup"><span data-stu-id="1f395-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="1f395-123">Параметр Report позволяет указать путь к файлу и имя файла для HTML-файла, созданного с помощью Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="1f395-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="1f395-124">Если не включить параметр отчета, HTML-файл будет автоматически сохранен в папке "Пользователи" и будет иметь имя, аналогичное следующему: ce84964a-c4da-4622-ad34-c54ff3ed361f. HTML.</span><span class="sxs-lookup"><span data-stu-id="1f395-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="1f395-125">Кроме того, при выполнении командлета Test-CsKerberosAccountAssignment необходимо указать удостоверение сайта.</span><span class="sxs-lookup"><span data-stu-id="1f395-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="1f395-126">Учетные записи Kerberos назначаются в области сайта.</span><span class="sxs-lookup"><span data-stu-id="1f395-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="1f395-127">Приведенная ниже команда выполняет команду Test-CsKerberosAccountAssignment и сохраняет выходные данные в файл с именем C:\\Logs\\KerberosTest. HTML:</span><span class="sxs-lookup"><span data-stu-id="1f395-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="1f395-128">Дополнительные сведения можно найти в справочной документации по командлету [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="1f395-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1f395-129">Определение успешности или сбоя</span><span class="sxs-lookup"><span data-stu-id="1f395-129">Determining Success or Failure</span></span>

<span data-ttu-id="1f395-130">Командлет Test-CsKerberosAccountAssignment не возвращает простой индикатор успешного или неудачи.</span><span class="sxs-lookup"><span data-stu-id="1f395-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="1f395-131">Вместо этого необходимо просмотреть созданный HTML-файл с помощью Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="1f395-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1f395-132">Причины, по которым может произойти сбой теста</span><span class="sxs-lookup"><span data-stu-id="1f395-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="1f395-133">Ниже приведены некоторые распространенные причины, по которым может произойти ошибка Test-CsKerberosAccountAssignment:</span><span class="sxs-lookup"><span data-stu-id="1f395-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="1f395-134">Возможно, вы указали неправильное удостоверение сайта.</span><span class="sxs-lookup"><span data-stu-id="1f395-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="1f395-135">Чтобы получить список допустимых идентификаторов сайтов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1f395-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="1f395-136">Как правило, идентификатор сайта выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="1f395-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="1f395-137">site: Redmond</span><span class="sxs-lookup"><span data-stu-id="1f395-137">site:Redmond</span></span>

  - <span data-ttu-id="1f395-138">Для указанного сайта может быть не назначена учетная запись Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1f395-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="1f395-139">Вы можете определить, назначена ли учетная запись Kerberos сайту, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1f395-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="1f395-140">Учетная запись Kerberos может иметь Недействительный пароль.</span><span class="sxs-lookup"><span data-stu-id="1f395-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="1f395-141">Если в отчете отображается следующее сообщение об ошибке, вероятно, вам потребуется сбросить пароль учетной записи Kerberos:</span><span class="sxs-lookup"><span data-stu-id="1f395-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="1f395-142">Инвалидкерберосконфигуратион: Недопустимая конфигурация Kerberos.</span><span class="sxs-lookup"><span data-stu-id="1f395-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="1f395-143">Инвалидкерберосконфигуратион: Конфигурация Kerberos в atl-cs001.litwareinc.com является недопустимой.</span><span class="sxs-lookup"><span data-stu-id="1f395-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="1f395-144">Предполагаемая назначенная учетная\\запись — litwareinc kerberostest.</span><span class="sxs-lookup"><span data-stu-id="1f395-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="1f395-145">Убедитесь, что срок действия учетной записи не истек, а пароль, настроенный на компьютере, соответствует паролю учетной записи Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1f395-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="1f395-146">Вы можете задать пароль с помощью командлета [Set – кскерберосаккаунтпассворд](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="1f395-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

