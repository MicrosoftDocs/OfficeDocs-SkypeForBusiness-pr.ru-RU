---
title: 'Lync Server 2013: распространенные угрозы безопасности в современных повседневных средах'
description: 'Lync Server 2013: распространенные угрозы безопасности в современном дне вычислений.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Common security threats in modern day computing
ms:assetid: 56d22197-e8e2-46b8-b3a3-507bd663700e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn433220(v=OCS.15)
ms:contentKeyID: 56708403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47284d91ea9f14e3bafadb1a285f6e98d9ea7ded
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576995"
---
# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="99900-103">Распространенные угрозы безопасности в современных повседневных вычислениях</span><span class="sxs-lookup"><span data-stu-id="99900-103">Common security threats in modern day computing</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99900-104">_**Последнее изменение темы:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="99900-104">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="99900-105">Так как Lync Server 2013 является корпоративной системой связи, следует учитывать распространенные атаки безопасности, которые могут повлиять на инфраструктуру и взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="99900-105">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="99900-106">Compromised-Key атака</span><span class="sxs-lookup"><span data-stu-id="99900-106">Compromised-Key Attack</span></span>

<span data-ttu-id="99900-107">Ключ — это секретный код или номер, используемый для шифрования, расшифровки или проверки секретной информации.</span><span class="sxs-lookup"><span data-stu-id="99900-107">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information.</span></span> <span data-ttu-id="99900-108">В инфраструктуре открытых ключей (PKI) используются два секретных ключа, которые необходимо учитывать:.</span><span class="sxs-lookup"><span data-stu-id="99900-108">There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="99900-109">Закрытый ключ, который у каждого держателя сертификата</span><span class="sxs-lookup"><span data-stu-id="99900-109">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="99900-110">Ключ сеанса, который используется после успешной идентификации и обмена ключами сеанса для взаимодействия с партнерами</span><span class="sxs-lookup"><span data-stu-id="99900-110">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="99900-111">Атака с помощью скомпрометированного ключа происходит, когда злоумышленник определяет закрытый ключ или ключ сеанса.</span><span class="sxs-lookup"><span data-stu-id="99900-111">A compromised-key attack occurs when the attacker determines the private key or the session key.</span></span> <span data-ttu-id="99900-112">Если злоумышленнику удалось определить ключ, злоумышленник может использовать ключ для расшифровки зашифрованных данных без знания отправителя.</span><span class="sxs-lookup"><span data-stu-id="99900-112">When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="99900-113">Lync Server 2013 использует функции PKI в операционной системе Windows Server, чтобы защитить данные ключа, используемые для шифрования подключений TLS.</span><span class="sxs-lookup"><span data-stu-id="99900-113">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="99900-114">Ключи, используемые для шифрования мультимедиа, передаются по протоколу TLS.</span><span class="sxs-lookup"><span data-stu-id="99900-114">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="99900-115">Сетевая атака типа "отказ в обслуживании"</span><span class="sxs-lookup"><span data-stu-id="99900-115">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="99900-116">*Атака типа "отказ в обслуживании"* происходит, когда злоумышленник предотвращает нормальные работы и функции сети действительными пользователями.</span><span class="sxs-lookup"><span data-stu-id="99900-116">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users.</span></span> <span data-ttu-id="99900-117">Это выполняется, когда злоумышленник перемещает службу с помощью подлинных запросов, которые переопределяют использование службы законными пользователями.</span><span class="sxs-lookup"><span data-stu-id="99900-117">This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users.</span></span> <span data-ttu-id="99900-118">С помощью атаки типа "отказ в обслуживании" злоумышленник может выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="99900-118">By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="99900-119">Отправлять недопустимые данные приложениям и службам, работающим в атаках в сети, для прерывания их нормальной работы.</span><span class="sxs-lookup"><span data-stu-id="99900-119">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="99900-120">Отправить большой объем трафика, перегрузить систему до тех пор, пока она не перестанет отвечать на допустимые запросы или реагирует медленнее.</span><span class="sxs-lookup"><span data-stu-id="99900-120">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="99900-121">Скрыть свидетельство атак.</span><span class="sxs-lookup"><span data-stu-id="99900-121">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="99900-122">Запретите пользователям доступ к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="99900-122">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="99900-123">Прослушивание (прослушивание, отслеживание)</span><span class="sxs-lookup"><span data-stu-id="99900-123">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="99900-124">*Прослушивание* может происходить, когда злоумышленник получает доступ к пути к данным в сети и имеет возможность отслеживать и читать трафик.</span><span class="sxs-lookup"><span data-stu-id="99900-124">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic.</span></span> <span data-ttu-id="99900-125">Это также называется *перехватом* или *прослеживанием*.</span><span class="sxs-lookup"><span data-stu-id="99900-125">This is also called *sniffing* or *snooping*.</span></span> <span data-ttu-id="99900-126">Если трафик находится в виде обычного текста, злоумышленник может прочитать трафик, когда он получит доступ к этому пути.</span><span class="sxs-lookup"><span data-stu-id="99900-126">If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path.</span></span> <span data-ttu-id="99900-127">Примером является атака, выполняемая путем управления маршрутизатором по пути к данным.</span><span class="sxs-lookup"><span data-stu-id="99900-127">An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="99900-128">По умолчанию рекомендации и настройка трафика в Microsoft Lync Server 2013 — использование взаимного протокола TLS (MTLS) между доверенными серверами и TLS от клиента к серверу.</span><span class="sxs-lookup"><span data-stu-id="99900-128">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="99900-129">Эта защитная мера сделает атаку очень сложной или невозможной для достижения в течение периода времени, в течение которого происходит данная беседа.</span><span class="sxs-lookup"><span data-stu-id="99900-129">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="99900-130">TLS проверяет подлинность всех сторон и шифрует весь трафик.</span><span class="sxs-lookup"><span data-stu-id="99900-130">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="99900-131">Это не предотвращает прослушивание, но злоумышленник не сможет прочитать трафик, если не будет нарушено его шифрование.</span><span class="sxs-lookup"><span data-stu-id="99900-131">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="99900-132">Протокол перебора NAT (TURN) не требует шифрования трафика, а отправляемые им сведения защищаются с помощью целостности сообщений.</span><span class="sxs-lookup"><span data-stu-id="99900-132">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity.</span></span> <span data-ttu-id="99900-133">Несмотря на то, что он открыт для прослушивания, отправляемые им сведения (то есть IP-адреса и порты) могут извлекаться напрямую путем простого изучения адресов исходного и конечного пакетов.</span><span class="sxs-lookup"><span data-stu-id="99900-133">Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets.</span></span> <span data-ttu-id="99900-134">Пограничная служба аудио-и видеоданных гарантирует, что данные действительны, проверив целостность сообщения с помощью ключа, полученного из нескольких элементов, включая пароль, который никогда не отправляется в виде простого текста.</span><span class="sxs-lookup"><span data-stu-id="99900-134">The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text.</span></span> <span data-ttu-id="99900-135">Если используется протокол Secure реального времени (SRTP), трафик мультимедиа также шифруется.</span><span class="sxs-lookup"><span data-stu-id="99900-135">If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="99900-136">Подмена удостоверений (подмена IP-адресов)</span><span class="sxs-lookup"><span data-stu-id="99900-136">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="99900-137">*Подмена* происходит, когда злоумышленник определяет и использует IP-адрес сети, компьютера или сетевого компонента без разрешения на эту задачу.</span><span class="sxs-lookup"><span data-stu-id="99900-137">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="99900-138">Успешная атака позволяет злоумышленнику работать так, как если бы злоумышленник выявил по IP-адресу.</span><span class="sxs-lookup"><span data-stu-id="99900-138">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="99900-139">В контексте Microsoft Lync Server 2013 эта ситуация возникает только в том случае, если администратор выполнил оба следующих действия:</span><span class="sxs-lookup"><span data-stu-id="99900-139">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="99900-140">Настроенные подключения, поддерживающие только протокол TCP (не рекомендуется, так как связь по протоколу TCP не зашифрована).</span><span class="sxs-lookup"><span data-stu-id="99900-140">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="99900-141">Пометил IP-адреса этих подключений как доверенных узлов.</span><span class="sxs-lookup"><span data-stu-id="99900-141">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="99900-142">Это не проблема для подключений по протоколу TLS, так как протокол TLS проверяет подлинность всех сторон и шифрует весь трафик.</span><span class="sxs-lookup"><span data-stu-id="99900-142">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="99900-143">Использование протокола TLS не позволяет злоумышленнику выполнять подмену IP-адресов для определенного подключения (например, с помощью обоюдных подключений TLS).</span><span class="sxs-lookup"><span data-stu-id="99900-143">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="99900-144">Но злоумышленник по-прежнему может подменить адрес DNS-сервера, используемого Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="99900-144">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="99900-145">Тем не менее, поскольку проверка подлинности в Lync выполняется с помощью сертификатов, злоумышленнику не нужен действительный сертификат, необходимый для подделки одной из сторон в общении.</span><span class="sxs-lookup"><span data-stu-id="99900-145">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="99900-146">Атака "злоумышленник в середине"</span><span class="sxs-lookup"><span data-stu-id="99900-146">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="99900-147">Атака "злоумышленник в середине" происходит, когда злоумышленник перенаправляет обмен данными между двумя пользователями через компьютер злоумышленника, не имея сведений о двух взаимодействующих пользователях.</span><span class="sxs-lookup"><span data-stu-id="99900-147">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="99900-148">Злоумышленник может отслеживать и читать трафик перед его отправкой получателю.</span><span class="sxs-lookup"><span data-stu-id="99900-148">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="99900-149">Каждый пользователь в общении не знает трафик от злоумышленника и получает трафик от злоумышленника, в то же время обдумывая их взаимодействие только с предполагаемым пользователем.</span><span class="sxs-lookup"><span data-stu-id="99900-149">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="99900-150">Это может произойти, если злоумышленник может изменить доменные службы Active Directory, чтобы добавить его сервер в качестве доверенного сервера или изменить систему доменных имен (DNS), чтобы клиенты могли подключаться к серверу через атакующий.</span><span class="sxs-lookup"><span data-stu-id="99900-150">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="99900-151">Атака "злоумышленник в середине" также может возникать с трафиком мультимедиа между двумя клиентами.</span><span class="sxs-lookup"><span data-stu-id="99900-151">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="99900-152">Однако в Microsoft Lync Server 2013 обмен между узлами, видео и общий доступ к приложениям, потоки шифруются с помощью SRTP, используя криптографические ключи, согласованные между одноранговыми узлами, использующими протокол SIP через TLS.</span><span class="sxs-lookup"><span data-stu-id="99900-152">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="99900-153">Для повышения безопасности веб-трафика серверы, такие как групповой чат, используют протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="99900-153">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="99900-154">Атака с повторением RTP</span><span class="sxs-lookup"><span data-stu-id="99900-154">RTP Replay Attack</span></span>

