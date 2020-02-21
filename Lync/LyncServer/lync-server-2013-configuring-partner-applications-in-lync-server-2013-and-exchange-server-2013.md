---
title: Настройка партнерских приложений в Lync Server 2013 и Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db2f0df542cb85956ae3efa7321083b99ed561a8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="88a57-102">Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a57-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88a57-103">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="88a57-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="88a57-p101">В проверке подлинности "сервер-сервер" обычно участвуют три объекта: два сервера, которые должны обмениваться данными, и сторонний сервер маркеров безопасности. Если двум серверам (например, серверу A и серверу B) необходимо обмениваться данными, оба сервера обычно начинают с обращения к серверу маркеров и получения взаимно доверенного маркера безопасности. Затем сервер A отправляет этот маркер безопасности серверу B (и наоборот) в качестве гарантии своей подлинности и надежности.</span><span class="sxs-lookup"><span data-stu-id="88a57-p101">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server. If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token. Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="88a57-107">Однако это общее правило.</span><span class="sxs-lookup"><span data-stu-id="88a57-107">However, that's a general rule.</span></span> <span data-ttu-id="88a57-108">Lync Server 2013, Microsoft Exchange Server 2013 и Microsoft SharePoint Server 2013 не требуется использовать сторонний сервер маркеров при взаимодействии друг с другом; Это связано с тем, что эти серверные продукты могут создавать маркеры безопасности, которые могут приниматься друг друга без необходимости использования отдельного сервера маркеров.</span><span class="sxs-lookup"><span data-stu-id="88a57-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="88a57-109">(Эта возможность доступна только в Lync Server 2013, Exchange 2013 и SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88a57-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="88a57-110">Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Майкрософт, потребуется использование стороннего сервера маркеров.</span><span class="sxs-lookup"><span data-stu-id="88a57-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="88a57-111">Для настройки межсерверной проверки подлинности между Lync Server и Exchange необходимо выполнить два действия: 1) необходимо назначить соответствующие сертификаты каждому серверу; и 2) необходимо настроить для каждого сервера партнерское приложение другого сервера: это означает, что необходимо настроить Lync Server 2013 как партнерское приложение для Exchange 2013, а Exchange 2013 — партнерское приложение для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88a57-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="88a57-112">Настройка Lync Server 2013 в качестве партнерского приложения для Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="88a57-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="88a57-113">Самый простой способ настроить Lync Server 2013 в качестве партнерского приложения с Exchange 2013 — запустить сценарий сценарий configure-enterprisepartnerapplication. ps1, сценарий Windows PowerShell, поставляемый с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="88a57-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="88a57-114">Для запуска этого сценария необходимо указать URL-адрес документа метаданных проверки подлинности Lync Server; как правило, это полное доменное имя пула Lync Server 2013, за которым следует суффикс/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="88a57-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="88a57-115">Например:</span><span class="sxs-lookup"><span data-stu-id="88a57-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="88a57-116">Чтобы настроить Lync Server в качестве партнерского приложения, откройте командную консоль Exchange и выполните команду, аналогичную следующей, при условии, что Exchange установлен на диске C: и используется путь к папке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88a57-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="88a57-117">После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на серверах почтовых ящиков Exchange и клиентского доступа.</span><span class="sxs-lookup"><span data-stu-id="88a57-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="88a57-118">Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="88a57-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="88a57-119">Эту команду можно выполнить в командной консоли Exchange или в любом другом командном окне, которое запускается с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="88a57-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="88a57-120">Настройка Exchange 2013 в качестве партнерского приложения для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a57-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="88a57-121">После настройки Lync Server 2013 в качестве партнерского приложения для Exchange 2013 необходимо настроить Exchange в качестве партнерского приложения для Lync Server.</span><span class="sxs-lookup"><span data-stu-id="88a57-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="88a57-122">Это можно сделать с помощью командной консоли Lync Server и указав документ метаданных проверки подлинности для Exchange. как правило, это универсальный код ресурса (URI) службы автообнаружения Exchange, за которым следует суффикс/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="88a57-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="88a57-123">Например:</span><span class="sxs-lookup"><span data-stu-id="88a57-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="88a57-124">В Lync Server партнерские приложения настраиваются с помощью командлета [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="88a57-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="88a57-125">В дополнение к указанию URI метаданных необходимо также установить полное значение уровня доверия для приложения; Это позволит Exchange предоставлять как самого себя, так и любого уполномоченного пользователя в сфере.</span><span class="sxs-lookup"><span data-stu-id="88a57-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="88a57-126">Например:</span><span class="sxs-lookup"><span data-stu-id="88a57-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="88a57-127">Кроме того, вы можете создать партнерское приложение, скопировав и изменив код скрипта, который находится в документации по проверке подлинности "сервер-сервер" в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="88a57-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="88a57-128">Для получения дополнительных сведений ознакомьтесь со статьей [Управление межсерверной проверкой подлинности (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="88a57-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="88a57-129">Если вы успешно настроили партнерские приложения для Lync Server и Exchange, это означает, что вы успешно настроили межсерверную проверку подлинности между двумя продуктами.</span><span class="sxs-lookup"><span data-stu-id="88a57-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="88a57-130">Lync Server 2013 включает командлет Windows PowerShell [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), который позволяет убедиться, что проверка подлинности между серверами настроена правильно и служба хранилища Lync Server может подключаться к Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="88a57-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="88a57-131">Это выполняется командлетом, подключаясь к почтовому ящику пользователя Exchange 2013, записывая элемент в папку журнала бесед для этого пользователя, а затем (необязательно) удаление этого элемента.</span><span class="sxs-lookup"><span data-stu-id="88a57-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="88a57-132">Чтобы протестировать интеграцию Lync Server 2013 и Exchange 2013, выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="88a57-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="88a57-133">В предыдущей команде Сипури представляет SIP адрес пользователя с учетной записью в Exchange 2013; команда не будет работать, так как она не является допустимой учетной записью пользователя.</span><span class="sxs-lookup"><span data-stu-id="88a57-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="88a57-134">Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.</span><span class="sxs-lookup"><span data-stu-id="88a57-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

