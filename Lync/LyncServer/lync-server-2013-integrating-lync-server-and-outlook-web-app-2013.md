---
title: 'Lync Server 2013: интеграция Lync Server и Outlook Web App 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31a25e1d0a6410171201af578d6b28f496468e06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="00899-102">Интеграция Microsoft Lync Server 2013 и Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="00899-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00899-103">_**Тема последнего изменения:** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="00899-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="00899-104">Помимо интеграции с Microsoft Outlook 2013, Microsoft Lync Server 2013 может быть полностью интегрирован с Microsoft Outlook Web App 2013. Помимо прочего, это позволяет добавить в Outlook Web App мгновенные сообщения и сведения о присутствии, а затем предоставить общий доступ к Объединенному списку контактов между Outlook Web App и Microsoft Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="00899-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="00899-105">Чтобы интегрировать Lync Server 2013 и Outlook Web App, необходимо сначала убедиться, что на внутреннем сервере Microsoft Exchange Server 2013 установлен интерфейс API единой системы обмена сообщениями 4,0.</span><span class="sxs-lookup"><span data-stu-id="00899-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="00899-106">Для этого достаточно проверить наличие следующего значения реестра:</span><span class="sxs-lookup"><span data-stu-id="00899-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="00899-107">Система\_\\hKey\_для\\локального компьютера\\куррентконтролсет\\Services мсексчанже\\OWA\\инстантмессагинг имплементатиондллпас</span><span class="sxs-lookup"><span data-stu-id="00899-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="00899-108">Значение ImplementationDLLPath должно указывать расположение папки с файлом Microsoft.Rtc.Internal.Ucweb.dll.</span><span class="sxs-lookup"><span data-stu-id="00899-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="00899-109">Если это не так или значение реестра не существует, необходимо скачать и установить программу установки среды выполнения УКМА из центра загрузки Майкрософт по адресу <http://www.microsoft.com/en-us/download/details.aspx?id=34992>.</span><span class="sxs-lookup"><span data-stu-id="00899-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <http://www.microsoft.com/en-us/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="00899-110">Инструкции по установке среды выполнения UCMA приведены на той же веб-странице.</span><span class="sxs-lookup"><span data-stu-id="00899-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="00899-111">**Обратная совместимость**</span><span class="sxs-lookup"><span data-stu-id="00899-111">**Backward Compatibility**</span></span>

