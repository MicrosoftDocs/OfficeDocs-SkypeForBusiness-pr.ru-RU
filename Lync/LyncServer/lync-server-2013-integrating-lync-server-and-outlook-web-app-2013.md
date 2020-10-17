---
title: 'Lync Server 2013: интеграция Lync Server и Outlook Web App 2013'
description: 'Lync Server 2013: интеграция Lync Server и Outlook Web App 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d9c7e91dba22f78325eaddc5b5d7469ccf4cc92
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567395"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="b4eac-103">Интеграция Microsoft Lync Server 2013 и Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="b4eac-103">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4eac-104">_**Последнее изменение темы:** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="b4eac-104">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="b4eac-105">Помимо интеграции с Microsoft Outlook 2013, Microsoft Lync Server 2013 может быть полностью интегрирован с Microsoft Outlook Web App 2013. Помимо прочего, добавляется обмен мгновенными сообщениями и сведения о присутствии в Outlook Web App, а также обеспечивается совместный доступ к единому списку контактов между Outlook Web App и Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b4eac-105">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="b4eac-106">Чтобы интегрировать Lync Server 2013 и Outlook Web App, необходимо сначала убедиться в том, что на внутреннем сервере Microsoft Exchange Server 2013 установлена среда выполнения Unified Communications Managed API 4,0.</span><span class="sxs-lookup"><span data-stu-id="b4eac-106">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="b4eac-107">Это можно сделать, просмотрев на наличие следующего раздела реестра:</span><span class="sxs-lookup"><span data-stu-id="b4eac-107">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="b4eac-108">\_Локальная \_ \\ система \\ CurrentControlSet \\ службы \\ MSExchange OWA \\ инстантмессагинг \\ имплементатиондллпас</span><span class="sxs-lookup"><span data-stu-id="b4eac-108">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="b4eac-109">Имплементатиондллпас должен указать расположение папки для файла Microsoft.Rtc.Internal.Ucweb.dll.</span><span class="sxs-lookup"><span data-stu-id="b4eac-109">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="b4eac-110">Если это не так или если значение реестра не существует, то необходимо скачать и установить программу установки среды выполнения UCMA из центра загрузки Майкрософт по адресу <https://www.microsoft.com/download/details.aspx?id=34992> .</span><span class="sxs-lookup"><span data-stu-id="b4eac-110">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <https://www.microsoft.com/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="b4eac-111">Сведения о том, как установить среду выполнения UCMA, можно найти на той же веб-странице.</span><span class="sxs-lookup"><span data-stu-id="b4eac-111">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="b4eac-112">**Обратная совместимость**</span><span class="sxs-lookup"><span data-stu-id="b4eac-112">**Backward Compatibility**</span></span>

