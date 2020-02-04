---
title: 'Lync Server 2013: изменение сертификатов для мобильной работы'
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="44dc5-102">Изменение сертификатов для мобильной работы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44dc5-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44dc5-103">_**Тема последнего изменения:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="44dc5-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="44dc5-104">Для обеспечения защищенных подключений между средой Lync и мобильными клиентами вы должны обновить сертификаты SSL для вашего пула, а также для пользовательского пула и обратного прокси-сервера с помощью дополнительного имени субъекта ( SAN).</span><span class="sxs-lookup"><span data-stu-id="44dc5-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="44dc5-105">Если вам нужно извлечь дополнительные сведения о требованиях к сертификатам для мобильных устройств, ознакомьтесь с разделом требования к сертификату в [технических требованиях для мобильных устройств в Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), но в основном вам потребуется получить новые сертификаты из центра сертификации с дополнительными записями San, а затем добавить их, выполнив действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="44dc5-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="44dc5-106">Конечно, прежде чем приступить к работе, лучше узнать, какие другие имена уже есть у ваших сертификатов.</span><span class="sxs-lookup"><span data-stu-id="44dc5-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="44dc5-107">Если вы не уверены в том, что уже настроено, вы можете узнать, как это сделать. Несмотря на то, что вы можете использовать команды **Get-ксцертификате** и других команд PowerShell для просмотра этих данных (что мы рассмотрим ниже) по умолчанию, что данные будут обрезаны, поэтому вам может не получиться Просмотреть все нужные свойства.</span><span class="sxs-lookup"><span data-stu-id="44dc5-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="44dc5-108">Чтобы получить хорошее представление о сертификате и всех его свойствах, вы можете открыть консоль управления (MMC) и загрузить оснастку "сертификаты" (которую также можно проанализировать ниже) или просто установить мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44dc5-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="44dc5-109">Как указано выше, описанные выше действия помогут вам обновить сертификаты с помощью командной консоли Lync Server Management Shell и MMC.</span><span class="sxs-lookup"><span data-stu-id="44dc5-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="44dc5-110">Если вы заинтересованы в использовании мастера сертификатов в мастере развертывания Lync Server, вы можете проверить [настройку сертификатов для режиссера в Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) для режиссера или режиссера, если вы настроили один из них (возможно, у вас нет).</span><span class="sxs-lookup"><span data-stu-id="44dc5-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="44dc5-111">Для внешнего сервера или пула переднего плана вам потребуется [настроить сертификаты для серверов в Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="44dc5-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="44dc5-112">Последнее, что следует помнить, — может иметься один сертификат по умолчанию в среде Lync Server 2013 или отдельные сертификаты для по умолчанию (все, кроме веб-служб), Вебсервицесекстернал и Вебсервицесинтернал.</span><span class="sxs-lookup"><span data-stu-id="44dc5-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="44dc5-113">Если вы не хотите настраивать конфигурацию, вам помогут эти действия.</span><span class="sxs-lookup"><span data-stu-id="44dc5-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="44dc5-114">Обновление сертификатов с использованием новых альтернативных имен для некоторых субъектов с помощью командной консоли Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="44dc5-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="44dc5-115">Необходимо войти на сервер Lync Server 2013 с помощью учетной записи, обладающей правами и разрешениями локального администратора.</span><span class="sxs-lookup"><span data-stu-id="44dc5-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="44dc5-116">Кроме того, если вы запускаете **запрос PowerShell — ксцертификате** на шагах 12 и более поздних, учетной записи должны быть предоставлены права на указанный центр сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="44dc5-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="44dc5-117">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="44dc5-118">Прежде чем вы сможете назначить обновленный сертификат, вам нужно узнать, какие сертификаты были назначены серверу и для какого типа использования.</span><span class="sxs-lookup"><span data-stu-id="44dc5-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="44dc5-119">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="44dc5-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="44dc5-120">Просмотрите результаты предыдущего шага, чтобы узнать, назначен ли один сертификат для нескольких применений, или назначается ли другой сертификат для каждого использования.</span><span class="sxs-lookup"><span data-stu-id="44dc5-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="44dc5-121">Чтобы узнать, как будет использоваться сертификат, найдите параметр Use.</span><span class="sxs-lookup"><span data-stu-id="44dc5-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="44dc5-122">Сравните параметр отпечатка для выводимых сертификатов, чтобы узнать, используется ли один и тот же сертификат несколько.</span><span class="sxs-lookup"><span data-stu-id="44dc5-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="44dc5-123">Проследите за параметром отпечатка.</span><span class="sxs-lookup"><span data-stu-id="44dc5-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="44dc5-124">Обновите сертификат.</span><span class="sxs-lookup"><span data-stu-id="44dc5-124">Update the certificate.</span></span> <span data-ttu-id="44dc5-125">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="44dc5-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="44dc5-126">Например, если командлет **Get-ксцертификате** показывает сертификат с использованием параметров по умолчанию, другой — с использованием вебсервицесинтернал, а другой — с помощью вебсервицесекстернал, и все они имеют одинаковое значение отпечатка, введите:</span><span class="sxs-lookup"><span data-stu-id="44dc5-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="44dc5-127">**Важно!**</span><span class="sxs-lookup"><span data-stu-id="44dc5-127">**Important:**</span></span>
    
    <span data-ttu-id="44dc5-128">Если вы назначаете отдельный сертификат для каждого использования (поэтому значение отпечатка, которое вы проверили выше для каждого сертификата), крайне важно, чтобы вы **не** выполняли командлет **Set-ксцертификате** с несколькими типами, как в приведенном выше примере.</span><span class="sxs-lookup"><span data-stu-id="44dc5-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="44dc5-129">В этом случае выполните командлет **Set-ксцертификате** отдельно для каждого использования.</span><span class="sxs-lookup"><span data-stu-id="44dc5-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="44dc5-130">Например:</span><span class="sxs-lookup"><span data-stu-id="44dc5-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="44dc5-131">Чтобы просмотреть сертификат (или сертификаты), нажмите кнопку **Пуск**и выберите команду **выполнить...**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="44dc5-132">Введите MMC, чтобы открыть консоль управления MMC.</span><span class="sxs-lookup"><span data-stu-id="44dc5-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="44dc5-133">В меню MMC выберите пункт **файл**, а затем — **Добавить или удалить оснастку...**, выберите пункт Сертификаты.</span><span class="sxs-lookup"><span data-stu-id="44dc5-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="44dc5-134">Нажмите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-134">Click **Add**.</span></span> <span data-ttu-id="44dc5-135">При появлении соответствующего запроса выберите пункт **учетная запись компьютера**, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="44dc5-136">Если это сервер, на котором находится сертификат, выберите **локальный компьютер**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="44dc5-137">Если сертификат расположен на другом компьютере, выберите **другой компьютер**, а затем введите полное доменное имя компьютера или нажмите кнопку **Обзор** в поле **введите имя нужного объекта**и введите имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="44dc5-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="44dc5-138">Нажмите кнопку **Проверить имена**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-138">Click **Check Names**.</span></span> <span data-ttu-id="44dc5-139">После разрешения имени компьютера оно будет подчеркнуто.</span><span class="sxs-lookup"><span data-stu-id="44dc5-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="44dc5-140">Нажмите кнопку **ОК**, а затем — **Готово**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="44dc5-141">Нажмите кнопку **ОК** , чтобы завершить выбор и закрыть диалоговое окно **Добавление и удаление оснасток** .</span><span class="sxs-lookup"><span data-stu-id="44dc5-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="44dc5-142">Чтобы просмотреть свойства сертификата, разверните раздел **Сертификаты**и выберите пункт **Личные**, а затем — **Сертификаты**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="44dc5-143">Выберите сертификат для просмотра, щелкните сертификат правой кнопкой мыши и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="44dc5-144">В представлении **сертификата** выберите **сведения**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="44dc5-145">Здесь вы можете выбрать имя субъекта сертификата, выделив **тему** , а также отобразить назначенное имя субъекта и связанные свойства.</span><span class="sxs-lookup"><span data-stu-id="44dc5-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="44dc5-146">Чтобы просмотреть назначенные альтернативные имена для темы, выберите **дополнительное имя субъекта**.</span><span class="sxs-lookup"><span data-stu-id="44dc5-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="44dc5-147">Здесь отображаются все назначенные альтернативные имена для темы.</span><span class="sxs-lookup"><span data-stu-id="44dc5-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="44dc5-148">Поиск по умолчанию альтернативных имен для темы имеет тип **DNS-имя** .</span><span class="sxs-lookup"><span data-stu-id="44dc5-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="44dc5-149">Должны отобразиться следующие участники (все должны быть полные доменные имена, представленные в DNS-адресах (а или, если записи IPv6 AAAA).</span><span class="sxs-lookup"><span data-stu-id="44dc5-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="44dc5-150">Имя пула для этого пула или имя отдельного сервера, если он не является пулом</span><span class="sxs-lookup"><span data-stu-id="44dc5-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="44dc5-151">Имя сервера, которому назначен сертификат</span><span class="sxs-lookup"><span data-stu-id="44dc5-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="44dc5-152">Простые URL-записи, обычно соответствующие требованиям и набору номера</span><span class="sxs-lookup"><span data-stu-id="44dc5-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="44dc5-153">Внутренние имена внутренних и веб-служб (например, webpool01.contoso.net, webpool01.contoso.com), основанные на вариантах, сделанных в построителе топологии, и переопределяемые выборы веб-служб.</span><span class="sxs-lookup"><span data-stu-id="44dc5-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="44dc5-154">Если уже назначено, lyncdiscover. \<сипдомаин\> и линкдисковеринтернал. \<сипдомаин\> записи.</span><span class="sxs-lookup"><span data-stu-id="44dc5-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="44dc5-155">Последний элемент — это то, что вам интересно, если у тебя есть lyncdiscover и линкдисковеринтернал сеть SAN.</span><span class="sxs-lookup"><span data-stu-id="44dc5-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="44dc5-156">Если вы хотите проверить несколько сертификатов, повторите эти действия.</span><span class="sxs-lookup"><span data-stu-id="44dc5-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="44dc5-157">После получения этих сведений вы можете закрыть представление сертификата и MMC.</span><span class="sxs-lookup"><span data-stu-id="44dc5-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="44dc5-158">Если отсутствует альтернативное имя субъекта службы автообнаружения и используется один сертификат по умолчанию для типов по умолчанию, Вебсервицесинтернал и Вебсервицеекстернал, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="44dc5-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="44dc5-159">В командной строке оболочки Lync Server Management Shell введите:</span><span class="sxs-lookup"><span data-stu-id="44dc5-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="44dc5-160">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="44dc5-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="44dc5-161">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="44dc5-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="44dc5-162">Если вы используете параметр DomainName, вам нужно определить полное доменное имя для записей линкдисковеринтернал и lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="44dc5-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="44dc5-163">Например:</span><span class="sxs-lookup"><span data-stu-id="44dc5-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="44dc5-164">Чтобы назначить сертификат, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="44dc5-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="44dc5-165">Где "отпечаток" — это отпечаток для нового выданного сертификата.</span><span class="sxs-lookup"><span data-stu-id="44dc5-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="44dc5-166">Для отсутствующей внутренней сети SAN для автообнаружения при использовании отдельных сертификатов для параметров по умолчанию, Вебсервицесинтернал и Вебсервицесекстернал выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="44dc5-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="44dc5-167">В командной строке оболочки Lync Server Management Shell введите:</span><span class="sxs-lookup"><span data-stu-id="44dc5-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="44dc5-168">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="44dc5-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="44dc5-169">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="44dc5-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="44dc5-170">При использовании параметра DomainName вы можете использовать соответствующий префикс для доменного имени SIP domain.</span><span class="sxs-lookup"><span data-stu-id="44dc5-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="44dc5-171">Например:</span><span class="sxs-lookup"><span data-stu-id="44dc5-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="44dc5-172">Чтобы получить отсутствующее дополнительное имя для субъекта автообнаружения, в командной строке введите:</span><span class="sxs-lookup"><span data-stu-id="44dc5-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="44dc5-173">Если у вас много доменов SIP, вы не можете использовать новый параметр Аллсипдомаин.</span><span class="sxs-lookup"><span data-stu-id="44dc5-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="44dc5-174">Вместо этого необходимо использовать параметр DomainName.</span><span class="sxs-lookup"><span data-stu-id="44dc5-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="44dc5-175">При использовании параметра DomainName вы можете использовать соответствующий префикс для доменного имени SIP domain.</span><span class="sxs-lookup"><span data-stu-id="44dc5-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="44dc5-176">Например:</span><span class="sxs-lookup"><span data-stu-id="44dc5-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="44dc5-177">Чтобы назначить индивидуальные типы сертификатов, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="44dc5-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="44dc5-178">Где "отпечаток" — это отпечаток для вновь выданных индивидуальных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="44dc5-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="44dc5-179">Обратите внимание, что шаги 12 и 13 должны выполняться только в том случае, если у учетной записи, с которой они работают, есть доступ к центру сертификации с необходимыми разрешениями.</span><span class="sxs-lookup"><span data-stu-id="44dc5-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="44dc5-180">Если вы не можете войти в систему с помощью учетной записи, для которой у вас есть такие разрешения, или если у вас есть общедоступный или удаленный центр сертификации для ваших сертификатов, вам потребуются мастер развертывания Lync Server, который был использован в верхней части данной.</span><span class="sxs-lookup"><span data-stu-id="44dc5-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