<span data-ttu-id="99900-155">*Атака преобразования* происходит, когда действительная передача мультимедиа между двумя сторонами перехватывается и повторно передается для вредоносных целей.</span><span class="sxs-lookup"><span data-stu-id="99900-155">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes.</span></span> <span data-ttu-id="99900-156">SRTP, используемый в связи с протоколом безопасного обмена сообщениями, обеспечивает защиту от атак типа "Повтор", позволяя получателю поддерживать индекс уже полученных пакетов RTP и сравнивать каждый новый пакет с теми, которые уже указаны в индексе.</span><span class="sxs-lookup"><span data-stu-id="99900-156">SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="99900-157">Нежелательные мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="99900-157">Spim</span></span>

<span data-ttu-id="99900-158">*Нежелательные мгновенные сообщения* — это незапрашиваемые коммерческие мгновенные сообщения или запросы подписки на присутствие.</span><span class="sxs-lookup"><span data-stu-id="99900-158">*Spim* is unsolicited commercial instant messages or presence subscription requests.</span></span> <span data-ttu-id="99900-159">Несмотря на то, что она не подвергает сеть, она, как минимум, может снизить доступность ресурсов и рабочую среду и может привести к нарушению связи в сети.</span><span class="sxs-lookup"><span data-stu-id="99900-159">While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network.</span></span> <span data-ttu-id="99900-160">Например, пользователи спимминг друг друга, отправляя запросы.</span><span class="sxs-lookup"><span data-stu-id="99900-160">An example of this is users spimming each other by sending requests.</span></span> <span data-ttu-id="99900-161">Пользователи могут блокировать друг друга, чтобы предотвратить это, но при использовании Федерации, если установлена согласованная атака нежелательные мгновенные сообщения, это может быть трудно преодолеть, если не отключить федерацию для партнера.</span><span class="sxs-lookup"><span data-stu-id="99900-161">Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="99900-162">Вирусы и черви</span><span class="sxs-lookup"><span data-stu-id="99900-162">Viruses and Worms</span></span>

