---
title: 'Lync Server 2013: TLS и MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7681b3394a640a64966e3b9c739ea085e6c0f2f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="ce832-102">TLS и MTLS для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce832-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce832-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ce832-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ce832-104">Протоколы TLS и протоколы MTLS обеспечивают зашифрованную связь и проверку подлинности конечных точек в Интернете.</span><span class="sxs-lookup"><span data-stu-id="ce832-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="ce832-105">Microsoft Lync Server 2013 использует эти два протокола для создания сети доверенных серверов, а также для обеспечения шифрования всех коммуникаций по сети.</span><span class="sxs-lookup"><span data-stu-id="ce832-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="ce832-106">Все связи SIP между серверами происходят через MTLS.</span><span class="sxs-lookup"><span data-stu-id="ce832-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="ce832-107">Связь SIP от клиента к серверу выполняется по протоколу TLS.</span><span class="sxs-lookup"><span data-stu-id="ce832-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="ce832-108">Протокол TLS позволяет пользователям с помощью клиентского программного обеспечения проверять подлинность серверов Lync Server 2013, к которым они подключаются.</span><span class="sxs-lookup"><span data-stu-id="ce832-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="ce832-109">При подключении по протоколу TLS клиент запрашивает действительный сертификат с сервера.</span><span class="sxs-lookup"><span data-stu-id="ce832-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="ce832-110">Чтобы быть допустимым, сертификат должен быть выдан центром сертификации, который также является доверенным для клиента, а DNS-имя сервера должно совпадать с DNS-именем в сертификате.</span><span class="sxs-lookup"><span data-stu-id="ce832-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="ce832-111">Если сертификат действителен, клиент использует открытый ключ в сертификате, чтобы зашифровать симметричные ключи шифрования, которые будут использоваться для взаимодействия, поэтому только исходный владелец сертификата может использовать его закрытый ключ для расшифровки содержимого.</span><span class="sxs-lookup"><span data-stu-id="ce832-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="ce832-112">Полученное соединение является доверенным и от него не вызываются другие доверенные серверы или клиенты.</span><span class="sxs-lookup"><span data-stu-id="ce832-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="ce832-113">В этом контексте протокол SSL (Secure Sockets Layer), используемый с веб-службами, может быть связан с помощью протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="ce832-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="ce832-114">Подключения между серверами основываются на MTLS для взаимной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ce832-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="ce832-115">Для подключения MTLS сервер, исходящий сообщение, и сервер, получающий сертификаты Exchange от взаимно доверенного центра сертификации.</span><span class="sxs-lookup"><span data-stu-id="ce832-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="ce832-116">Сертификаты гарантируют идентичность каждого сервера.</span><span class="sxs-lookup"><span data-stu-id="ce832-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="ce832-117">В развертываниях Lync Server 2013 сертификаты, выданные центром сертификации предприятия и не отозванные центром сертификации, автоматически считаются действительными всеми внутренними клиентами и серверами, так как все участники домена Active Directory доверять центру сертификации предприятия в этом домене.</span><span class="sxs-lookup"><span data-stu-id="ce832-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="ce832-118">В федеративных сценариях выставляющий ЦС должен быть доверенным для обоих федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="ce832-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="ce832-119">При необходимости каждый партнер может использовать другой ЦС, пока этот центр сертификации также доверяет другому партнеру.</span><span class="sxs-lookup"><span data-stu-id="ce832-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="ce832-120">Это отношение доверия наиболее легко выполнить с пограничными серверами, на которых сертификат корневого центра сертификации партнера находится в доверенных корневых ЦС, или с помощью стороннего центра сертификации, который является доверенным для обеих сторон.</span><span class="sxs-lookup"><span data-stu-id="ce832-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="ce832-121">Протоколы TLS и MTLS помогают предотвратить как перехват, так и атаки "злоумышленник в середине".</span><span class="sxs-lookup"><span data-stu-id="ce832-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="ce832-122">При атаке "злоумышленник в середине" злоумышленник перенаправляет связь между двумя сетевыми сущностями через компьютер злоумышленника, не зная ни одной из сторон.</span><span class="sxs-lookup"><span data-stu-id="ce832-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="ce832-123">Спецификация TLS и Lync Server 2013 — спецификация доверенных серверов (только указанные в построителе топологий) снижает риск частичной атаки на уровне приложения с помощью сквозного шифрования, согласованного с помощью шифрования открытых ключей между двумя конечными точками и злоумышленник должен иметь действительный и доверенный сертификат с соответствующим закрытым ключом, который выдается в имени службы, с которой клиент взаимодействует для расшифровки связи.</span><span class="sxs-lookup"><span data-stu-id="ce832-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="ce832-124">Тем не менее, в конечном итоге необходимо следовать рекомендациям по обеспечению безопасности в вашей сетевой инфраструктуре (в данном случае это корпоративный DNS-сервер).</span><span class="sxs-lookup"><span data-stu-id="ce832-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="ce832-125">Lync Server 2013 предполагает, что DNS-сервер является доверенным, так как контроллеры домена и глобальные каталоги являются надежными, но DNS обеспечивает уровень защиты от атак DNS-имен, предотвращая успешную реакцию злоумышленника на Запросите поддельное имя.</span><span class="sxs-lookup"><span data-stu-id="ce832-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="ce832-126">На следующем рисунке показан на высоком уровне того, как Lync Server 2013 использует MTLS для создания сети доверенных серверов.</span><span class="sxs-lookup"><span data-stu-id="ce832-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="ce832-127">**Доверенные подключения в сети Lync Server**</span><span class="sxs-lookup"><span data-stu-id="ce832-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="ce832-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="ce832-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

