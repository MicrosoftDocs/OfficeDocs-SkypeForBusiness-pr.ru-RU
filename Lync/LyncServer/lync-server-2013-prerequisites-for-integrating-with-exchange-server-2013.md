---
title: 'Lync Server 2013: необходимые условия для интеграции с Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ea70be8c4d431b6231b1cf8e8dc252581643b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="4e018-102">Необходимые условия для интеграции Microsoft Lync Server 2013 и Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e018-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e018-103">_**Последнее изменение темы:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="4e018-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="4e018-104">Перед интеграцией Microsoft Lync Server 2013 и Microsoft Exchange Server 2013 необходимо убедиться, что все необходимые действия выполнены.</span><span class="sxs-lookup"><span data-stu-id="4e018-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="4e018-105">Как вы можете ожидать, интеграция не может быть выполнена, пока не будут полностью установлены и запущены Exchange 2013 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4e018-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="4e018-106">Более подробную информацию об установке Exchange можно найти в документации по планированию и [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539)развертыванию Exchange 2013 на сайте.</span><span class="sxs-lookup"><span data-stu-id="4e018-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="4e018-107">Подробные сведения об установке Lync Server 2013 можно найти в документации по планированию и [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806)развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4e018-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="4e018-108">После установки и запуска серверов необходимо назначить сертификаты проверки подлинности "сервер – сервер" для Lync Server 2013 и Exchange 2013. Эти сертификаты позволяют Lync Server и Exchange обмениваться информацией и общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="4e018-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="4e018-109">При установке Exchange 2013 создается самозаверяющий сертификат с именем сертификата проверки подлинности Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="4e018-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="4e018-110">Этот сертификат, который можно найти в хранилище сертификатов локального компьютера, должен использоваться для межсерверной проверки подлинности на сервере Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4e018-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="4e018-111">Подробные сведения о назначении сертификатов в Exchange 2013 приведены в [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540)разделе "Настройка почтового ящика и клиентского доступа".</span><span class="sxs-lookup"><span data-stu-id="4e018-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="4e018-112">Для Lync Server 2013 вы можете использовать существующий сертификат Lync Server в качестве сертификата проверки подлинности "сервер – сервер"; Например, сертификат по умолчанию также можно использовать в качестве сертификата OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="4e018-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="4e018-113">Lync Server 2013 позволяет использовать любой сертификат веб-сервера в качестве сертификата для проверки подлинности "сервер-сервер" при условии, что:</span><span class="sxs-lookup"><span data-stu-id="4e018-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="4e018-114">этот сертификат содержит имя домена SIP в поле "Тема";</span><span class="sxs-lookup"><span data-stu-id="4e018-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="4e018-115">тот же сертификат настроен как сертификат OAuthTokenIssuer на всех интерфейсных серверах;</span><span class="sxs-lookup"><span data-stu-id="4e018-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="4e018-116">длина сертификата составляет не менее 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="4e018-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="4e018-117">Сведения о сертификатах проверки подлинности "сервер – сервер" для Microsoft Lync Server 2013 приведены в [статье назначение сертификата проверки подлинности между серверами в Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="4e018-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="4e018-118">После назначения сертификатов необходимо настроить службу автообнаружения в Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4e018-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="4e018-119">В Exchange 2013 служба автообнаружения настраивает профили пользователей и предоставляет доступ к службам Exchange при входе пользователей в систему.</span><span class="sxs-lookup"><span data-stu-id="4e018-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="4e018-120">Пользователи предоставляют службе автообнаружения свой адрес электронной почты и пароль; в свою очередь службы предоставляют пользователю следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="4e018-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="4e018-121">Сведения о подключении как для внутреннего, так и для внешнего подключения к Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="4e018-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="4e018-122">расположение сервера почтовых ящиков пользователя;</span><span class="sxs-lookup"><span data-stu-id="4e018-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="4e018-123">URL-адреса для компонентов Outlook, таких как сведения о доступности, единой системе обмена сообщениями, а также автономной адресной книге;</span><span class="sxs-lookup"><span data-stu-id="4e018-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="4e018-124">параметры сервера мобильного Outlook.</span><span class="sxs-lookup"><span data-stu-id="4e018-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="4e018-125">Для интеграции Lync Server 2013 и Exchange 2013 необходимо настроить службу автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="4e018-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="4e018-126">Вы можете проверить, настроена ли служба автообнаружения, выполнив следующую команду в командной консоли Exchange и проверив значение свойства AutoDiscoverServiceInternalUri:</span><span class="sxs-lookup"><span data-stu-id="4e018-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="4e018-p106">Если это значение пусто, необходимо назначить URI службе автообнаружения. Обычно этот URI выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4e018-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="4e018-129">URI автообнаружения можно назначить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="4e018-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="4e018-130">Подробные сведения о службе автообнаружения содержатся в [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542)разделе "Общие сведения о службе автообнаружения".</span><span class="sxs-lookup"><span data-stu-id="4e018-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="4e018-131">После настройки службы автообнаружения необходимо изменить параметры конфигурации OAuth для Lync Server; Это гарантирует, что Lync Server будет знать, где найти службу автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="4e018-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="4e018-132">Чтобы изменить параметры конфигурации OAuth в Lync Server 2013, выполните следующую команду в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4e018-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="4e018-133">При выполнении этой команды необходимо указать универсальный код ресурса (URI) для службы автообнаружения, запущенной на сервере Exchange Server, и использовать функцию **автообнаружения. svc** для указания расположения службы вместо **автообнаружения. XML** (указывает на XML-файл, используемый службой):</span><span class="sxs-lookup"><span data-stu-id="4e018-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="4e018-134">Параметр Identity в предыдущей команде является необязательным; Это связано с тем, что Lync Server позволяет использовать только одну глобальную коллекцию параметров конфигурации OAuth.</span><span class="sxs-lookup"><span data-stu-id="4e018-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="4e018-135">Помимо прочего, это означает, что вы можете настроить URL-адрес автообнаружения, используя немного более простую команду:</span><span class="sxs-lookup"><span data-stu-id="4e018-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="4e018-136">Set-CsOAuthConfiguration – Ексчанжеаутодисковерурл "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="4e018-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="4e018-p109">Если вы не знакомы с этой технологией, OAuth — это стандартный протокол авторизации, который применяется на различных крупных веб-сайтах. При использовании OAuth учетные данные и пароли пользователей не переносятся с одного компьютера на другой. Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="4e018-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="4e018-140">В дополнение к настройке службы автообнаружения необходимо также создать запись DNS для службы, указывающей на сервер Exchange.</span><span class="sxs-lookup"><span data-stu-id="4e018-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="4e018-141">Например, если служба автообнаружения расположена по адресу autodiscover.litwareinc.com, необходимо создать запись DNS для autodiscover.litwareinc.com, которая разрешается в полное доменное имя сервера Exchange (например, atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="4e018-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

