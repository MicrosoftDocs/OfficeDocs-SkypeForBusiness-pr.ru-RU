---
title: Управление проверкой подлинности серверов (OAuth) и приложениями-партнерами
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="cbf75-102">Управление проверкой подлинности между сервером (OAuth) и приложениями-партнерами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbf75-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf75-103">_**Тема последнего изменения:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="cbf75-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="cbf75-104">Microsoft Lync Server 2013 должен обеспечивать надежную и беспроблемную связь с другими приложениями и серверными продуктами.</span><span class="sxs-lookup"><span data-stu-id="cbf75-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="cbf75-105">Например, вы можете настроить Lync Server 2013 таким образом, чтобы данные контактных данных и (или) данные архивации хранились в Microsoft Exchange Server 2013; Тем не менее, это можно сделать только в том случае, если Lync Server и Exchange могут безопасно взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="cbf75-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="cbf75-106">Кроме того, вы можете запланировать Конференц-связь с Lync Server в Microsoft SharePoint Server. Тем не менее, это можно сделать только в том случае, если два сервера (SharePoint и Lync Server) доверяют друг другу.</span><span class="sxs-lookup"><span data-stu-id="cbf75-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="cbf75-107">Несмотря на то, что вы можете использовать один механизм проверки подлинности для обмена данными между Lync и Exchange и отдельный механизм для обмена информацией между Lync и SharePoint, лучше и эффективнее использовать стандартный метод для всех серверных серверов Проверка подлинности и авторизация.</span><span class="sxs-lookup"><span data-stu-id="cbf75-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="cbf75-108">Использование единого стандартного метода для проверки подлинности между сервером — это подход, который выйдет Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbf75-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="cbf75-109">В выпуске 2013 Lync Server 2013 (а также другие серверные продукты Майкрософт, в том числе Exchange 2013 и Microsoft SharePoint Server) поддерживают протокол OAuth (открытая авторизация) для проверки подлинности и авторизации сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="cbf75-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="cbf75-110">С помощью OAuth стандартным протоколом авторизации, используемым для ряда основных сайтов, учетные данные пользователя и пароли не передаются с одного компьютера на другой.</span><span class="sxs-lookup"><span data-stu-id="cbf75-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="cbf75-111">Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="cbf75-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="cbf75-112">Как правило, проверка подлинность OAuth включает три компонента: отдельный сервер авторизации и две области, которые должны взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="cbf75-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="cbf75-113">(Кроме того, можно выполнить проверку подлинности "сервер-сервер" без использования сервера авторизации — процесс, который будет обсуждаться ниже в этом документе.) Маркеры безопасности выдаются сервером авторизации (также называемым сервером маркеров безопасности) в две сферы, которые должны поддерживать связь; Эти маркеры проверки того, что связь, исходящие из одной сферы, должна быть доверенной для другой сферы.</span><span class="sxs-lookup"><span data-stu-id="cbf75-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="cbf75-114">Например, сервер авторизации может выдавать маркеры, которые подтверждают, что пользователи из определенной сферы Lync Server 2013 могут получить доступ к указанной сфере Exchange 2013, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="cbf75-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cbf75-115">Область представляет собой просто контейнер безопасности.</span><span class="sxs-lookup"><span data-stu-id="cbf75-115">A realm is simply a security container.</span></span> <span data-ttu-id="cbf75-116">По умолчанию Lync Server 2013 использует используемый по умолчанию домен SIP в качестве сферы OAuth.</span><span class="sxs-lookup"><span data-stu-id="cbf75-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="cbf75-117">В список "Альтернативное имя субъекта" в сертификате OAuth добавляются дополнительные пространства имен SIP.</span><span class="sxs-lookup"><span data-stu-id="cbf75-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="cbf75-118">Lync Server 2013 поддерживает три сценария проверки подлинности "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="cbf75-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="cbf75-119">С помощью Lync Server 2013 вы можете:</span><span class="sxs-lookup"><span data-stu-id="cbf75-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="cbf75-120">Настройка проверки подлинности серверов (сервер-сервер) между локальной установкой Lync Server 2013 и локальной установкой Exchange 2013 и/или Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="cbf75-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="cbf75-121">Настройка проверки подлинности серверов между парой компонентов Office 365 (например, между Microsoft Exchange и Microsoft Lync Server или между Microsoft Lync Server и Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="cbf75-121">Configure server-to-server authentication between a pair of Office 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="cbf75-122">Настройка проверки подлинности серверов в разных локальных средах (то есть для проверки подлинности серверов между локальным сервером и компонентом Office 365).</span><span class="sxs-lookup"><span data-stu-id="cbf75-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Office 365 component).</span></span>

