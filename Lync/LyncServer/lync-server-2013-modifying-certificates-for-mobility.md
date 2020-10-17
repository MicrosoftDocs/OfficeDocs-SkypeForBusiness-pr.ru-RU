---
title: 'Lync Server 2013: изменение сертификатов для мобильной работы'
description: 'Lync Server 2013: изменение сертификатов для мобильной работы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555855"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="55b0f-103">Изменение сертификатов для мобильных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55b0f-103">Modifying certificates for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55b0f-104">_**Последнее изменение темы:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="55b0f-104">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="55b0f-105">Для поддержки безопасных подключений между средой Lync и мобильными клиентами необходимо обновить сертификаты SSL для пула директоров, интерфейсного пула и обратного прокси-сервера с помощью дополнительных записей альтернативного имени субъекта (SAN).</span><span class="sxs-lookup"><span data-stu-id="55b0f-105">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="55b0f-106">Если вам нужно узнать больше о требованиях к сертификатам для мобильных устройств, ознакомьтесь со статьей "требования к сертификату" в разделе [технические требования для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), но в основном вам потребуется получить новые сертификаты из центра сертификации с дополнительными записями San, а затем добавить их, выполнив действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="55b0f-106">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="55b0f-107">Конечно, прежде чем начать, рекомендуется знать, какие альтернативные имена субъектов уже имеют сертификаты.</span><span class="sxs-lookup"><span data-stu-id="55b0f-107">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="55b0f-108">Если вы не уверены в том, что уже настроено, существует множество способов. В этом случае можно выполнить команды **Get-CsCertificate** и другие команды PowerShell для просмотра этих сведений (по умолчанию), чтобы эти данные были усечены, поэтому вы можете не увидеть все необходимые свойства.</span><span class="sxs-lookup"><span data-stu-id="55b0f-108">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="55b0f-109">Чтобы получить хорошее представление о сертификате и всех его свойствах, перейдите в консоль управления (MMC) и загрузите оснастку "сертификаты" (Кроме того, вы также можете выполнить описанные ниже шаги) или просто проверьте мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55b0f-109">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="55b0f-110">Как отмечалось выше, приведенные выше действия позволят выполнить обновление сертификатов с помощью командной консоли Lync Server и консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="55b0f-110">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="55b0f-111">Если вы заинтересованы в использовании мастера сертификатов в мастере развертывания Lync Server, то можно проверить [настройку сертификатов для директора в Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) для директории или пула директоров, если вы настроили один из них (возможно, у вас его нет).</span><span class="sxs-lookup"><span data-stu-id="55b0f-111">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="55b0f-112">Для сервера переднего плана или интерфейсного пула необходимо ознакомиться с [настройками сертификатов для серверов в Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="55b0f-112">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="55b0f-113">Последнее, что следует учитывать, это то, что у вас может быть один сертификат по умолчанию в среде Lync Server 2013, или вы можете использовать отдельные сертификаты для по умолчанию (все, кроме веб-служб), WebServicesExternal и WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="55b0f-113">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="55b0f-114">Как и в вашей конфигурации, эти действия должны помочь вам.</span><span class="sxs-lookup"><span data-stu-id="55b0f-114">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="55b0f-115">Обновление сертификатов с использованием новых альтернативных имен субъектов с помощью командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="55b0f-115">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="55b0f-116">Необходимо выполнить вход на сервер Lync Server 2013 с помощью учетной записи с правами и разрешениями локального администратора.</span><span class="sxs-lookup"><span data-stu-id="55b0f-116">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="55b0f-117">Кроме того, если вы используете PowerShell **request-CsCertificate** в шагах 12 и более поздних, учетная запись должна иметь права на доступ к указанному центру сертификации (CA).</span><span class="sxs-lookup"><span data-stu-id="55b0f-117">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="55b0f-118">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="55b0f-119">Прежде чем назначать обновленный сертификат, вам необходимо узнать, какие сертификаты были назначены серверу и для какого типа использования.</span><span class="sxs-lookup"><span data-stu-id="55b0f-119">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="55b0f-120">В командной строке введите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="55b0f-120">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="55b0f-121">Просмотрите результаты предыдущего действия, чтобы узнать, был ли один сертификат назначен для нескольких вариантов использования или назначен ли другой сертификат для каждого использования.</span><span class="sxs-lookup"><span data-stu-id="55b0f-121">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="55b0f-122">Просмотрите параметр Use, чтобы узнать, как используется сертификат.</span><span class="sxs-lookup"><span data-stu-id="55b0f-122">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="55b0f-123">Сравните параметр  Thumbprint для отображаемых сертификатов, чтобы узнать, имеет ли один сертификат несколько использований.</span><span class="sxs-lookup"><span data-stu-id="55b0f-123">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="55b0f-124">Следите за параметром Thumbprint.</span><span class="sxs-lookup"><span data-stu-id="55b0f-124">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="55b0f-125">Обновите сертификат.</span><span class="sxs-lookup"><span data-stu-id="55b0f-125">Update the certificate.</span></span> <span data-ttu-id="55b0f-126">Введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="55b0f-126">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="55b0f-127">Например, если командлет **Get – CsCertificate** показывает сертификат с использованием параметра Default, другой с использованием WebServicesInternal и другой с использованием WebServicesExternal, и все они имели одинаковое значение отпечатка, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="55b0f-127">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="55b0f-128">**Важно!**</span><span class="sxs-lookup"><span data-stu-id="55b0f-128">**Important:**</span></span>
    
    <span data-ttu-id="55b0f-129">Если для каждого использования назначается отдельный сертификат (поэтому значение отпечатка, указанное выше для каждого сертификата), крайне важно, чтобы **не** выполнять командлет **Set-CsCertificate** с несколькими типами, как в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="55b0f-129">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="55b0f-130">В данном случае отдельно запустите командлет **Set-CsCertificate** для каждого использования.</span><span class="sxs-lookup"><span data-stu-id="55b0f-130">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="55b0f-131">Например:</span><span class="sxs-lookup"><span data-stu-id="55b0f-131">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="55b0f-132">Чтобы просмотреть сертификат (или сертификаты), нажмите кнопку **Пуск**, выберите пункт **выполнить...**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-132">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="55b0f-133">Введите MMC, чтобы открыть консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="55b0f-133">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="55b0f-134">В меню консоли управления (MMC) выберите **Файл**, **Добавить или удалить оснастку…**, «Сертификаты».</span><span class="sxs-lookup"><span data-stu-id="55b0f-134">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="55b0f-135">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-135">Click **Add**.</span></span> <span data-ttu-id="55b0f-136">При отображении запроса выберите **учетной записи компьютера**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-136">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="55b0f-137">Если это сервер, на котором расположен сертификат, выберите **локальный компьютер**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-137">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="55b0f-138">Если сертификат находится на другом компьютере, выберите **другой компьютер**, а затем введите полное доменное имя компьютера или нажмите кнопку **Обзор** в поле **введите имя объекта для выбора**и введите имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="55b0f-138">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="55b0f-139">Нажмите кнопку **Проверить имена**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-139">Click **Check Names**.</span></span> <span data-ttu-id="55b0f-140">Когда имя компьютера разрешается, оно будет подчеркиванием.</span><span class="sxs-lookup"><span data-stu-id="55b0f-140">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="55b0f-141">Нажмите кнопку **ОК**, а затем кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-141">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="55b0f-142">Нажмите кнопку **ОК** для подтверждения выбора и закройте диалоговое окно **Добавление и удаление оснасток**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-142">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="55b0f-p113">Чтобы просмотреть свойства сертификата, разверните узел **Сертификаты**, разверните узел **Личные** и выберите элемент **Сертификаты**. Выберите сертификат для просмотра, щелкните его правой кнопкой мыши и выберите пункт **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="55b0f-p114">В представлении **Сертификат** выберите элемент **Сведения**. Здесь вы можете выбрать имя субъекта сертификата, выбрав элемент **Субъект**, после чего отображаются назначенное имя субъекта и связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="55b0f-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="55b0f-147">Чтобы просмотреть назначенные альтернативные имена субъектов, выберите **Альтернативное имя субъекта**.</span><span class="sxs-lookup"><span data-stu-id="55b0f-147">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="55b0f-148">Здесь отображаются все назначенные альтернативные имена субъектов.</span><span class="sxs-lookup"><span data-stu-id="55b0f-148">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="55b0f-149">Альтернативные имена субъектов, найденные здесь, имеют тип **DNS-имени** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="55b0f-149">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="55b0f-150">Вам следует просмотреть следующие элементы (в соответствии с записями DNS-узла (A либо AAAA для IPv6) все они должны быть полными доменными именами:</span><span class="sxs-lookup"><span data-stu-id="55b0f-150">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="55b0f-151">Имя пула для этого пула или имя отдельного сервера, если это не пул</span><span class="sxs-lookup"><span data-stu-id="55b0f-151">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="55b0f-152">Имя сервера, которому назначен сертификат</span><span class="sxs-lookup"><span data-stu-id="55b0f-152">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="55b0f-153">Записи простых URL-адресов (обычно meet и dialin)</span><span class="sxs-lookup"><span data-stu-id="55b0f-153">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="55b0f-154">Внутренние имена веб-служб и внешние имена веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в построителе топологий и переопределенных на выборе веб-службах.</span><span class="sxs-lookup"><span data-stu-id="55b0f-154">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="55b0f-155">Если уже назначено, lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="55b0f-155">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="55b0f-156">и lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="55b0f-156">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="55b0f-157">запис.</span><span class="sxs-lookup"><span data-stu-id="55b0f-157">records.</span></span>
    
    <span data-ttu-id="55b0f-158">Последний элемент является наиболее подинтересующимся: при наличии записи SAN lyncdiscover и lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="55b0f-158">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="55b0f-159">Повторите эти действия, если вы хотите проверить несколько сертификатов.</span><span class="sxs-lookup"><span data-stu-id="55b0f-159">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="55b0f-160">После получения этой информации вы можете закрыть представление сертификата и консоль управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="55b0f-160">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="55b0f-161">Если отсутствует альтернативное имя субъекта службы автообнаружения и вы используете один сертификат Default для типов Default, WebServicesInternal и WebServiceExternal, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="55b0f-161">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="55b0f-162">В командной строке командной строки командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="55b0f-162">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="55b0f-163">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="55b0f-163">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="55b0f-164">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="55b0f-164">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="55b0f-165">При использовании параметра имя_домена необходимо определить полное доменное имя для записей lyncdiscoverinternal и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="55b0f-165">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="55b0f-166">Например:</span><span class="sxs-lookup"><span data-stu-id="55b0f-166">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="55b0f-167">Чтобы назначить сертификат, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="55b0f-167">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="55b0f-168">Где «Thumbprint» — это отпечаток, отображаемый для недавно выданного сертификата.</span><span class="sxs-lookup"><span data-stu-id="55b0f-168">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="55b0f-169">Для отсутствия внутренней сети хранения данных для автообнаружения при использовании отдельных сертификатов для значений по умолчанию, WebServicesInternal и WebServicesExternal выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="55b0f-169">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="55b0f-170">В командной строке командной строки командной консоли Lync Server введите:</span><span class="sxs-lookup"><span data-stu-id="55b0f-170">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="55b0f-171">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="55b0f-171">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="55b0f-172">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="55b0f-172">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="55b0f-173">При использовании параметра имя_домена необходимо использовать соответствующий префикс для полного доменного имени домена SIP.</span><span class="sxs-lookup"><span data-stu-id="55b0f-173">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="55b0f-174">Например:</span><span class="sxs-lookup"><span data-stu-id="55b0f-174">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="55b0f-175">В случае отсутствия внешнего альтернативного имени субъекта автообнаружения введите в командной строке следующее:</span><span class="sxs-lookup"><span data-stu-id="55b0f-175">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="55b0f-176">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="55b0f-176">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="55b0f-177">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="55b0f-177">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="55b0f-178">При использовании параметра имя_домена необходимо использовать соответствующий префикс для полного доменного имени домена SIP.</span><span class="sxs-lookup"><span data-stu-id="55b0f-178">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="55b0f-179">Например:</span><span class="sxs-lookup"><span data-stu-id="55b0f-179">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="55b0f-180">Чтобы назначить индивидуальные типы сертификатов, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="55b0f-180">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="55b0f-181">Где «Thumbprint» — это отпечаток, отображаемый для недавно выданных индивидуальных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="55b0f-181">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="55b0f-182">Обратите внимание, что шаги 12 и 13 следует выполнять только в том случае, если у учетной записи, выполняющей их, есть доступ к центру сертификации с соответствующими разрешениями.</span><span class="sxs-lookup"><span data-stu-id="55b0f-182">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="55b0f-183">Если вы не можете войти в систему с помощью учетной записи, которой предоставлены эти разрешения, или если вы используете общедоступный или удаленный центр сертификации для ваших сертификатов, вам потребуется запросить их с помощью мастера развертывания Lync Server, который был использован в начале статьи.</span><span class="sxs-lookup"><span data-stu-id="55b0f-183">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