<span data-ttu-id="99900-163">*Вирус* — это блок кода, предназначенный для воспроизведения дополнительных схожих единиц кода.</span><span class="sxs-lookup"><span data-stu-id="99900-163">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units.</span></span> <span data-ttu-id="99900-164">Для работы вирус должен быть основным приложением, таким как файл, электронная почта или программа.</span><span class="sxs-lookup"><span data-stu-id="99900-164">To work, a virus needs a host, such as a file, email, or program.</span></span> <span data-ttu-id="99900-165">*Worm* — это блок кода, предназначенный для воспроизведения дополнительных, похожих единиц кода, но не требующих ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="99900-165">A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host.</span></span> <span data-ttu-id="99900-166">Вирусы и черви обычно отображаются во время передачи файлов между клиентами или при отправке URL-адресов от других пользователей.</span><span class="sxs-lookup"><span data-stu-id="99900-166">Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users.</span></span> <span data-ttu-id="99900-167">Если вирус находится на вашем компьютере, он может, например, использовать удостоверение и отправлять мгновенные сообщения от вашего имени.</span><span class="sxs-lookup"><span data-stu-id="99900-167">If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="99900-168">Личные сведения;</span><span class="sxs-lookup"><span data-stu-id="99900-168">Personally Identifiable Information</span></span>

