---
title: 'Lync Server 2013: Проверка серверных сертификатов Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="3fb84-102">Проверка серверных сертификатов Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fb84-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fb84-103">_**Тема последнего изменения:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="3fb84-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3fb84-104">Расписание проверки</span><span class="sxs-lookup"><span data-stu-id="3fb84-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3fb84-105">Ежемесячно</span><span class="sxs-lookup"><span data-stu-id="3fb84-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3fb84-106">Средство тестирования</span><span class="sxs-lookup"><span data-stu-id="3fb84-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3fb84-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3fb84-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3fb84-108">Требуемые разрешения</span><span class="sxs-lookup"><span data-stu-id="3fb84-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3fb84-109">При локальном запуске с помощью командной консоли Lync Server пользователи должны быть членами группы безопасности Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="3fb84-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3fb84-110">При запуске с помощью удаленного экземпляра Windows PowerShell пользователям должна быть назначена роль RBAC, имеющая разрешение на запуск командлета Get-Ксцертификате.</span><span class="sxs-lookup"><span data-stu-id="3fb84-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="3fb84-111">Чтобы просмотреть список всех ролей RBAC, которые могут использовать этот командлет, выполните в командной строке Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3fb84-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3fb84-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3fb84-112">Description</span></span>

<span data-ttu-id="3fb84-113">Командлет Get-Ксцертификате позволяет получить сведения о каждом из сертификатов сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3fb84-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="3fb84-114">Это особенно важно, так как у сертификатов есть встроенная Дата окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="3fb84-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="3fb84-115">Например, просроченные сертификаты, как правило, истекает через 12 месяцев.</span><span class="sxs-lookup"><span data-stu-id="3fb84-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="3fb84-116">Если срок действия одного из сертификатов вашего сервера Lync Server истек, то все возможности будут потеряны до тех пор, пока сертификат не будет обновлен или заменен.</span><span class="sxs-lookup"><span data-stu-id="3fb84-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3fb84-117">Выполнение теста</span><span class="sxs-lookup"><span data-stu-id="3fb84-117">Running the test</span></span>

<span data-ttu-id="3fb84-118">Чтобы получить сведения о каждом из ваших сертификатов сервера Lync Server, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3fb84-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="3fb84-119">Вы также можете отфильтровать сведения о сертификате возврата на основе даты окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="3fb84-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="3fb84-120">Например, эта команда ограничивает возвращаемые данные сертификатами с истекшим сроком действия (не может использоваться после) июня 1, 2014:</span><span class="sxs-lookup"><span data-stu-id="3fb84-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="3fb84-121">Дополнительные сведения можно найти в справочной документации по командлету Get-Ксцертификате.</span><span class="sxs-lookup"><span data-stu-id="3fb84-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="3fb84-122">Обратите внимание, что несмотря на то, что командлет Test-Ксцертификатеконфигуратион существует, он не очень полезен администраторам.</span><span class="sxs-lookup"><span data-stu-id="3fb84-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="3fb84-123">(Вместо этого этот командлет используется преимущественно мастером сертификатов.) Несмотря на то что командлет работает, возвращаемые им данные имеют минимальное значение, как показано в следующем примере вывода:</span><span class="sxs-lookup"><span data-stu-id="3fb84-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="3fb84-124">Использование отпечатка</span><span class="sxs-lookup"><span data-stu-id="3fb84-124">Thumbprint Use</span></span>

<span data-ttu-id="3fb84-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="3fb84-125"></span></span>

<span data-ttu-id="3fb84-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 по умолчанию</span><span class="sxs-lookup"><span data-stu-id="3fb84-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="3fb84-127">Просмотр результатов</span><span class="sxs-lookup"><span data-stu-id="3fb84-127">Reviewing the output</span></span>

<span data-ttu-id="3fb84-128">Командлет Get-Ксцертификате возвращает сведения о каждом из сертификатов сервера Lync Server, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="3fb84-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="3fb84-129">Issuer: CN = Фабрикамка</span><span class="sxs-lookup"><span data-stu-id="3fb84-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="3fb84-130">Нотафтер: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="3fb84-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="3fb84-131">Нотбефоре: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="3fb84-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="3fb84-132">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="3fb84-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="3fb84-133">Тема: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb84-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="3fb84-134">Алтернативенамес: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="3fb84-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="3fb84-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="3fb84-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="3fb84-136">Отпечаток: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="3fb84-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="3fb84-137">Использование: Default</span><span class="sxs-lookup"><span data-stu-id="3fb84-137">Use : Default</span></span>

<span data-ttu-id="3fb84-138">Как правило, основные проблемы, связанные с сертификатами Lync Server, включают в себя даты и время, например время вступления в силу сертификатов (Нотбефоре) или срок их действия (Нотафтер).</span><span class="sxs-lookup"><span data-stu-id="3fb84-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="3fb84-139">Поскольку эти значения даты и времени настолько важны, возможно, потребуется ограничить возвращаемые данные такими данными, как использование сертификата, серийный номер сертификата и Дата окончания срока действия сертификата; После этого вы сможете быстро просмотреть все сертификаты и срок их действия.</span><span class="sxs-lookup"><span data-stu-id="3fb84-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="3fb84-140">Чтобы вернуть эти данные, используйте команду вместе с параметрами, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="3fb84-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="3fb84-141">Эта команда возвращает данные, похожие на приведенные ниже, при этом сертификаты сортируются в порядке их истечения срока действия.</span><span class="sxs-lookup"><span data-stu-id="3fb84-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="3fb84-142">Использование Нотафтер SerialNumber</span><span class="sxs-lookup"><span data-stu-id="3fb84-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="3fb84-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="3fb84-143"></span></span>

<span data-ttu-id="3fb84-144">611BB01200000000000C по умолчанию 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="3fb84-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="3fb84-145">Вебсервицесинтерал 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="3fb84-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="3fb84-146">Вебсервицесекстернал 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="3fb84-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="3fb84-147">Если у вас возникли проблемы с сертификатом, возможно, вы захотите просмотреть Алтернативенамес, настроенный для сертификата.</span><span class="sxs-lookup"><span data-stu-id="3fb84-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="3fb84-148">На первый взгляд, это похоже на проблему.</span><span class="sxs-lookup"><span data-stu-id="3fb84-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="3fb84-149">По умолчанию, в зависимости от размера окна консоли, Get-Ксцертификате может не отображать все имена:</span><span class="sxs-lookup"><span data-stu-id="3fb84-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="3fb84-150">Алтернативенамес: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="3fb84-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="3fb84-151">meet.fabrikam.com, admin. фабрика...}</span><span class="sxs-lookup"><span data-stu-id="3fb84-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="3fb84-152">Чтобы просмотреть все альтернативные имена, назначенные сертификату, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3fb84-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="3fb84-153">Для отображения всех альтернативных имен в сертификате:</span><span class="sxs-lookup"><span data-stu-id="3fb84-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="3fb84-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb84-154">sip.fabrikam.com</span></span>

<span data-ttu-id="3fb84-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb84-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="3fb84-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb84-156">meet.fabrikam.com</span></span>

<span data-ttu-id="3fb84-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb84-157">admin.fabrikam.com</span></span>

<span data-ttu-id="3fb84-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb84-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="3fb84-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="3fb84-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3fb84-160">См. также</span><span class="sxs-lookup"><span data-stu-id="3fb84-160">See Also</span></span>


[<span data-ttu-id="3fb84-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="3fb84-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

