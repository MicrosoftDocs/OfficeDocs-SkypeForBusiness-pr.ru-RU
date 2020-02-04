---
title: 'Lync Server 2013: Настройка сертификатов для автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758337"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="68a77-102">Настройка сертификатов для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68a77-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68a77-103">_**Тема последнего изменения:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="68a77-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="68a77-104">Для использования сертификатов для вашего пула каталогов, пула переднего плана и обратного прокси требуются дополнительные записи альтернативного имени для обеспечения безопасной связи с клиентами Lync.</span><span class="sxs-lookup"><span data-stu-id="68a77-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68a77-105">Вы можете использовать командлет <STRONG>Get-ксцертификате</STRONG> для просмотра сведений о текущих назначенных сертификатах.</span><span class="sxs-lookup"><span data-stu-id="68a77-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="68a77-106">Однако представление по умолчанию усекает свойства сертификата и не отображает все значения в свойстве Субжекталтернативенамес.</span><span class="sxs-lookup"><span data-stu-id="68a77-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="68a77-107">Вы можете использовать командлеты <STRONG>Get-ксцертификате</STRONG> , <STRONG>request-</STRONG>Ксцертификате и <STRONG>Set-ксцертификате</STRONG> для просмотра некоторых данных и запроса и назначения сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68a77-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="68a77-108">Тем не менее, это не лучший способ использовать, если вы не знаете, какие свойства используются для альтернативных имен субъектов (SAN) для текущего сертификата.</span><span class="sxs-lookup"><span data-stu-id="68a77-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="68a77-109">Для просмотра сертификата и всех участников свойств рекомендуется использовать оснастку «Сертификаты» <EM>консоли управления (MMC)</EM> или мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68a77-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="68a77-110">В мастере развертывания Lync Server вы можете просматривать свойства сертификата с помощью мастера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68a77-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="68a77-111">Ниже описаны процедуры для просмотра, запроса и назначения сертификата с помощью командной консоли Lync Server Management Shell и <EM>консоль управления MMC</EM> .</span><span class="sxs-lookup"><span data-stu-id="68a77-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="68a77-112">Чтобы воспользоваться мастером развертывания Lync Server, ознакомьтесь с подробными сведениями, если вы развернули необязательный режиссер или Режиссер: <A href="lync-server-2013-configure-certificates-for-the-director.md">Настройка сертификатов для режиссера в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="68a77-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="68a77-113">Сведения о том, как <A href="lync-server-2013-configure-certificates-for-servers.md">настроить сертификаты для серверов в Lync server 2013</A>, можно найти на сервере переднего плана или в пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="68a77-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="68a77-114">Начальные шаги в этой процедуре предназначены для подготовки, чтобы расположить вас как роль, которую воспроизводится текущими сертификатами.</span><span class="sxs-lookup"><span data-stu-id="68a77-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="68a77-115">По умолчанию в сертификатах не будет lyncdiscover. &lt;сипдомаин&gt; или линкдисковеринтернал. &lt;внутренний доменный&gt; имя, если только вы ранее не установили службы Mobility Service или заранее подготовили свои сертификаты.</span><span class="sxs-lookup"><span data-stu-id="68a77-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="68a77-116">В этой процедуре используется пример имени домена SIP "contoso.com" и внутреннего доменного имени "contoso.net".</span><span class="sxs-lookup"><span data-stu-id="68a77-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="68a77-117">Конфигурация сертификата по умолчанию для Lync Server 2013 и Lync Server 2010 — использование единого сертификата (по умолчанию) с целью назначения по умолчанию (для всех целей, кроме веб-служб), Вебсервицесекстернал и Вебсервицесинтернал.</span><span class="sxs-lookup"><span data-stu-id="68a77-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="68a77-118">Необязательная настройка — это использование отдельных сертификатов для каждой цели.</span><span class="sxs-lookup"><span data-stu-id="68a77-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="68a77-119">Сертификаты можно управлять с помощью командной консоли Lync Server Management Shell и командлетов Windows PowerShell либо с помощью мастера сертификатов в мастере развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="68a77-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="68a77-120">Обновление сертификатов с использованием новых альтернативных имен для некоторых субъектов с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="68a77-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="68a77-121">Войдите в систему с помощью учетной записи, обладающей правами и разрешениями локального администратора.</span><span class="sxs-lookup"><span data-stu-id="68a77-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="68a77-122">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="68a77-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68a77-123">Узнайте, какие сертификаты были назначены серверу и для какого типа использования.</span><span class="sxs-lookup"><span data-stu-id="68a77-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="68a77-124">Вам понадобятся эти сведения на следующем этапе, чтобы назначить обновленный сертификат.</span><span class="sxs-lookup"><span data-stu-id="68a77-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="68a77-125">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68a77-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="68a77-126">Просмотрите результаты предыдущего шага, чтобы узнать, назначен ли один сертификат для нескольких применений, или назначается ли другой сертификат для каждого использования.</span><span class="sxs-lookup"><span data-stu-id="68a77-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="68a77-127">Чтобы узнать, как используется сертификат, найдите параметр Use.</span><span class="sxs-lookup"><span data-stu-id="68a77-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="68a77-128">Сравните параметр отпечатка для выводимых сертификатов, чтобы узнать, используется ли один и тот же сертификат несколько.</span><span class="sxs-lookup"><span data-stu-id="68a77-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="68a77-129">Обновите сертификат.</span><span class="sxs-lookup"><span data-stu-id="68a77-129">Update the certificate.</span></span> <span data-ttu-id="68a77-130">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68a77-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="68a77-131">Например, если командлет **Get-ксцертификате** показывает сертификат с использованием значения по умолчанию, другой — с помощью вебсервицесинтернал, а другой — с помощью вебсервицесекстернал, а для всех — с одинаковым значением отпечатка, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="68a77-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="68a77-132">**Важно!**</span><span class="sxs-lookup"><span data-stu-id="68a77-132">**Important:**</span></span>
    
    <span data-ttu-id="68a77-133">Если каждому использованию назначается отдельный сертификат (значение отпечатка отличается для каждого сертификата), важно не выполнять командлет **Set-ксцертификате** с несколькими типами.</span><span class="sxs-lookup"><span data-stu-id="68a77-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="68a77-134">В этом случае выполните командлет **Set-ксцертификате** отдельно для каждого использования.</span><span class="sxs-lookup"><span data-stu-id="68a77-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="68a77-135">Например:</span><span class="sxs-lookup"><span data-stu-id="68a77-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="68a77-136">Чтобы просмотреть сертификат, нажмите кнопку **Пуск**и выберите команду **выполнить...**.</span><span class="sxs-lookup"><span data-stu-id="68a77-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="68a77-137">Введите MMC, чтобы открыть консоль управления MMC.</span><span class="sxs-lookup"><span data-stu-id="68a77-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="68a77-138">В меню MMC выберите пункт **файл**, а затем — **Добавить или удалить оснастку...**, выберите пункт Сертификаты.</span><span class="sxs-lookup"><span data-stu-id="68a77-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="68a77-139">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="68a77-139">Click **Add**.</span></span> <span data-ttu-id="68a77-140">При появлении соответствующего запроса выберите пункт **учетная запись компьютера**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="68a77-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="68a77-141">Если сертификат находится на этом компьютере, выберите пункт **локальный компьютер**.</span><span class="sxs-lookup"><span data-stu-id="68a77-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="68a77-142">Если сертификат находится на другом компьютере, выберите **другой компьютер**, введите полное доменное имя компьютера или нажмите кнопку **Обзор** в поле **введите имя нужного объекта**, введите имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="68a77-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="68a77-143">Нажмите кнопку **Проверить имена**.</span><span class="sxs-lookup"><span data-stu-id="68a77-143">Click **Check Names**.</span></span> <span data-ttu-id="68a77-144">После разрешения имени компьютера оно будет подчеркнуто.</span><span class="sxs-lookup"><span data-stu-id="68a77-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="68a77-145">Нажмите кнопку **ОК**, а затем — **Готово**.</span><span class="sxs-lookup"><span data-stu-id="68a77-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="68a77-146">Нажмите кнопку **ОК** , чтобы завершить выбор и закрыть диалоговое окно **Добавление и удаление оснасток** .</span><span class="sxs-lookup"><span data-stu-id="68a77-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="68a77-147">Если сертификат не отображается на консоли, убедитесь, что вы не выбрали пользователя или службу.</span><span class="sxs-lookup"><span data-stu-id="68a77-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="68a77-148">Необходимо выбрать компьютер, или вы не сможете найти сертификат пробпер.</span><span class="sxs-lookup"><span data-stu-id="68a77-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="68a77-149">Чтобы просмотреть свойства сертификата, разверните раздел **Сертификаты**и выберите пункт **Личные**, а затем — **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="68a77-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="68a77-150">Выберите сертификат для просмотра, щелкните сертификат правой кнопкой мыши и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="68a77-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="68a77-151">В представлении **сертификата** выберите **сведения**.</span><span class="sxs-lookup"><span data-stu-id="68a77-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="68a77-152">Здесь вы можете выбрать имя субъекта сертификата, выделив **тему** , а также отобразить назначенное имя субъекта и связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="68a77-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="68a77-153">Чтобы просмотреть назначенные альтернативные имена для темы, выберите **дополнительное имя субъекта**.</span><span class="sxs-lookup"><span data-stu-id="68a77-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="68a77-154">Отображаются все назначенные альтернативные имена для темы.</span><span class="sxs-lookup"><span data-stu-id="68a77-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="68a77-155">По умолчанию в качестве альтернативных имен для темы, которые находятся в свойстве, используется **DNS-имя** .</span><span class="sxs-lookup"><span data-stu-id="68a77-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="68a77-156">Должны отобразиться следующие участники (все должны быть полные доменные имена, представленные в DNS-адресах (а или, если записи IPv6 AAAA).</span><span class="sxs-lookup"><span data-stu-id="68a77-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="68a77-157">Имя пула для этого пула или имя одного сервера, если он не является пулом.</span><span class="sxs-lookup"><span data-stu-id="68a77-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="68a77-158">Имя сервера, которому назначен сертификат</span><span class="sxs-lookup"><span data-stu-id="68a77-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="68a77-159">Простые URL-записи, обычно соответствующие требованиям и набору номера</span><span class="sxs-lookup"><span data-stu-id="68a77-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="68a77-160">Внутренние имена внутренних и веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в построителе топологии, и переопределяемые выборы веб-служб.</span><span class="sxs-lookup"><span data-stu-id="68a77-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="68a77-161">Если уже назначено, lyncdiscover. \<сипдомаин\> и линкдисковеринтернал. \<сипдомаин\> записи.</span><span class="sxs-lookup"><span data-stu-id="68a77-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="68a77-162">Последний элемент является наиболее подинтересен – если имеется lyncdiscover и линкдисковеринтернал сеть SAN.</span><span class="sxs-lookup"><span data-stu-id="68a77-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="68a77-163">После получения этих сведений вы можете закрыть представление сертификата и MMC.</span><span class="sxs-lookup"><span data-stu-id="68a77-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="68a77-164">Если служба автообнаружения, то есть lyncdiscover. \>доменное\> имя и линкдисковеринтернал. \<доменное\> имя (в зависимости от того, является ли это внешнему или внутренним сертификатом) отсутствует альтернативное имя субъекта, и вы используете один сертификат по умолчанию для типов по умолчанию, вебсервицесинтернал и вебсервицеекстернал, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="68a77-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="68a77-165">В командной строке оболочки Lync Server Management Shell введите:</span><span class="sxs-lookup"><span data-stu-id="68a77-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="68a77-166">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="68a77-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="68a77-167">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="68a77-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="68a77-168">Если вы используете параметр DomainName, необходимо определить полные доменные имена для записей линкдисковеринтернал и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="68a77-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="68a77-169">Например:</span><span class="sxs-lookup"><span data-stu-id="68a77-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="68a77-170">Чтобы назначить сертификат, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="68a77-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="68a77-171">Где "отпечаток" — это отпечаток для нового выданного сертификата.</span><span class="sxs-lookup"><span data-stu-id="68a77-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="68a77-172">Для отсутствующего альтернативных имен субъектов автообнаружения при использовании отдельных сертификатов для параметров по умолчанию, Вебсервицесинтернал и Вебсервицесекстернал выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="68a77-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="68a77-173">В командной строке оболочки Lync Server Management Shell введите:</span><span class="sxs-lookup"><span data-stu-id="68a77-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="68a77-174">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="68a77-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="68a77-175">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="68a77-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="68a77-176">Если вы используете параметр DomainName, необходимо использовать соответствующий префикс для полного доменного имени домена SIP.</span><span class="sxs-lookup"><span data-stu-id="68a77-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="68a77-177">Например:</span><span class="sxs-lookup"><span data-stu-id="68a77-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="68a77-178">Чтобы получить отсутствующее дополнительное имя для субъекта автообнаружения, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="68a77-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="68a77-179">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="68a77-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="68a77-180">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="68a77-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="68a77-181">Если вы используете параметр DomainName, необходимо использовать соответствующий префикс для полного доменного имени домена SIP.</span><span class="sxs-lookup"><span data-stu-id="68a77-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="68a77-182">Например:</span><span class="sxs-lookup"><span data-stu-id="68a77-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="68a77-183">Чтобы назначить индивидуальные типы сертификатов, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68a77-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="68a77-184">Где "отпечаток" — это отпечаток для вновь выданных индивидуальных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68a77-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