<span data-ttu-id="99900-169">Microsoft Lync Server 2013 может раскрывать информацию в общедоступной сети, которая может быть связана с отдельным пользователем.</span><span class="sxs-lookup"><span data-stu-id="99900-169">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="99900-170">Типы данных могут быть разбиты на две определенные категории:</span><span class="sxs-lookup"><span data-stu-id="99900-170">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="99900-171">**Расширенные данные о присутствии** Расширенные данные о присутствии — это сведения, которые пользователь может выбрать для совместного использования или совместного использования ссылки на федеративный партнер или с контактами в Организации.</span><span class="sxs-lookup"><span data-stu-id="99900-171">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="99900-172">Эти данные не предоставлены пользователям в общедоступной сети обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="99900-172">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="99900-173">Клиентские политики и другая конфигурация клиента могут помещать администратору некоторый элемент управления.</span><span class="sxs-lookup"><span data-stu-id="99900-173">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="99900-174">В Lync Server 2013 режим конфиденциальности расширенного присутствия можно настроить для отдельного пользователя, чтобы запретить пользователям Lync, не включенным в список контактов пользователя, просматривать сведения о присутствии пользователя.</span><span class="sxs-lookup"><span data-stu-id="99900-174">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="99900-175">Расширенный режим конфиденциальности присутствия не запрещает пользователям Microsoft Office Communicator 2007 и Microsoft Office Communicator 2007 R2 просматривать сведения о присутствии пользователя.</span><span class="sxs-lookup"><span data-stu-id="99900-175">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="99900-176">Дополнительные сведения: [новые возможности для клиентов в Lync server 2013](lync-server-2013-what-s-new-for-clients.md) в документации Приступая к работе и [Настройка режима конфиденциальности расширенного присутствия в Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="99900-176">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="99900-177">**Обязательные данные** Обязательные данные необходимы для правильной работы сервера или клиента и не управляют администрированием клиента или системы.</span><span class="sxs-lookup"><span data-stu-id="99900-177">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="99900-178">Это информация, необходимая на уровне сервера или сети в целях маршрутизации, обслуживания состояния и сигнализации.</span><span class="sxs-lookup"><span data-stu-id="99900-178">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="99900-179">В приведенных ниже таблицах перечислены данные, предоставляемые через общедоступную сеть.</span><span class="sxs-lookup"><span data-stu-id="99900-179">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="99900-180">Расширенные данные о присутствии</span><span class="sxs-lookup"><span data-stu-id="99900-180">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99900-181">Данные не закрыты</span><span class="sxs-lookup"><span data-stu-id="99900-181">Data Disclosed</span></span></th>
<th><span data-ttu-id="99900-182">Возможные параметры</span><span class="sxs-lookup"><span data-stu-id="99900-182">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99900-183">Персональные данные</span><span class="sxs-lookup"><span data-stu-id="99900-183">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="99900-184">Имя, должность, компания, адрес электронной почты, часовой пояс</span><span class="sxs-lookup"><span data-stu-id="99900-184">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99900-185">Номера телефонов</span><span class="sxs-lookup"><span data-stu-id="99900-185">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="99900-186">Рабочий, мобильный, домашний</span><span class="sxs-lookup"><span data-stu-id="99900-186">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99900-187">Сведения о календаре</span><span class="sxs-lookup"><span data-stu-id="99900-187">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="99900-188">Сведения о доступности, об отсутствии на месте, сведения о собрании (для тех, у кого есть доступ к календарю);</span><span class="sxs-lookup"><span data-stu-id="99900-188">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99900-189">Состояние присутствия</span><span class="sxs-lookup"><span data-stu-id="99900-189">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="99900-190">Нет на месте, доступно, занято, не беспокоить, не подключено</span><span class="sxs-lookup"><span data-stu-id="99900-190">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="99900-191">Обязательные данные</span><span class="sxs-lookup"><span data-stu-id="99900-191">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99900-192">Данные не закрыты</span><span class="sxs-lookup"><span data-stu-id="99900-192">Data Disclosed</span></span></th>
<th><span data-ttu-id="99900-193">Пример сведений</span><span class="sxs-lookup"><span data-stu-id="99900-193">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99900-194">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="99900-194">IP Address</span></span></p></td>
<td><p><span data-ttu-id="99900-195">Фактический адрес компьютера или альтернативного адреса</span><span class="sxs-lookup"><span data-stu-id="99900-195">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99900-196">Универсальный код ресурса (URI) SIP</span><span class="sxs-lookup"><span data-stu-id="99900-196">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="99900-197">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="99900-197">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

