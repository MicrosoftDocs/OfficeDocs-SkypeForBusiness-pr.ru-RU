---
title: 'Lync Server 2013: проверка подлинности пользователей и клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 397b17e83d566248117baf917c24fd3100f402d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="f6cd6-102">Проверка подлинности пользователей и клиентов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6cd6-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6cd6-103">_**Последнее изменение темы:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="f6cd6-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="f6cd6-104">Доверенным пользователем является тот, чьи учетные данные прошли проверку подлинности доверенным сервером в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f6cd6-105">Этот сервер обычно является сервером Standard Edition Server, сервером переднего плана Enterprise Edition или директором.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="f6cd6-106">Lync Server 2013 использует доменные службы Active Directory в качестве единого доверенного внутреннего репозитория учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="f6cd6-107">Проверка подлинности — это предоставление учетных данных пользователя доверенному серверу.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="f6cd6-108">Lync Server 2013 использует следующие протоколы проверки подлинности в зависимости от состояния и местоположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="f6cd6-109">**Протокол безопасности MIT Kerberos версии 5** для внутренних пользователей с учетными данными Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="f6cd6-110">Для Kerberos требуется подключение клиентов к доменным службам Active Directory, поэтому он не может использоваться для проверки подлинности клиентов за пресбоями в корпоративном брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="f6cd6-111">**Протокол NTLM** для пользователей с учетными данными Active Directory, которые подключаются из конечной точки за прев корпоративном брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="f6cd6-112">Служба пограничного доступа передает запросы на вход в директоре, если она есть, или на сервер переднего плана для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="f6cd6-113">Служба пограничного доступа сама по себе не выполняет проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f6cd6-114">Протокол NTLM обеспечивает слабую защиту от атак по сравнению с Kerberos, поэтому некоторые организации уменьшают использование NTLM.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="f6cd6-115">В результате доступ к Lync Server 2013 может быть ограничен внутренними или клиентами, подключенными через VPN или подключение DirectAccess.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="f6cd6-116">**Дайджест-протокол** для так называемых анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-116">**Digest protocol** for so-called anonymous users.</span></span> <span data-ttu-id="f6cd6-117">Анонимные пользователи — это внешние пользователи, у которых нет распознаваемых учетных данных Active Directory, но которые были приглашены на локальную конференцию и имеют действительный ключ конференции.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-117">Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key.</span></span> <span data-ttu-id="f6cd6-118">Дайджест-проверка подлинности не используется для других клиентских взаимодействий.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-118">Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="f6cd6-119">Аутентификация Lync Server 2013 состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="f6cd6-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="f6cd6-120">Между клиентом и сервером устанавливается сопоставление безопасности.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="f6cd6-121">Клиент и сервер используют существующее сопоставление безопасности для подписи сообщений, которые они отправляют, и для проверки сообщений, которые они получают.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-121">The client and server use the existing security association to sign messages that they send and to verify the messages they receive.</span></span> <span data-ttu-id="f6cd6-122">Сообщения, не прошедшие проверку подлинности, не принимаются клиентом при включенной проверке подлинности на сервере.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-122">Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="f6cd6-123">Доверие пользователя присоединяется к каждому сообщению, полученному от пользователя, а не к самому удостоверению пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-123">User trust is attached to each message that originates from a user, not to the user identity itself.</span></span> <span data-ttu-id="f6cd6-124">Сервер проверяет каждое сообщение на наличие действительных учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-124">The server checks each message for valid user credentials.</span></span> <span data-ttu-id="f6cd6-125">Если учетные данные пользователя действительны, сообщение не будет обработано только на первом сервере для его получения, но всеми остальными серверами в облаке доверенных серверов.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-125">If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="f6cd6-126">Пользователи с действительными учетными данными, выданными федеративным партнером, являются доверенными, но при необходимости могут быть недоступны дополнительные ограничения на полный диапазон прав, применяющий внутренних пользователей.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="f6cd6-127">Протоколы ICE и TURN также используют дайджест-запрос, как описано в документе IETF.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="f6cd6-128">Клиентские сертификаты предоставляют альтернативный способ проверки подлинности пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="f6cd6-129">Вместо имени пользователя и пароля пользователи имеют сертификат и закрытый ключ, соответствующий сертификату, который требуется для решения криптографических проблем.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="f6cd6-130">(Этот сертификат должен содержать имя субъекта или альтернативное имя субъекта, которое идентифицирует пользователя и должно быть выдано корневым центром сертификации, который является доверенным для серверов, работающих под управлением Lync Server 2013, в течение срока действия сертификата, а не отозван). Чтобы пройти проверку подлинности, пользователям необходимо ввести личный идентификационный номер (ПИН-код).</span><span class="sxs-lookup"><span data-stu-id="f6cd6-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="f6cd6-131">Сертификаты особенно удобны для телефонных телефонов и других устройств с Microsoft Lync 2013 Phone Edition, где трудно ввести имя пользователя и/или пароль.</span><span class="sxs-lookup"><span data-stu-id="f6cd6-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

