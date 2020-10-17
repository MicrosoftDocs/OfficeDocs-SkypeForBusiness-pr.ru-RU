---
title: 'Lync Server 2013: Проверка или Настройка проверки подлинности и сертификации для виртуальных каталогов IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c07fc83680fd6b1d3f4d0d24429165ff9cc5ca65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518616"
---
# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="a7108-102">Проверка и Настройка проверки подлинности и сертификации в виртуальных каталогах IIS в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7108-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7108-103">_**Последнее изменение темы:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="a7108-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="a7108-104">Используйте следующую процедуру для настройки сертификата в виртуальных каталогах служб IIS или убедитесь, что сертификат настроен правильно.</span><span class="sxs-lookup"><span data-stu-id="a7108-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="a7108-105">Выполните приведенную ниже процедуру на каждом сервере, на котором выполняются службы IIS, в внутреннем пуле Lync Server, а также в дополнительном директоре или серверах пула директоров.</span><span class="sxs-lookup"><span data-stu-id="a7108-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a7108-106">Приведенная ниже процедура определяет процедуру запроса комбинированного сертификата, используемого для всех целей Lync Server, внутреннего веб-сайта и внешнего веб-сайта в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="a7108-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="a7108-107">Lync Server 2010 представил набор командлетов Windows PowerShell для консоли управления Lync Server, чтобы &nbsp; выразить цель управления запросом сертификата, импортом и назначением.</span><span class="sxs-lookup"><span data-stu-id="a7108-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="a7108-108">В данной процедуре предполагается, что существует внутренний развернутый центр сертификации (ЦС), который может обработать данный запрос.</span><span class="sxs-lookup"><span data-stu-id="a7108-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="a7108-109">Если вы используете общедоступные сертификаты для целей Lync Server, или для вашего ЦС требуется автономный запрос, ознакомьтесь с подробным синтаксисом, приведенным в этом разделе, для получения сведений о параметре – OUTPUT.</span><span class="sxs-lookup"><span data-stu-id="a7108-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="a7108-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request — CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="a7108-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="a7108-111">Настройка проверки подлинности и сертификатов для виртуальных каталогов служб IIS</span><span class="sxs-lookup"><span data-stu-id="a7108-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="a7108-112">Для успешного выполнения следующих действий необходимо войти на компьютер (сервер переднего плана или директор), где установлены веб-службы, и быть локальным администратором.</span><span class="sxs-lookup"><span data-stu-id="a7108-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="a7108-113">Вам следует иметь разрешения **read** и **enroll** для центра сертификации, из которого вы будете запрашивать сертификаты, если этот центр сертификации принадлежит вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a7108-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="a7108-114">Разрешения для центра сертификации не требуются, если вы настроите и отправите автономный запрос на сертификат.</span><span class="sxs-lookup"><span data-stu-id="a7108-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="a7108-115">Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="a7108-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="a7108-p104">В окне **Диспетчер служб IIS** выберите **Имя сервера**. В окне **Просмотр возможностей** выберите элемент **Сертификаты сервера**, щелкните правой кнопкой мыши и выберите пункт **Открытие функции**.</span><span class="sxs-lookup"><span data-stu-id="a7108-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a7108-p105">Если имеются сертификаты, назначенные данному серверу, они отображаются в этом представлении компонента сертификатов сервера. Если имеется сертификат, соответствующий требованиям для внешнего веб-сайта в службах IIS, вы можете использовать его повторно. Чтобы просмотреть сертификат, щелкните его правой кнопкой мыши и выберите пункт <STRONG>Просмотреть…</STRONG></span><span class="sxs-lookup"><span data-stu-id="a7108-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="a7108-121">На сервере переднего плана или режиссере, для которого запрашивается сертификат, нажмите кнопку **Пуск**, выберите **все программы**, выберите **Microsoft Lync Server 2013**и щелкните **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="a7108-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="a7108-122">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a7108-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="a7108-p106">выходные данные представляют собой список сертификатов, которые в данный момент находятся в хранилище личных сертификатов на компьютере. Обратите внимание на то, что в комбинированном сертификате (где компоненты по умолчанию, компоненты внутренних веб-служб и компоненты внешних веб-служб используют один и тот же сертификат) видно, что свойство Use заполняется значениями Default, WebServicesInternal и WebServicesExternal. Кроме того, свойство Thumbprint будет одинаковым для каждого из типов Use. Пример выходных данных Get-CsCertificate показан в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a7108-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="a7108-127">![Get – CsCertificate сведения о текущем состоянии сцерт](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate сведения о текущем состоянии сцерт")</span><span class="sxs-lookup"><span data-stu-id="a7108-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="a7108-128">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a7108-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="a7108-129">При этом полная команда выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a7108-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a7108-p107">По умолчанию Request-CsCertificate заполняет имя субъекта именем сервера или пула, а записи в альтернативном имени субъекта — полным доменным именем сервера, полным доменным именем пула, полными доменными именами простых URL-адресов, а также полными доменными именами внутренних и внешних веб-служб. Для этого командлет ссылается на документ топологии в вашем развертывании. Если вы указали параметр –Verbose, то в случае отсутствия какого-либо значения вы получаете уведомление о том, что расчетные и фактические значения для альтернативных имен различаются, однако этот параметр не сообщает вам, какие именно значения отсутствуют. Он предоставляет вам полное вычисленное значение, на которое ссылается командлет. Используйте строку вычисленных альтернативных имен в выходных данных, чтобы повторно запросить новый сертификат, включающий в себя все значения.</span><span class="sxs-lookup"><span data-stu-id="a7108-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="a7108-135">![Выходные данные запроса сертификата с помощью команды Request — Ксцертифика](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Выходные данные запроса сертификата с помощью Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="a7108-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="a7108-136">В командной консоли Lync Server введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a7108-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="a7108-137">При этом полная команда выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a7108-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="a7108-138">Выходные данные командлета Set-CsCertificate покажут, что один сертификат (обозначенный отпечатком сертификата) назначается для использования Default, WebServicesExternal и WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="a7108-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="a7108-139">![Выходные данные Set-CsCertificate на IIS Вебекст](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Выходные данные Set-CsCertificate на IIS Вебекст")</span><span class="sxs-lookup"><span data-stu-id="a7108-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="a7108-140">Настройка проверки подлинности и сертификатов для виртуальных каталогов служб IIS и подтверждение правильности такой настройки</span><span class="sxs-lookup"><span data-stu-id="a7108-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="a7108-141">Нажмите кнопку **Пуск**, выберите **Все программы**, **Администрирование** и затем **Диспетчер служб IIS**.</span><span class="sxs-lookup"><span data-stu-id="a7108-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="a7108-142">В **диспетчере служб IIS**разверните узел **ServerName**и разверните узел **сайты**.</span><span class="sxs-lookup"><span data-stu-id="a7108-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="a7108-143">Щелкните правой кнопкой мыши элемент **Lync Server External Web Site** (Внешний веб-сайт Lync Server) и выберите пункт **Изменить привязки**</span><span class="sxs-lookup"><span data-stu-id="a7108-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="a7108-144">Убедитесь, что HTTPS сопоставлен с портом 4443, а затем щелкните элемент **HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="a7108-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="a7108-145">Выберите запись HTTPS, нажмите кнопку **изменить**, а затем убедитесь, что сервер Lync Server вебсервицесекстерналцертификате связан с этим протоколом.</span><span class="sxs-lookup"><span data-stu-id="a7108-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="a7108-146">Сравните отпечаток из командлета Set-CsCertificate, чтобы убедиться, что ожидаемый сертификат правильно сопоставлен с привязкой HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a7108-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a7108-147">См. также</span><span class="sxs-lookup"><span data-stu-id="a7108-147">See Also</span></span>


[<span data-ttu-id="a7108-148">Get — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="a7108-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="a7108-149">Set — CsCertificate</span><span class="sxs-lookup"><span data-stu-id="a7108-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

