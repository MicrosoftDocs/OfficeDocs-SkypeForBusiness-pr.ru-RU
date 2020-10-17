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
ms.openlocfilehash: e97bb7d77bbd468fff18084ecc7d4da8c5feb7f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502116"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="76541-102">Настройка сертификатов для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76541-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76541-103">_**Последнее изменение темы:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="76541-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="76541-104">Для поддержки безопасных подключений с клиентами Lync в сертификатах для пула директоров, интерфейсных пулов и обратном прокси-сервере требуются дополнительные записи альтернативного имени субъекта.</span><span class="sxs-lookup"><span data-stu-id="76541-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76541-105">Вы можете использовать командлет <STRONG>Get-CsCertificate</STRONG> для просмотра сведений о сертификатах, назначенных в данный момент.</span><span class="sxs-lookup"><span data-stu-id="76541-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="76541-106">Однако в представлении по умолчанию не указываются свойства сертификата и отображаются не все значения в свойстве SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="76541-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="76541-107">Вы можете использовать командлеты <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate и <STRONG>Set-CsCertificate</STRONG>, чтобы просматривать некоторые сведения, а также запрашивать и назначать сертификаты.</span><span class="sxs-lookup"><span data-stu-id="76541-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="76541-108">Однако это не самый лучший способ в том случае, когда вы не уверены в свойствах альтернативных имен субъектов в текущем сертификате.</span><span class="sxs-lookup"><span data-stu-id="76541-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="76541-109">Для просмотра сертификата и всех участников свойств рекомендуется использовать оснастку "сертификаты" <EM>консоли управления (MMC)</EM> или мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76541-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="76541-110">В мастере развертывания Lync Server можно просмотреть свойства сертификата с помощью мастера сертификатов.</span><span class="sxs-lookup"><span data-stu-id="76541-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="76541-111">Процедуры просмотра, запроса и назначения сертификата с помощью командной консоли Lync Server и <EM>консоли управления (MMC)</EM> описаны в следующих процедурах.</span><span class="sxs-lookup"><span data-stu-id="76541-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="76541-112">Чтобы использовать мастер развертывания Lync Server, ознакомьтесь с подробными сведениями, если вы развернули пул необязательных директоров или директоров директоров: <A href="lync-server-2013-configure-certificates-for-the-director.md">Настройка сертификатов для директора в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="76541-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="76541-113">Сведения о сервере переднего плана или интерфейсном пуле можно найти здесь: <A href="lync-server-2013-configure-certificates-for-servers.md">Настройка сертификатов для серверов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="76541-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="76541-114">Начальные шаги этой процедуры являются подготовительными действиями, призванными сориентировать вас относительно роли текущего сертификата.</span><span class="sxs-lookup"><span data-stu-id="76541-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="76541-115">По умолчанию сертификаты не будут иметь lyncdiscover. &lt; sipdomain &gt; или lyncdiscoverinternal. &lt; Внутренняя запись доменного имени &gt; , если вы еще не установили службы Mobility Service или заранее подготовили свои сертификаты.</span><span class="sxs-lookup"><span data-stu-id="76541-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="76541-116">В данной процедуре используется пример имени домена SIP «contoso.com» и пример внутреннего имени домена «contoso.net».</span><span class="sxs-lookup"><span data-stu-id="76541-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="76541-117">Конфигурация сертификата по умолчанию для Lync Server 2013 и Lync Server 2010 — использовать один сертификат (с именем "default") по умолчанию (для всех целей, кроме веб-служб), WebServicesExternal и WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="76541-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="76541-118">Дополнительная конфигурация заключается в использовании отдельных сертификатов для каждого назначения.</span><span class="sxs-lookup"><span data-stu-id="76541-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="76541-119">Управление сертификатами осуществляется с помощью Командная консоль Lync Server и командлеты Windows PowerShell или с помощью мастера сертификатов в мастере развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76541-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="76541-120">Обновление сертификатов с использованием новых альтернативных имен субъектов с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="76541-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="76541-121">Войдите на компьютер, используя учетную запись с правами и разрешениями локального администратора.</span><span class="sxs-lookup"><span data-stu-id="76541-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="76541-122">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="76541-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="76541-p104">Определите, какие сертификаты были назначены серверу и для какого типа использования. Эта информация потребуется вам на следующем шаге для назначения обновленного сертификата. Введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="76541-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="76541-p105">Просмотрите выходные данные из предыдущего шага, чтобы узнать, назначен ли нескольким использованиям один сертификат или для каждого из них назначен отдельный сертификат. Посмотрите на параметр Use, чтобы выяснить, как используется сертификат. Сравните параметр  Thumbprint для отображаемых сертификатов, чтобы узнать, имеет ли один сертификат несколько использований.</span><span class="sxs-lookup"><span data-stu-id="76541-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="76541-p106">Обновите сертификат. Введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="76541-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="76541-131">Например, если командлет **Get-CsCertificate** отобразил сертификат, у которого для параметра Use установлено значение Default, другой сертификат со значением WebServicesInternal и еще один со значением WebServicesExternal, и все они имеют одинаковое значение Thumbprint, введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="76541-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="76541-132">**Важно!**</span><span class="sxs-lookup"><span data-stu-id="76541-132">**Important:**</span></span>
    
    <span data-ttu-id="76541-133">Если каждому использованию назначен отдельный сертификат (значение Thumbprint различно для каждого из сертификатов), важно не запускать командлет **Set-CsCertificate** с несколькими типами.</span><span class="sxs-lookup"><span data-stu-id="76541-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="76541-134">В данном случае отдельно запустите командлет **Set-CsCertificate** для каждого использования.</span><span class="sxs-lookup"><span data-stu-id="76541-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="76541-135">Например:</span><span class="sxs-lookup"><span data-stu-id="76541-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="76541-p108">Чтобы просмотреть сертификат, нажмите кнопку **Пуск**, щелкните **Выполнить…**. Введите MMC, чтобы открыть консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="76541-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="76541-p109">В меню консоли управления (MMC) выберите **Файл**, **Добавить или удалить оснастку…**, «Сертификаты». Нажмите кнопку **Добавить**. При отображении запроса выберите **учетной записи компьютера**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="76541-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="76541-141">Если сертификат находится на этом компьютере, выберите **локальный компьютер**.</span><span class="sxs-lookup"><span data-stu-id="76541-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="76541-142">Если сертификат находится на другом компьютере, выберите **другой компьютер**, введите полное доменное имя компьютера или нажмите кнопку **Обзор** в поле **введите имя объекта для выбора**, введите имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="76541-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="76541-143">Щелкните элемент **Проверить имена**.</span><span class="sxs-lookup"><span data-stu-id="76541-143">Click **Check Names**.</span></span> <span data-ttu-id="76541-144">После разрешения имени компьютера оно подчеркивается.</span><span class="sxs-lookup"><span data-stu-id="76541-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="76541-145">Нажмите кнопку **ОК**, а затем кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="76541-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="76541-146">Нажмите кнопку **ОК** для подтверждения выбора и закройте диалоговое окно **Добавление и удаление оснасток**.</span><span class="sxs-lookup"><span data-stu-id="76541-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="76541-147">Если сертификат не отображается в консоли, убедитесь, что вы не выбрали пользователя или службу.</span><span class="sxs-lookup"><span data-stu-id="76541-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="76541-148">Необходимо выбрать компьютер, или вы не сможете определить сертификат пробпер.</span><span class="sxs-lookup"><span data-stu-id="76541-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="76541-p112">Чтобы просмотреть свойства сертификата, разверните узел **Сертификаты**, разверните узел **Личные** и выберите элемент **Сертификаты**. Выберите сертификат для просмотра, щелкните его правой кнопкой мыши и выберите пункт **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="76541-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="76541-p113">В представлении **Сертификат** выберите элемент **Сведения**. Здесь вы можете выбрать имя субъекта сертификата, выбрав элемент **Субъект**, после чего отображаются назначенное имя субъекта и связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="76541-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="76541-153">Чтобы просмотреть назначенные альтернативные имена субъектов, выберите **Альтернативное имя субъекта**.</span><span class="sxs-lookup"><span data-stu-id="76541-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="76541-154">Отображаются все назначенные альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="76541-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="76541-155">Найденные в свойстве альтернативные имена субъектов по умолчанию имеют тип **DNS-имя**.</span><span class="sxs-lookup"><span data-stu-id="76541-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="76541-156">Вам следует просмотреть следующие элементы (в соответствии с записями DNS-узла (A либо AAAA для IPv6) все они должны быть полными доменными именами:</span><span class="sxs-lookup"><span data-stu-id="76541-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="76541-157">Имя пула для этого пула или имя отдельного сервера, если это не пул</span><span class="sxs-lookup"><span data-stu-id="76541-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="76541-158">Имя сервера, которому назначен сертификат</span><span class="sxs-lookup"><span data-stu-id="76541-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="76541-159">Записи простых URL-адресов (обычно meet и dialin)</span><span class="sxs-lookup"><span data-stu-id="76541-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="76541-160">Внутренние имена веб-служб и внешние имена веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в построителе топологий и переопределенных на выборе веб-службах.</span><span class="sxs-lookup"><span data-stu-id="76541-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="76541-161">Если уже назначено, lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="76541-161">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="76541-162">и lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="76541-162">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="76541-163">запис.</span><span class="sxs-lookup"><span data-stu-id="76541-163">records.</span></span>
    
    <span data-ttu-id="76541-164">Последний элемент представляет для вас наибольший интерес — наличие записи альтернативного имени субъекта lyncdiscover и lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="76541-164">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="76541-165">После получения этой информации вы можете закрыть представление сертификата и консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="76541-165">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="76541-166">Если служба автообнаружения, то есть lyncdiscover. \> доменное имя \> и lyncdiscoverinternal.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="76541-166">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\></span></span> <span data-ttu-id="76541-167">(в зависимости от того, что это внешний или внутренний сертификат) отсутствует альтернативное имя субъекта, и вы используете один сертификат по умолчанию для типов WebServicesInternal и Вебсервицеекстернал по умолчанию, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="76541-167">(based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="76541-168">В командной строке командной строки командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="76541-168">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="76541-169">Если у вас имеется много SIP-доменов, вы не можете использовать новый параметр AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="76541-169">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="76541-170">Вместо этого вам следует использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="76541-170">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="76541-171">Когда вы используете параметр DomainName, вам следует определить полное доменное имя для записей lyncdisscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="76541-171">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="76541-172">Например:</span><span class="sxs-lookup"><span data-stu-id="76541-172">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="76541-173">Чтобы назначить сертификат, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="76541-173">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="76541-174">Где «Thumbprint» — это отпечаток, отображаемый для недавно выданного сертификата.</span><span class="sxs-lookup"><span data-stu-id="76541-174">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="76541-175">В случае отсутствия внутренних альтернативных имен субъектов автообнаружения при использовании отдельных сертификатов для Default, WebServicesInternal и WebServicesExternal выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="76541-175">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="76541-176">В командной строке командной строки командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="76541-176">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="76541-p118">Если у вас имеется много SIP-доменов, вы не можете использовать новый параметр AllSipDomain. Вместо этого вам следует использовать параметр DomainName. Когда вы используете параметр DomainName, вам следует определить подходящий префикс для полного доменного имени. Например:</span><span class="sxs-lookup"><span data-stu-id="76541-p118">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="76541-181">В случае отсутствия внешнего альтернативного имени субъекта автообнаружения введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="76541-181">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="76541-p119">Если у вас имеется много SIP-доменов, вы не можете использовать новый параметр AllSipDomain. Вместо этого вам следует использовать параметр DomainName. Когда вы используете параметр DomainName, вам следует определить подходящий префикс для полного доменного имени. Например:</span><span class="sxs-lookup"><span data-stu-id="76541-p119">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="76541-186">Чтобы назначить индивидуальные типы сертификатов, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="76541-186">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="76541-187">Где «Thumbprint» — это отпечаток, отображаемый для недавно выданных индивидуальных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="76541-187">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

