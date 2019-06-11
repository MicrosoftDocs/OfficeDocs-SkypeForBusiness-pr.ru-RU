---
title: Настройка партнерских приложений в Lync Server 2013 и Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="29fab-102">Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="29fab-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29fab-103">_**Тема последнего изменения:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="29fab-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="29fab-104">Проверка подлинности "сервер-сервер" обычно включает три сущности: два сервера, которые должны взаимодействовать друг с другом, и сторонний сервер маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="29fab-104">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="29fab-105">Если на двух серверах (например, сервер A и B) требуется связь, то оба эти сервера обычно начинаются с того, чтобы они получали доступ к серверу-маркеру и получили взаимно доверенный маркер безопасности.</span><span class="sxs-lookup"><span data-stu-id="29fab-105">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="29fab-106">Сервер а затем представляет маркер безопасности для сервера B (и наоборот), чтобы гарантировать как его подлинность, так и его надежность.</span><span class="sxs-lookup"><span data-stu-id="29fab-106">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="29fab-107">Однако это общее правило.</span><span class="sxs-lookup"><span data-stu-id="29fab-107">However, that's a general rule.</span></span> <span data-ttu-id="29fab-108">Lync Server 2013, Microsoft Exchange Server 2013 и Microsoft SharePoint Server 2013 не требуется использовать сторонний сервер маркеров при взаимодействии друг с другом. Это может быть вызвано тем, что эти серверные продукты могут создавать маркеры безопасности, которые могут принимать друг друга, без необходимости использования отдельного сервера маркеров.</span><span class="sxs-lookup"><span data-stu-id="29fab-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="29fab-109">(Эта возможность доступна только в Lync Server 2013, Exchange 2013 и SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29fab-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="29fab-110">Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Microsoft, потребуется использование стороннего сервера маркеров.)</span><span class="sxs-lookup"><span data-stu-id="29fab-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="29fab-111">Для настройки проверки подлинности между сервером Lync Server и Exchange необходимо выполнить два действия: 1) необходимо назначить каждому серверу соответствующие сертификаты. и 2) необходимо настроить каждый сервер как приложение-партнер для другого сервера: это означает, что необходимо настроить Lync Server 2013 таким образом, чтобы он был партнерским приложением для Exchange 2013, и необходимо настроить Exchange 2013 как приложение-партнер для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29fab-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="29fab-112">Настройка сервера Lync Server 2013 в качестве партнерской программы для Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="29fab-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="29fab-113">Самый простой способ настроить Lync Server 2013 для использования в качестве партнерского приложения с Exchange 2013 — запустить сценарий Конфигуре-ентерприсепартнераппликатион. ps1 — сценарий Windows PowerShell, который поставляется с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="29fab-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="29fab-114">Чтобы выполнить этот сценарий, необходимо указать URL-адрес для документа метаданных проверки подлинности в Lync Server; как правило, это полное доменное имя пула Lync Server 2013, за которым следует суффикс/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="29fab-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="29fab-115">Например:</span><span class="sxs-lookup"><span data-stu-id="29fab-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="29fab-116">Чтобы настроить сервер Lync Server как партнерское приложение, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и используется путь к папке по умолчанию):</span><span class="sxs-lookup"><span data-stu-id="29fab-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="29fab-117">После настройки приложения-партнера рекомендуется остановить и перезапустить службы IIS в почтовом ящике Exchange и на серверах клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="29fab-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="29fab-118">Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.</span><span class="sxs-lookup"><span data-stu-id="29fab-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="29fab-119">Эту команду можно выполнить в командной консоли Exchange или в любом другом окне команд, которое запускается с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="29fab-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="29fab-120">Настройка Exchange 2013 для приложения-партнера для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29fab-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="29fab-121">После того как вы настроили Lync Server 2013 в качестве партнера-приложения для Exchange 2013, необходимо настроить Exchange в качестве партнерского приложения для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="29fab-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="29fab-122">Это можно сделать, используя командную консоль Lync Server Management Shell и указав документ метаданных проверки подлинности для Exchange; как правило, это URI службы автообнаружения Exchange, за которой следует суффикс/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="29fab-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="29fab-123">Например:</span><span class="sxs-lookup"><span data-stu-id="29fab-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="29fab-124">В Lync Server приложения-партнеры настраиваются с помощью командлета [New-кспартнераппликатион](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="29fab-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="29fab-125">В дополнение к указанию URI метаданных необходимо также установить полный уровень доверия для приложения; Это позволит Exchange самостоятельно представлять себе и всех авторизованных пользователей в сфере.</span><span class="sxs-lookup"><span data-stu-id="29fab-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="29fab-126">Например:</span><span class="sxs-lookup"><span data-stu-id="29fab-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="29fab-127">Кроме того, вы можете создать партнерское приложение, скопировав и изменив код сценария, который находится в документации по проверке подлинности серверов в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="29fab-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="29fab-128">Дополнительные сведения можно найти [в статье Управление проверкой подлинности серверов (OAuth) и партнерских приложений в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="29fab-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="29fab-129">Если вы успешно настроили партнерские приложения для Lync Server и Exchange, это означает, что вы также успешно настроили проверку подлинности серверов и серверов между двумя продуктами.</span><span class="sxs-lookup"><span data-stu-id="29fab-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="29fab-130">Lync Server 2013 содержит командлет Windows PowerShell [Test-ксекссторажеконнективити](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), который позволяет проверить правильность настройки проверки подлинности серверов и сервера в службе хранилища Lync Server, которая может подключиться к Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="29fab-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="29fab-131">Командлет делает это, подключаясь к почтовому ящику пользователя Exchange 2013, записывая элемент в папку журнала бесед для этого пользователя и, при необходимости, удаляя его.</span><span class="sxs-lookup"><span data-stu-id="29fab-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="29fab-132">Чтобы протестировать интеграцию Lync Server 2013 и Exchange 2013, выполните в командной консоли Lync Server команду, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="29fab-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="29fab-133">В предыдущей команде Сипури представляет адрес SIP пользователя с учетной записью в Exchange 2013; не удается выполнить команду, так как она не является действительной учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="29fab-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="29fab-134">Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="29fab-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

