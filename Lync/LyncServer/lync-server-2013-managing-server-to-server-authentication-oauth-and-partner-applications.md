---
title: Управление проверкой подлинности между серверами (OAuth) и партнерским приложением
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
ms.openlocfilehash: a0d554bc935ea24f7098472a5c893f58dc717839
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="c1c8f-102">Управление проверкой подлинности между серверами (OAuth) и партнерским приложением в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1c8f-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1c8f-103">_**Последнее изменение темы:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="c1c8f-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="c1c8f-104">Microsoft Lync Server 2013 должен обеспечивать безопасное и эффективное взаимодействие с другими приложениями и серверными продуктами.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="c1c8f-105">Например, вы можете настроить Lync Server 2013 таким образом, чтобы данные контактов и/или архивные данные хранились в Microsoft Exchange Server 2013; Тем не менее, это можно сделать только в том случае, если Lync Server и Exchange могут безопасно общаться друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="c1c8f-106">Аналогичным образом можно запланировать конференцию Lync Server на сервере Microsoft SharePoint Server; однако опять же это возможно только при наличии взаимных отношений доверия между этими двумя серверами (SharePoint и Lync Server).</span><span class="sxs-lookup"><span data-stu-id="c1c8f-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="c1c8f-107">Хотя можно использовать один механизм проверки подлинности для взаимодействия Lync с Exchange и другой — для взаимодействия Lync с SharePoint, более эффективным подходом является использование стандартного метода для межсерверной проверки подлинности и авторизации.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="c1c8f-108">Один стандартизированный метод проверки подлинности "сервер-сервер" — это подход, выполняемый Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="c1c8f-109">В выпуске 2013 Lync Server 2013 (а также другие серверные продукты Майкрософт, в том числе Exchange 2013 и Microsoft SharePoint Server) поддерживают протокол OAuth (открытая авторизация) для проверки подлинности и авторизации "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="c1c8f-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="c1c8f-110">При использовании OAuth стандартным протоколом авторизации, используемым для ряда основных сайтов, учетные данные пользователя и пароли не передаются с одного компьютера на другой.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="c1c8f-111">Вместо этого проверка подлинности и авторизация основаны на обмене маркерами безопасности, которые предоставляют доступ к определенному набору ресурсов в течение определенного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="c1c8f-112">Как правило, проверка подлинность OAuth включает три компонента: отдельный сервер авторизации и две области, которые должны взаимодействовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="c1c8f-113">(Вы также можете выполнять проверку подлинности "сервер-сервер", не используя сервер авторизации, процесс, который будет обсуждаться далее в этом документе.) Токены безопасности выдаются сервером авторизации (также называется сервером маркеров безопасности) в две сферы, которые необходимы для обмена сообщениями; Эти маркеры проверки того, что связь, поступающие из одной области, должна быть доверенной для другой области.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="c1c8f-114">Например, сервер авторизации может выдать маркеры, которые проверяют, что пользователи из определенной области Lync Server 2013 могут получить доступ к заданной области Exchange 2013, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c1c8f-115">Область представляет собой просто контейнер безопасности.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-115">A realm is simply a security container.</span></span> <span data-ttu-id="c1c8f-116">По умолчанию Lync Server 2013 использует домен SIP по умолчанию в качестве области OAuth.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="c1c8f-117">Дополнительные пространства имен SIP добавляются в список альтернативных имен субъектов в сертификате OAuth.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="c1c8f-118">Lync Server 2013 поддерживает три сценария проверки подлинности между серверами.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="c1c8f-119">С помощью Lync Server 2013 вы можете:</span><span class="sxs-lookup"><span data-stu-id="c1c8f-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="c1c8f-120">Настройка межсерверной проверки подлинности между локальной установкой Lync Server 2013 и локальной установкой Exchange 2013 и/или Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="c1c8f-121">Настройка межсерверной проверки подлинности между двумя компонентами Office 365 (например, между Microsoft Exchange и Microsoft Lync Server или между Microsoft Lync Server и Microsoft SharePoint).</span><span class="sxs-lookup"><span data-stu-id="c1c8f-121">Configure server-to-server authentication between a pair of Office 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="c1c8f-122">Настраивать межсерверную проверку подлинности в распределенной среде (то есть межсерверную проверку подлинности между локальным сервером и компонентом 365).</span><span class="sxs-lookup"><span data-stu-id="c1c8f-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Office 365 component).</span></span>

