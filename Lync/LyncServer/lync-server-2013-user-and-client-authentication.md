---
title: 'Lync Server 2013: проверка подлинности пользователя и клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="b5011-102">Проверка подлинности пользователей и клиентов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5011-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5011-103">_**Тема последнего изменения:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="b5011-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="b5011-104">Доверенный пользователь, учетные данные которого прошли проверку подлинности надежным сервером в Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5011-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b5011-105">Этот сервер обычно является сервером стандартных выпусков, сервером переднего плана Enterprise Edition или режиссером.</span><span class="sxs-lookup"><span data-stu-id="b5011-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="b5011-106">В Lync Server 2013 для доменных служб Active Directory используется один доверенный серверный репозиторий для учетных данных пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5011-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="b5011-107">Проверка подлинности представляет собой предоставление учетных данных пользователя доверенному серверу.</span><span class="sxs-lookup"><span data-stu-id="b5011-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="b5011-108">Lync Server 2013 использует следующие протоколы проверки подлинности в зависимости от состояния и местоположения пользователя.</span><span class="sxs-lookup"><span data-stu-id="b5011-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="b5011-109">**Протокол безопасности MIT Kerberos версии 5** для внутренних пользователей с учетными данными Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b5011-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="b5011-110">Для использования протокола Kerberos требуется подключение клиента к доменным службам Active Directory, поэтому его нельзя использовать для проверки подлинности клиентов за пределами корпоративного брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="b5011-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="b5011-111">**Протокол NTLM** для пользователей с учетными данными Active Directory, которые подключаются из конечной точки за пределами корпоративного брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="b5011-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="b5011-112">Служба пограничного доступа передает запросы на вход в директории, если она есть, или на сервер переднего плана для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="b5011-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="b5011-113">Сама служба доступа EDGE не выполняет проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b5011-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b5011-114">Протокол NTLM обеспечивает более слабую защиту от атак в сравнении с Kerberos, поэтому некоторые организации сводят использование NTLM к минимуму.</span><span class="sxs-lookup"><span data-stu-id="b5011-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="b5011-115">В результате доступ к Lync Server 2013 может быть ограничен внутренними или клиентами, подключенными через подключение VPN или DirectAccess.</span><span class="sxs-lookup"><span data-stu-id="b5011-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="b5011-p106">**Дайджест-проверка** для так называемых анонимных пользователей. Анонимные пользователи — это внешние пользователи, которые не имеют распознанных учетных данных Active Directory, но были приглашены в локальную конференцию и обладают действительным ключом конференции. Дайджест-проверка подлинности не используется для других клиентских взаимодействий.</span><span class="sxs-lookup"><span data-stu-id="b5011-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="b5011-119">Аутентификация Lync Server 2013 состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="b5011-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="b5011-120">Между клиентом и сервером устанавливается сопоставление безопасности.</span><span class="sxs-lookup"><span data-stu-id="b5011-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="b5011-p107">Клиент и сервер используют существующее сопоставление безопасности для подписи сообщений, которые они отправляют, и для проверки получения сообщений. Не прошедшие проверку подлинности сообщения от клиента не принимаются при включенной на сервере проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="b5011-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="b5011-p108">Доверие пользователя прикрепляется к каждому сообщению, которое исходит от пользователя, но не к удостоверению пользователя. Сервер проверяет каждое сообщение на наличие действительных учетных данных пользователя. Если учетные данные пользователя действительны, сообщение принимается не только первым получившим его сервером, но и всеми другими серверами в доверенном облаке серверов.</span><span class="sxs-lookup"><span data-stu-id="b5011-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="b5011-126">Пользователи с действительными выданными федеративным партнером учетными данными являются доверенными, но к ним могут применяться другие ограничения привилегий, которые полностью доступны внутренним пользователям.</span><span class="sxs-lookup"><span data-stu-id="b5011-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="b5011-127">Протоколы ICE и TURN также используют требование Digest, описанное в документе IETF TURN RFC.</span><span class="sxs-lookup"><span data-stu-id="b5011-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="b5011-128">Сертификаты клиентов предоставляют альтернативный способ проверки подлинности пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b5011-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="b5011-129">Вместо предоставления имени пользователя и пароля пользователи имеют сертификат и закрытый ключ, соответствующий необходимому для решения криптографической задачи сертификату.</span><span class="sxs-lookup"><span data-stu-id="b5011-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="b5011-130">(У этого сертификата должно быть имя субъекта или дополнительное имя субъекта, которое определяет пользователя, и оно должно выдаваться корневым центром сертификации, который является надежным для серверов с Lync Server 2013, должен быть указан в течение срока действия сертификата, и его нельзя было отозвать.) Для проверки подлинности пользователи обязаны вводить только персональный идентификационный номер (ПИН-код).</span><span class="sxs-lookup"><span data-stu-id="b5011-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="b5011-131">Сертификаты особенно полезны для телефонных звонков и других устройств с Microsoft Lync 2013 Phone Edition, в которых трудно вводить имя пользователя и (или) пароль.</span><span class="sxs-lookup"><span data-stu-id="b5011-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