<span data-ttu-id="b4eac-113">Lync Server 2013 можно интегрировать с Microsoft Exchange Server 2010 версии единой системы обмена сообщениями и Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-113">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="b4eac-114">Для получения дополнительных сведений ознакомьтесь со статьей развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2010 по адресу [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) .</span><span class="sxs-lookup"><span data-stu-id="b4eac-114">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="b4eac-115">Если вы интегрируетесь с Exchange 2010, у вас не будет специальных функций Lync Server, таких как единое хранилище контактов и архивация по Lync в Exchange.</span><span class="sxs-lookup"><span data-stu-id="b4eac-115">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="b4eac-116">Microsoft Lync 2013 также можно использовать вместе с Exchange 2010 и Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="b4eac-116">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="b4eac-117">Однако в этом случае новые функции, такие как единое хранилище контактов и фотографии с высоким разрешением, не будут доступны пользователям Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b4eac-117">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="b4eac-118">Для этих новых возможностей требуется как Lync Server 2013, так и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b4eac-118">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="b4eac-119">**Создание пула доверенных приложений для Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="b4eac-119">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="b4eac-120">Если вы установили службу маршрутизатора вызовов единой системы обмена сообщениями Microsoft Exchange и службу единой системы обмена сообщениями Microsoft Exchange на том же компьютере, вам не нужно создавать пул доверенных приложений для Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-120">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="b4eac-121">(Предполагается, что на рассматриваемом сервере размещена абонентская группа единой системы обмена сообщениями SipName.) Если вы используете один компьютер для размещения обеих этих служб, вы можете перейти к разделу этого документа под названием **Включение функции обмена мгновенными сообщениями в Outlook Web App**.</span><span class="sxs-lookup"><span data-stu-id="b4eac-121">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="b4eac-122">Lync Server 2013 может выполнить автообнаружение серверов Exchange, на которых размещается абонентская группа единой системы обмена сообщениями SipName; Эти серверы автоматически добавляются в список известных серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4eac-122">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="b4eac-123">Нет необходимости создавать пул доверенных приложений и добавлять эти серверы в список известных серверов.</span><span class="sxs-lookup"><span data-stu-id="b4eac-123">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="b4eac-124">На самом деле это приведет к прекращению работы интеграции Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-124">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b4eac-125">Это связано с тем, что в топологии Lync Server теперь есть две записи для одного и того же компьютера: автоматически обнаруженная запись и запись, добавленная вручную.</span><span class="sxs-lookup"><span data-stu-id="b4eac-125">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="b4eac-126">Чтобы устранить проблему и повторно запустить Outlook Web App, используйте Windows PowerShell для удаления доверенного пула и записей доверенных приложений для сервера.</span><span class="sxs-lookup"><span data-stu-id="b4eac-126">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="b4eac-127">Для получения дополнительных сведений ознакомьтесь со статьями справки для командлетов <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove – кструстедаппликатионпул</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove – кструстедаппликатион</A> .</span><span class="sxs-lookup"><span data-stu-id="b4eac-127">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="b4eac-128">Если эти две службы запущены на разных компьютерах, после проверки того, что установлена среда выполнения единой системы обмена сообщениями Managed API 4,0, необходимо создать пул доверенных приложений Lync Server и доверенное приложение, связанное с Outlook Web App; Это приведет к добавлению сервера в список известных серверов.</span><span class="sxs-lookup"><span data-stu-id="b4eac-128">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="b4eac-129">Для этого сначала выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b4eac-129">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="b4eac-130">В предыдущей команде atl-owa-001.litwareinc.com — полное доменное имя пула Outlook Web App; Это должно быть одно и то же имя, которое отображается в полях имя субъекта и альтернативное имя субъекта (SAN) сертификата, который предоставляет доступ к Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-130">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="b4eac-131">Аналогичным образом, atl-cs-001.litwareinc.com это полное доменное имя пула Lync Server 2013, в котором будет размещаться новый пул доверенных приложений.</span><span class="sxs-lookup"><span data-stu-id="b4eac-131">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="b4eac-132">Обратите внимание, что указанный сайт, Redmond, представляет сайт сайта Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4eac-132">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="b4eac-133">Имя сайта не обязательно должно совпадать с отображаемым именем сайта; Вы можете получить Ситеидс для сайтов Lync Server, выполнив следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b4eac-133">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="b4eac-134">После создания пула доверенных приложений используйте команду, аналогичную приведенной ниже, для настройки удостоверения приложения и порта для Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-134">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="b4eac-p110">В предыдущей команде значение ApplicationID являлось простым и понятным идентификатором, используемым для разграничения доверенных приложений. Значением ApplicationID может являться любая текстовая строка, которая не содержит пробелов и других запрещенных символов. (Чтобы создать допустимый идентификатор, при определении ApplicationId рекомендуется использовать только буквы и цифры.) Значение, назначенное параметру порта, также оставляется на выбор администратора; может использоваться любой доступный сетевой порт.</span><span class="sxs-lookup"><span data-stu-id="b4eac-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="b4eac-138">После создания доверенного приложения необходимо выполнить следующую команду, чтобы включить изменения в топологии Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b4eac-138">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="b4eac-139">Обратите внимание на то, что необходимо также добавить сервер клиентского доступа и почтовых ящиков Exchange во все абонентские группы URI SIP.</span><span class="sxs-lookup"><span data-stu-id="b4eac-139">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="b4eac-140">В свою очередь, эти серверы будут настроены как доверенные одноранговые узлы SIP с топологией ExUmRouting для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4eac-140">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="b4eac-141">**Включение обмена мгновенными сообщениями в Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="b4eac-141">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="b4eac-142">После правильной настройки Lync Server вы можете начать настройку Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-142">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="b4eac-143">Первый этап этого процесса состоит в том, чтобы включить обмен мгновенными сообщениями для всех виртуальных каталогов Outlook Web App на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="b4eac-143">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="b4eac-144">(Нет необходимости включать обмен мгновенными сообщениями для виртуальных каталогов на внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="b4eac-144">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="b4eac-145">На самом деле не рекомендуется включать обмен мгновенными сообщениями на внутренних серверах.) На серверах клиентского доступа можно включить обмен мгновенными сообщениями, выполнив в командной консоли Exchange следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4eac-145">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="b4eac-146">По умолчанию при установке Outlook Web App включен обмен мгновенными сообщениями; то есть свойство InstantMessagingEnabled имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="b4eac-146">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="b4eac-147">Тем не менее необходимо выполнить предыдущую команду, чтобы установить для типа обмена мгновенными сообщениями значение OCS.</span><span class="sxs-lookup"><span data-stu-id="b4eac-147">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="b4eac-148">По умолчанию для Инстантмессагингтипе задано значение None.</span><span class="sxs-lookup"><span data-stu-id="b4eac-148">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="b4eac-149">Затем необходимо добавить следующие две строки в файл Web.config Outlook Web App (этот файл обычно находится в папке C: \\ Program Files \\ Microsoft \\ Exchange Server \\ V15 \\ ClientAccess \\ OWA).</span><span class="sxs-lookup"><span data-stu-id="b4eac-149">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="b4eac-150">Эти две строки следует добавить в \<AppSettings\> узел файла Web.config, и эта процедура должна выполняться только на внутренних серверах, где установлено приложение Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="b4eac-150">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="b4eac-151">В предыдущем примере значение параметра Имцертификатесумбпринт должно быть отпечатком для сертификата Exchange 2013, установленного на внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="b4eac-151">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="b4eac-152">Вы можете получить эти сведения, выполнив следующую команду в командной консоли Exchange:</span><span class="sxs-lookup"><span data-stu-id="b4eac-152">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="b4eac-153">Обратите внимание, что значение, назначенное для ServerName, является полным доменным именем пула Lync Server, в котором вы создали пул доверенных приложений для Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-153">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="b4eac-154">Сертификат, используемый для Outlook Web App, должен быть сертификатом, который является доверенным для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4eac-154">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="b4eac-155">Один из способов удостовериться, что сертификат будет доверенным для Lync Server и Exchange, — использовать свой внутренний центр сертификации для создания сертификата на сервере почтовых ящиков, убедившись, что полное доменное имя сервера используется для имени субъекта и отображается в поле альтернативное имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="b4eac-155">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="b4eac-156">После создания сертификата его можно импортировать на внутренние серверы.</span><span class="sxs-lookup"><span data-stu-id="b4eac-156">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="b4eac-157">В итоге это тот же сертификат, который используется для двух целей: 1) для обмена данными между единой системой обмена сообщениями Exchange и Lync Server; и 2) интеграция между Outlook Web App и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4eac-157">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="b4eac-158">После того как вы обновите файл Web.config, выполните следующую команду на внутреннем сервере Exchange, чтобы перезапустить пул Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="b4eac-158">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="b4eac-159">Если операция перезапуска успешно выполнена, в командной консоли Exchange появится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="b4eac-159">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="b4eac-160">**Настройка политик почтовых ящиков Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="b4eac-160">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="b4eac-161">На этом шаге можно использовать следующую команду для настройки обмена мгновенными сообщениями в соответствующей политике почтовых ящиков Outlook Web App (или политиках).</span><span class="sxs-lookup"><span data-stu-id="b4eac-161">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="b4eac-162">Например, эта команда запускается на одном из серверов почтовых ящиков и включает обмен мгновенными сообщениями в политике по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="b4eac-162">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="b4eac-163">Эта команда включает обмен мгновенными сообщениями для всех политик почтовых ящиков Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-163">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="b4eac-164">После включения политики почтовых ящиков все пользователи, которым управляет эта политика, будут иметь полную интеграцию между Lync Server и Outlook Web App при условии, что:</span><span class="sxs-lookup"><span data-stu-id="b4eac-164">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="b4eac-165">У пользователя есть почтовый ящик в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b4eac-165">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="b4eac-166">Для пользователя включена поддержка Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b4eac-166">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="b4eac-167">Пользователь имеет допустимый прокси-адрес SIP.</span><span class="sxs-lookup"><span data-stu-id="b4eac-167">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="b4eac-168">**Отключение обмена мгновенными сообщениями в Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="b4eac-168">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="b4eac-169">Как отмечалось ранее, Обмен мгновенными сообщениями по умолчанию включен в Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-169">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="b4eac-170">Это означает, что если вы не интегрирует Outlook Web App с Lync Server, пользователи увидят пустые значки присутствия и сообщение об ошибке каждый раз при входе в Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-170">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="b4eac-171">Чтобы предотвратить эту проблему, используйте следующую команду командной консоли Exchange для отключения обмена мгновенными сообщениями в Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="b4eac-171">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="b4eac-172">**Проверка интеграции с Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="b4eac-172">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="b4eac-173">Чтобы убедиться, что обмен мгновенными сообщениями и сведения о присутствии интегрированы с Outlook Web App, войдите в Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="b4eac-173">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="b4eac-174">В верхнем правом углу экрана отображается отображаемое имя Exchange.</span><span class="sxs-lookup"><span data-stu-id="b4eac-174">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="b4eac-175">Если рядом с именем есть значок присутствия (например, зеленый значок, указывающий на то, что текущее состояние доступно), что означает, что вы успешно интегрируете Lync Server и Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="b4eac-175">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="b4eac-176">После первого входа в Outlook Web App проверьте, записано ли в журнал событий на сервере почтовых ящиков событие с ИДЕНТИФИКАТОРом 112 (и исходным MSExchange OWA).</span><span class="sxs-lookup"><span data-stu-id="b4eac-176">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="b4eac-177">Это событие указывает на то, что диспетчер конечной точки обмена мгновенными сообщениями успешно инициализирован.</span><span class="sxs-lookup"><span data-stu-id="b4eac-177">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="b4eac-178">Если обмен мгновенными сообщениями не работает, то на сервере почтовых ящиков найдите файлы журнала в папке C: \\ Program Files \\ Microsoft \\ Exchange Server \\ V15 \\ Logging \\ инстантмессагинг для OWA \\ .</span><span class="sxs-lookup"><span data-stu-id="b4eac-178">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="b4eac-179">Если папки "журнал" или "Инстантмессагинг" не существуют, что свидетельствует о неудачной интеграции.</span><span class="sxs-lookup"><span data-stu-id="b4eac-179">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="b4eac-180">В этом случае вы можете использовать трассировку SIPStack на Lync Server (все уровни и все флажки), чтобы проверить, почему не удалось выполнить интеграцию.</span><span class="sxs-lookup"><span data-stu-id="b4eac-180">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