<span data-ttu-id="cbf75-123">Обратите внимание на то, что в данный момент времени только Exchange 2013, SharePoint Server и Lync Server 2013 поддерживают проверку подлинности серверов и серверов; Если вы не используете один из этих серверов, вы не сможете полностью реализовать проверку подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="cbf75-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="cbf75-124">Кроме того, следует обратить внимание на то, что для развертывания Lync Server 2013 не требуется проверка подлинности от сервера к серверу.</span><span class="sxs-lookup"><span data-stu-id="cbf75-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="cbf75-125">Если Lync Server 2013 не требуется взаимодействовать с другими серверами (например, Exchange 2013), проверка подлинности серверов не требуется.</span><span class="sxs-lookup"><span data-stu-id="cbf75-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="cbf75-126">Однако проверка подлинности "сервер-сервер" требуется, если вы хотите использовать некоторые из новых возможностей Lync Server, например "единое хранилище контактов".</span><span class="sxs-lookup"><span data-stu-id="cbf75-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="cbf75-127">С единым хранилищем контактов сведения о контактах Lync Server 2013 хранятся в Exchange 2013, а не в Lync Server; Это позволяет пользователям использовать один набор контактов, доступ к которому можно получить в Lync, Microsoft Outlook или Microsoft Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="cbf75-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="cbf75-128">Поскольку единому хранилищу контактов требуется Lync Server 2013 для совместного использования данных с Exchange 2013, необходимо использовать проверку подлинности серверов для сервера, чтобы развернуть ее.</span><span class="sxs-lookup"><span data-stu-id="cbf75-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="cbf75-129">Проверка подлинности "сервер-сервер" также необходима, если вы решили использовать архивацию Exchange, в которой записи в сеансах обмена мгновенными сообщениями сохраняются как сообщения Exchange 2013, а не в виде отдельных записей базы данных.</span><span class="sxs-lookup"><span data-stu-id="cbf75-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="cbf75-130">Чтобы в версии Office 365 для Lync Server взаимодействовать с аналогом Exchange, Lync Server 2013 сначала должен получить маркер безопасности от сервера авторизации.</span><span class="sxs-lookup"><span data-stu-id="cbf75-130">For the Office 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="cbf75-131">Затем сервер Lync Server использует этот маркер безопасности для идентификации себя в Exchange.</span><span class="sxs-lookup"><span data-stu-id="cbf75-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="cbf75-132">Для связи с Lync Server 2013 версия Exchange для Office 365 должна пройти один и тот же процесс.</span><span class="sxs-lookup"><span data-stu-id="cbf75-132">The Office 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="cbf75-133">Однако для локальной межсерверной проверки подлинности, осуществляемой между двумя серверами Майкрософт, использование стороннего сервера маркеров.</span><span class="sxs-lookup"><span data-stu-id="cbf75-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="cbf75-134">Серверные продукты, такие как Lync Server 2013 и Exchange 2013, имеют встроенный сервер маркеров, который можно использовать для проверки подлинности на других серверах Майкрософт (например, SharePoint Server), поддерживающих проверку подлинности сервера и сервера.</span><span class="sxs-lookup"><span data-stu-id="cbf75-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="cbf75-135">Например, Lync Server 2013 может выпустить и подписать маркер безопасности самостоятельно, а затем использовать этот маркер для связи с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="cbf75-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="cbf75-136">В таком случае использование стороннего сервера маркеров не требуется.</span><span class="sxs-lookup"><span data-stu-id="cbf75-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="cbf75-137">Чтобы настроить проверку подлинности серверов для локальной реализации Lync Server 2013, необходимо выполнить два действия.</span><span class="sxs-lookup"><span data-stu-id="cbf75-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="cbf75-138">Назначьте сертификат встроенному поставщику маркеров Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cbf75-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="cbf75-139">Настройте сервер, с которым будет взаимодействовать Lync Server 2013, как "приложение-партнер".</span><span class="sxs-lookup"><span data-stu-id="cbf75-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="cbf75-140">Например, если для Lync Server 2013 требуется связь с Exchange 2013, то вам потребуется настроить Exchange в качестве партнерского приложения.</span><span class="sxs-lookup"><span data-stu-id="cbf75-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cbf75-141">"Приложение-партнер" — это любое приложение, с помощью которого Lync Server 2013 может напрямую обмениваться маркерами безопасности, не пробегая от стороннего сервера маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="cbf75-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="cbf75-142">Обратите внимание, что OAuth является основной частью продукта. Его нельзя ни отключить, ни удалить.</span><span class="sxs-lookup"><span data-stu-id="cbf75-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="cbf75-143">См. также</span><span class="sxs-lookup"><span data-stu-id="cbf75-143">See Also</span></span>


[<span data-ttu-id="cbf75-144">Назначение сертификата проверки подлинности сервера серверу Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbf75-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="cbf75-145">Настройка Microsoft Lync Server 2013 в нескольких локальных средах</span><span class="sxs-lookup"><span data-stu-id="cbf75-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

