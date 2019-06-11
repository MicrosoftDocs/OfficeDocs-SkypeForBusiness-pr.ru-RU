---
title: 'Lync Server 2013: проверка и настройка проверки подлинности и сертификатов для виртуальных каталогов IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="e0ceb-102">Проверка и настройка проверки подлинности и сертификатов для виртуальных каталогов IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0ceb-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0ceb-103">_**Тема последнего изменения:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="e0ceb-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e0ceb-104">Для настройки сертификата в виртуальных каталогах служб IIS или проверки правильности настройки сертификата выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="e0ceb-105">Выполните описанные ниже действия на каждом сервере IIS в внутреннем пуле сервера Lync, а также в дополнительном директории или на серверах пула.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e0ceb-106">Ниже описана процедура запроса комбинированного сертификата, который используется для всех целей Lync Server, внутренних веб-сайтов и внешних веб-сайтов в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="e0ceb-107">Lync Server 2010 представил набор командлетов&nbsp;Windows PowerShell для управления запросом сертификата, импорта и назначения.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="e0ceb-108">В этой процедуре предполагается, что имеется внутренний развернутый центр сертификации (ЦС), который может обработать запрос.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="e0ceb-109">Если вы используете общедоступные сертификаты для целей сервера Lync или вам требуется автономный запрос, ознакомьтесь с подробным описанием этой статьи, чтобы получить сведения о параметре – OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="e0ceb-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="e0ceb-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e0ceb-111">Настройка проверки подлинности и сертификатов в виртуальных каталогах IIS</span><span class="sxs-lookup"><span data-stu-id="e0ceb-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e0ceb-112">Для успешного выполнения указанных ниже действий необходимо войти в систему на компьютере (внешнем сервере или в директории), где установлены веб-службы, и являетесь локальным администратором.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="e0ceb-113">Вы должны иметь разрешения на **Чтение** и **регистрацию** в центре сертификации, у которого вы будете получать сертификаты, если центр сертификации является центром сертификации организации.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="e0ceb-114">Если вы настроите и отправляете запрос на автономный сертификат, вы не будете получать разрешения на доступ к центру сертификации.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="e0ceb-115">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Администрирование**, а затем — пункт **Диспетчер информационных служб Интернета (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="e0ceb-116">В **диспетчере информационных служб Интернета (IIS)** выберите **ServerName**.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="e0ceb-117">В **представлении функции**выберите пункт **Сертификаты сервера**, щелкните правой кнопкой мыши и выберите команду **открыть компонент**.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e0ceb-118">В представлении функции серверных сертификатов, если есть сертификаты, назначенные серверу, они будут показаны здесь.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="e0ceb-119">Если сертификат соответствует требованиям к внешнему веб-сайту в IIS, вы можете повторно использовать этот сертификат.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="e0ceb-120">Чтобы просмотреть сертификат, щелкните его правой кнопкой мыши и выберите пункт <STRONG>Просмотреть...</STRONG></span><span class="sxs-lookup"><span data-stu-id="e0ceb-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="e0ceb-121">На сервере переднего плана или режиссере, для которого запрашивается сертификат, нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="e0ceb-122">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e0ceb-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="e0ceb-123">Выходные данные — это список сертификатов, которые в настоящее время находятся на сервере в хранилище персональных сертификатов компьютера.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="e0ceb-124">Обратите внимание, что в Объединенном сертификате (то есть, где по умолчанию внешние веб-службы и веб-службы используют один и тот же сертификат) вы увидите, что свойство Use будет заполнено значением по умолчанию, Вебсервицесинтернал и Вебсервицесекстернал.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="e0ceb-125">Кроме того, Свойство Thumbprint будет одинаковым для каждого типа использования.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="e0ceb-126">Пример выходных данных Get-Ксцертификате показан в этом примере:</span><span class="sxs-lookup"><span data-stu-id="e0ceb-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="e0ceb-127">![Get-ксцертификате info for Current сцерт Status] (images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-ксцертификате info for Current сцерт Status")</span><span class="sxs-lookup"><span data-stu-id="e0ceb-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="e0ceb-128">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e0ceb-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="e0ceb-129">Если команда выглядит так, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e0ceb-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e0ceb-130">По умолчанию при использовании запроса Ксцертификате имя субъекта заполнится именем сервера или пула и заполните элементы в альтернативном имени сервера, FQDN, полное доменное имя пула, простой URL-адрес, а также внутренние и внешние доменные имена веб-служб.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="e0ceb-131">Это осуществляется с помощью ссылки на документ Topology в развертывании.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="e0ceb-132">Если вы задаете значение параметра – verbose, вы будете уведомлены о том, что вычисляемые и фактические значения для альтернативных имен различаются, но не уведомляются о том, какие значения отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="e0ceb-133">Она предоставляет вам полное вычисляемое значение, на которое ссылается командлет.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="e0ceb-134">Для повторного запроса нового сертификата, который будет включать все значения, используйте строку "вычисляемые альтернативные имена" в выходных данных.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="e0ceb-135">![Вывод запроса сертификата с помощью запроса-ксцертифика] (images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Вывод запроса сертификата с помощью запроса-ксцертифика")</span><span class="sxs-lookup"><span data-stu-id="e0ceb-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="e0ceb-136">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e0ceb-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="e0ceb-137">Если команда выглядит так, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e0ceb-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="e0ceb-138">Выходные данные командлета Set-Ксцертификате будут показывать, что один и тот же сертификат (определенный по отпечатку сертификата) назначается для использования по умолчанию, Вебсервицесекстернал и Вебсервицесинтернал.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="e0ceb-139">![Вывод из Set-ксцертификате на IIS вебекст] (images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Вывод из Set-ксцертификате на IIS вебекст")</span><span class="sxs-lookup"><span data-stu-id="e0ceb-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e0ceb-140">Проверка и Настройка проверки подлинности и сертификатов в виртуальных каталогах IIS</span><span class="sxs-lookup"><span data-stu-id="e0ceb-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e0ceb-141">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Администрирование**, а затем — пункт **Диспетчер информационных служб Интернета (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="e0ceb-142">В **диспетчере информационных служб Интернета (IIS)** разверните узел **ServerName**и разверните узел **сайты**.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="e0ceb-143">Щелкните правой кнопкой мыши **внешний веб-сайт Lync Server**и выберите команду **изменить привязки** .</span><span class="sxs-lookup"><span data-stu-id="e0ceb-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="e0ceb-144">Убедитесь, что HTTPS сопоставлен с портом 4443, и нажмите кнопку **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="e0ceb-145">Выберите запись HTTPS, нажмите кнопку **изменить**, а затем убедитесь, что к этому протоколу привязывается Lync Server вебсервицесекстерналцертификате.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="e0ceb-146">Сравните отпечаток командлета Set-Ксцертификате, чтобы убедиться, что ожидаемый сертификат правильно связан с привязкой HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e0ceb-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e0ceb-147">См. также</span><span class="sxs-lookup"><span data-stu-id="e0ceb-147">See Also</span></span>


[<span data-ttu-id="e0ceb-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e0ceb-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="e0ceb-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e0ceb-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