<span data-ttu-id="00899-112">Lync Server 2013 можно интегрировать с версиями единой системы обмена сообщениями и Outlook Web App в Microsoft Exchange Server 2010.</span><span class="sxs-lookup"><span data-stu-id="00899-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="00899-113">Дополнительные сведения можно найти в статье Развертывание локальной единой системы обмена сообщениями Exchange для предоставления голосовой почты Lync Server 2010 [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)по адресу.</span><span class="sxs-lookup"><span data-stu-id="00899-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="00899-114">Если вы интегрируется с Exchange 2010, у вас нет специфических функций Lync Server, таких как единое хранилище контактов и архивирование из Lync в Exchange.</span><span class="sxs-lookup"><span data-stu-id="00899-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="00899-115">Microsoft Lync 2013 также можно использовать в сочетании с Exchange 2010 и Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="00899-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="00899-116">Тем не менее, новые функции, такие как единое хранилище контактов и фотографии высокого разрешения, не будут доступны для пользователей Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="00899-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="00899-117">Для этих новых возможностей требуется как Lync Server 2013, так и Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="00899-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="00899-118">**Создание пула доверенных приложений для Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="00899-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="00899-119">Если вы установили службу маршрутизатора для единой системы обмена сообщениями Microsoft Exchange и служба единой системы обмена сообщениями Microsoft Exchange на том же компьютере, вам не нужно создавать доверенную группу приложений для Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="00899-120">(Предполагается, что на сервере размещается абонентская группа Сипнаме UM). Если вы используете один компьютер для размещения обоих этих служб, вы можете перейти к разделу этого документа с названием **Включение функции обмена мгновенными сообщениями в Outlook Web App**.</span><span class="sxs-lookup"><span data-stu-id="00899-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="00899-121">Lync Server 2013 может выключать любые серверы Exchange, на которых размещена абонентская группа UM Сипнаме; Эти серверы автоматически добавляются в список известных серверов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00899-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="00899-122">Создавать пул доверенных приложений и добавлять эти серверы к списку известных серверов вручную не требуется.</span><span class="sxs-lookup"><span data-stu-id="00899-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="00899-123">Более того, такие действия приводят к нарушению взаимодействия с Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00899-124">Это обусловлено тем, что топология Lync Server теперь содержит две записи для одного и того же компьютера: автоматически обнаруживаемый элемент и добавленный вручную элемент.</span><span class="sxs-lookup"><span data-stu-id="00899-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="00899-125">Для устранения неполадки и восстановления работоспособности Outlook Web App следует с помощью Windows PowerShell удалить доверенный пул и записи доверенных приложений для этого сервера.</span><span class="sxs-lookup"><span data-stu-id="00899-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="00899-126">Дополнительные сведения см. в разделах справки по командлетам <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A>.</span><span class="sxs-lookup"><span data-stu-id="00899-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="00899-127">Если эти две службы запущены на разных компьютерах, после того как вы убедитесь в том, что на компьютере установлено приложение интегрированной среды выполнения API 4,0, необходимо создать доверенный пул приложений Lync Server и доверенное приложение, связанное с Outlook Web App; будет добавлен сервер в список известных серверов.</span><span class="sxs-lookup"><span data-stu-id="00899-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="00899-128">Для этого сначала выполните в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="00899-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="00899-129">В приведенной выше команде atl-owa-001.litwareinc.com — полное доменное имя пула Outlook Web App; это же имя должно отображаться в полях имени субъекта и альтернативного имени субъекта (SAN) сертификата, обеспечивающего доступ к Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="00899-130">Точно так же atl-cs-001.litwareinc.com — это полное доменное имя пула Lync Server 2013, на котором будет размещен новый доверенный пул приложений.</span><span class="sxs-lookup"><span data-stu-id="00899-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="00899-131">Обратите внимание, что указанный сайт "Redmond" представляет сайт сайта Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00899-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="00899-132">Идентификатор сайта — это не обязательно тот же отображаемый элемент; Вы можете получить Ситеидс для сайтов Lync Server, выполнив в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="00899-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="00899-133">После создания пула доверенных приложений используйте команду, аналогичную приведенной ниже, для настройки удостоверения приложения и порта для Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="00899-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="00899-p110">В предыдущей команде значение ApplicationID являлось простым и понятным идентификатором, используемым для разграничения доверенных приложений. Значением ApplicationID может являться любая текстовая строка, которая не содержит пробелов и других запрещенных символов. (Чтобы создать допустимый идентификатор, при определении ApplicationId рекомендуется использовать только буквы и цифры.) Значение, назначенное параметру порта, также оставляется на выбор администратора; может использоваться любой доступный сетевой порт.</span><span class="sxs-lookup"><span data-stu-id="00899-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="00899-137">После создания надежного приложения необходимо выполнить следующую команду, чтобы включить изменения в топологии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00899-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="00899-138">Обратите внимание, что необходимо также добавить сервер клиентского доступа и почтового ящика ко всем абонентам SIP URI.</span><span class="sxs-lookup"><span data-stu-id="00899-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="00899-139">В свою очередь, они будут настраивать серверы как доверенные одноранговые модули SIP с помощью топологии Ексумраутинг для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00899-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="00899-140">**Включение обмена мгновенными сообщениями в Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="00899-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="00899-141">После правильной настройки Lync Server вы можете приступить к настройке Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="00899-142">Первый этап этого процесса — включить обмен мгновенными сообщениями во всех виртуальных каталогах Outlook Web App на серверах переднего плана.</span><span class="sxs-lookup"><span data-stu-id="00899-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="00899-143">(Не нужно включать обмен мгновенными сообщениями для виртуальных каталогов на внутренних серверах.</span><span class="sxs-lookup"><span data-stu-id="00899-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="00899-144">На самом деле не рекомендуется включать функцию обмена мгновенными сообщениями на внутренних серверах.) Вы можете включить функцию обмена мгновенными сообщениями на серверах клиентского доступа, выполнив следующую команду в командной консоли Exchange:</span><span class="sxs-lookup"><span data-stu-id="00899-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="00899-p113">По умолчанию обмен мгновенными сообщениями включается при установке Outlook Web App, то есть когда для свойства InstantMessagingEnabled задается значение True. Однако вам все равно следует выполнить предыдущую команду, чтобы установить для обмена мгновенными сообщениями тип OCS. По умолчанию для InstantMessagingType установлено значение None.</span><span class="sxs-lookup"><span data-stu-id="00899-p113">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True. However, you must still run the preceding command in order to set the instant messaging type to OCS. By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="00899-148">Затем вы должны добавить следующие две строки в файл Outlook Web App Web. config (этот файл обычно находится в\\папке C: Program Files\\Microsoft\\Exchange Server\\V15\\клиентакцесс\\OWA).</span><span class="sxs-lookup"><span data-stu-id="00899-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="00899-149">Эти две строки нужно добавить под узлом \<appSettings\> в файле Web. config, и эта процедура должна выполняться только на внутренних серверах, где установлено приложение Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="00899-150">В предыдущем примере значение параметра Имцертификатесумбпринт должно представлять собой отпечаток сертификата Exchange 2013, установленного на серверных серверах.</span><span class="sxs-lookup"><span data-stu-id="00899-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="00899-151">Вы можете получить эти сведения, выполнив следующую команду в командной консоли Exchange:</span><span class="sxs-lookup"><span data-stu-id="00899-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="00899-152">Обратите внимание, что значение, присвоенное параметру ServerName, — это полное доменное имя пула Lync Server, в котором вы создали доверенный пул приложений для Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="00899-153">Сертификат, используемый для Outlook Web App, должен быть сертификатом, который является надежным для сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00899-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="00899-154">Один из способов удостовериться, что сертификат будет надежно установлен как в Lync Server, так и в Exchange, — использовать внутренний центр сертификации для создания сертификата на сервере почтовых ящиков, что гарантирует использование полного доменного имени сервера и его полное доменное имя в t поле альтернативное имя сертификата.</span><span class="sxs-lookup"><span data-stu-id="00899-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="00899-155">После создания сертификата его можно импортировать на внутренние серверы.</span><span class="sxs-lookup"><span data-stu-id="00899-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="00899-156">Конечный результат состоит в том, что один и тот же сертификат используется в двух целях: 1) обмен данными между единой системой обмена сообщениями Exchange и Lync Server; и 2) интеграция между Outlook Web App и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="00899-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="00899-157">После обновления файла Web. config для перезапуска пула Outlook Web App необходимо выполнить следующую команду на сервере внутреннего сервера Exchange:</span><span class="sxs-lookup"><span data-stu-id="00899-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="00899-158">Если операция перезапуска была выполнена успешно, в командной консоли Exchange появится следующее сообщение:</span><span class="sxs-lookup"><span data-stu-id="00899-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="00899-159">**Настройка политик почтовых ящиков Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="00899-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="00899-p117">На этом этапе можно использовать приведенную ниже команду в целях настройки обмена мгновенными сообщениями посредством подходящей политики почтовых ящиков (или нескольких таких политик) Outlook Web App. Например, при запуске на одном из серверов почтовых ящиков данная команда включает обмен мгновенными сообщениями для политики по умолчанию:</span><span class="sxs-lookup"><span data-stu-id="00899-p117">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies). For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="00899-162">А эта команда включает обмен мгновенными сообщениями для всех политик почтовых ящиков Outlook Web App:</span><span class="sxs-lookup"><span data-stu-id="00899-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="00899-163">После включения политики почтовых ящиков все пользователи, которым управляет эта политика, получат полную интеграцию между Lync Server и Outlook Web App, при условии что:</span><span class="sxs-lookup"><span data-stu-id="00899-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="00899-164">У пользователя есть почтовый ящик в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="00899-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="00899-165">У пользователя установлен сервер Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="00899-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="00899-166">Пользователь имеет допустимый прокси-адрес SIP.</span><span class="sxs-lookup"><span data-stu-id="00899-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="00899-167">**Отключение обмена мгновенными сообщениями в Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="00899-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="00899-168">Как было отмечено ранее, по умолчанию в Outlook Web App включен обмен мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="00899-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="00899-169">Это означает, что если вы не интегрирует Outlook Web App с Lync Server, пользователи увидят пустой значок присутствия и сообщение об ошибке при каждом входе в Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="00899-170">Чтобы избежать этой проблемы, используйте следующую команду командной консоли Exchange, чтобы отключить функцию обмена мгновенными сообщениями в Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="00899-171">**Проверка интеграции с Outlook Web App**</span><span class="sxs-lookup"><span data-stu-id="00899-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="00899-172">Для проверки интеграции обмена мгновенными сообщениями и индикации присутствия с Outlook Web App войдите в Outlook Web App 2013.</span><span class="sxs-lookup"><span data-stu-id="00899-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="00899-173">В правом верхнем углу экрана появляется отображаемое имя Exchange.</span><span class="sxs-lookup"><span data-stu-id="00899-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="00899-174">Если рядом с вашим именем есть значок присутствия (например, зеленый значок, указывающий на то, что ваше текущее состояние доступно), указывающий на то, что вы успешно интегрированы с Lync Server и Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="00899-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="00899-175">После первого входа в Outlook Web App проверьте, записано ли событие с идентификатором 112 (и исходное событие MSExchange OWA) в журнал событий на сервере почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="00899-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="00899-176">Это событие указывает на успешную инициализацию диспетчера конечных точек обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="00899-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="00899-177">Если обмен мгновенными сообщениями не работает, то на сервере почтовых ящиков найдите файлы журнала в папке\\C: Program Files\\Microsoft\\Exchange Server\\V15\\ведения\\журнала\\OWA инстантмессагинг.</span><span class="sxs-lookup"><span data-stu-id="00899-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="00899-178">Если папка Logging или InstantMessaging отсутствует, интеграция не настроена.</span><span class="sxs-lookup"><span data-stu-id="00899-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="00899-179">В этом случае вы можете использовать трассировку Сипстакк на Lync Server (все уровни и все флаги), чтобы проверить, почему интеграция завершилась сбоем.</span><span class="sxs-lookup"><span data-stu-id="00899-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