<span data-ttu-id="c1c8f-123">Обратите внимание на то, что на данный момент времени только Exchange 2013, SharePoint Server и Lync Server 2013 поддерживает проверку подлинности между серверами; Если вы не используете один из этих серверов, вы не сможете полностью реализовать проверку подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="c1c8f-124">Кроме того, следует обратить внимание на то, что не требуется использовать проверку подлинности "сервер-сервер": проверка подлинности между серверами не требуется для развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="c1c8f-125">Если Lync Server 2013 не требуется связываться с другими серверами (например, Exchange 2013), то проверка подлинности "сервер-сервер" не требуется.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="c1c8f-126">Однако межсерверная проверка подлинности необходимо, если вы хотите использовать некоторые новые функции сервера Lync Server, например «универсальное хранилище контактов».</span><span class="sxs-lookup"><span data-stu-id="c1c8f-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="c1c8f-127">В едином хранилище контактов сведения о контакте для Lync Server 2013 хранятся в Exchange 2013, а не в Lync Server; Это позволяет пользователям иметь единый набор контактов, доступных в Lync, Microsoft Outlook или Microsoft Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="c1c8f-128">Так как в едином хранилище контактов требуется Lync Server 2013 для обмена данными с Exchange 2013, необходимо использовать проверку подлинности "сервер-сервер", чтобы развернуть эту функцию.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="c1c8f-129">Проверка подлинности "сервер-сервер" также необходима, если вы решили использовать архивацию Exchange, в которой расшифровки сеансов обмена мгновенными сообщениями сохраняются как сообщения Exchange 2013, а не как отдельные записи базы данных.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="c1c8f-130">Для обмена данными с аналогом Exchange в версии Office 365 Lync Server 2013 сначала необходимо получить маркер безопасности от сервера авторизации.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-130">For the Office 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="c1c8f-131">Затем Lync Server использует этот маркер безопасности для идентификации в Exchange.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="c1c8f-132">Для связи с Lync Server 2013 в версии Office 365 Exchange необходимо выполнить один и тот же процесс.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-132">The Office 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="c1c8f-133">Однако для локальной межсерверной проверки подлинности, осуществляемой между двумя серверами Майкрософт, использование стороннего сервера маркеров.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="c1c8f-134">Серверные продукты, такие как Lync Server 2013 и Exchange 2013, имеют встроенный сервер маркеров, который можно использовать для проверки подлинности с другими серверами Майкрософт (например, SharePoint Server), поддерживающими проверку подлинности "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="c1c8f-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="c1c8f-135">Например, Lync Server 2013 может сам создать и подписать токен безопасности, с помощью которого затем установит связь с Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="c1c8f-136">В таком случае использовать сторонний сервер токенов не нужно.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="c1c8f-137">Чтобы настроить межсерверную проверку подлинности для локальной реализации Lync Server 2013, необходимо выполнить два действия:</span><span class="sxs-lookup"><span data-stu-id="c1c8f-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="c1c8f-138">Назначить сертификат встроенному средству выдачи маркеров Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="c1c8f-139">Настройте сервер, с которым будет общаться Lync Server 2013, как "партнерское приложение".</span><span class="sxs-lookup"><span data-stu-id="c1c8f-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="c1c8f-140">Например, если Lync Server 2013 должен обмениваться данными с Exchange 2013, необходимо настроить Exchange для использования в качестве партнерского приложения.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="c1c8f-141">"Партнерское приложение" — это любое приложение, с помощью которого Lync Server 2013 может напрямую обмениваться маркерами безопасности, без необходимости проходить от стороннего сервера маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="c1c8f-142">Обратите внимание, что OAuth является основной частью продукта и не может быть отключен или удален.</span><span class="sxs-lookup"><span data-stu-id="c1c8f-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c1c8f-143">См. также</span><span class="sxs-lookup"><span data-stu-id="c1c8f-143">See Also</span></span>


[<span data-ttu-id="c1c8f-144">Назначение сертификата проверки подлинности между серверами серверу Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1c8f-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="c1c8f-145">Настройка Microsoft Lync Server 2013 в распределенной среде</span><span class="sxs-lookup"><span data-stu-id="c1c8f-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

