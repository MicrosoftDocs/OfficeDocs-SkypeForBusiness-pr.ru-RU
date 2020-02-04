---
title: 'Lync Server 2013: распространенные угрозы безопасности в современных повседневных системах'
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
ms.openlocfilehash: 99e17f9f6dbba30697c72fecf77fbff4bfbdc003
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="common-security-threats-in-modern-day-computing"></a><span data-ttu-id="c3359-102">Распространенные угрозы безопасности в современном компьютерном мире</span><span class="sxs-lookup"><span data-stu-id="c3359-102">Common security threats in modern day computing</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3359-103">_**Тема последнего изменения:** 2013-09-10_</span><span class="sxs-lookup"><span data-stu-id="c3359-103">_**Topic Last Modified:** 2013-09-10_</span></span>

<span data-ttu-id="c3359-104">Поскольку Lync Server 2013 — это система связи по корпоративному классу, необходимо знать об общих атаках системы безопасности, которые могут повлиять на инфраструктуру и связь.</span><span class="sxs-lookup"><span data-stu-id="c3359-104">Because Lync Server 2013 is an enterprise-class communications system, you should be aware of common security attacks that could affect its infrastructure and communications.</span></span>

<div>

## <a name="compromised-key-attack"></a><span data-ttu-id="c3359-105">Атака с использованием скомпрометированного ключа</span><span class="sxs-lookup"><span data-stu-id="c3359-105">Compromised-Key Attack</span></span>

<span data-ttu-id="c3359-p101">Ключ — это секретный код или число, используемые для шифрования, расшифровки или проверки секретных сведений. В инфраструктуре открытых ключей есть два важных ключа, которые требуют пристального внимания.</span><span class="sxs-lookup"><span data-stu-id="c3359-p101">A key is a secret code or number that is used to encrypt, decrypt, or validate secret information. There are two sensitive keys in use in public key infrastructure (PKI) that must be considered: .</span></span>

  - <span data-ttu-id="c3359-108">Закрытый ключ, который есть у каждого владельца сертификата</span><span class="sxs-lookup"><span data-stu-id="c3359-108">The private key that each certificate holder has</span></span>

  - <span data-ttu-id="c3359-109">Ключ сеанса, который используется после успешной идентификации и обмена ключами сеансов между участниками обмена данными</span><span class="sxs-lookup"><span data-stu-id="c3359-109">The session key that is used after a successful identification and session key exchange by the communicating partners</span></span>

<span data-ttu-id="c3359-p102">Атака с использованием скомпрометированного ключа происходит, когда злоумышленнику удается получить закрытый ключ или ключ сеанса. После этого он может использовать полученный ключ для расшифровки зашифрованных данных без ведома отправителя.</span><span class="sxs-lookup"><span data-stu-id="c3359-p102">A compromised-key attack occurs when the attacker determines the private key or the session key. When the attacker is successful in determining the key, the attacker can use the key to decrypt encrypted data without the knowledge of the sender.</span></span>

<span data-ttu-id="c3359-112">Lync Server 2013 использует возможности PKI в операционной системе Windows Server для защиты данных ключа, используемых для шифрования подключений TLS.</span><span class="sxs-lookup"><span data-stu-id="c3359-112">Lync Server 2013 uses the PKI features in the Windows Server operating system to protect the key data used for encryption for the Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="c3359-113">Ключи, используемые для шифрования, передаются по каналам TLS.</span><span class="sxs-lookup"><span data-stu-id="c3359-113">The keys used for media encryption are exchanged over TLS connections.</span></span>

</div>

<div>

## <a name="network-denial-of-service-attack"></a><span data-ttu-id="c3359-114">Атака отказа в обслуживании сети</span><span class="sxs-lookup"><span data-stu-id="c3359-114">Network Denial-of-Service Attack</span></span>

<span data-ttu-id="c3359-p104">*Атака типа "отказ в обслуживании"* происходит, когда злоумышленнику удается нарушить нормальную работу сети и возможность ее штатного использования. Для этого злоумышленник отправляет службе большое количество формально допустимых запросов, которые мешают работе с ней нормальных пользователей. С помощью атаки типа "отказ в обслуживании" злоумышленник может выполнить перечисленные ниже задачи.</span><span class="sxs-lookup"><span data-stu-id="c3359-p104">The *denial-of-service attack* occurs when the attacker prevents normal network use and function by valid users. This is done when the attacker floods the service with legitimate requests that overwhelm the use of the service by legitimate users. By using a denial-of-service attack, the attacker can do the following:</span></span>

  - <span data-ttu-id="c3359-118">Отправка недействительных данных приложениям и службам, работающим в атакуемой сети, для нарушения их нормальной работы.</span><span class="sxs-lookup"><span data-stu-id="c3359-118">Send invalid data to applications and services running in the attacked network to disrupt their normal function.</span></span>

  - <span data-ttu-id="c3359-119">Отправка больших объемов трафика, перегружающего систему, пока она не прекратит реагировать на нормальные запросы либо время реакции не замедлится.</span><span class="sxs-lookup"><span data-stu-id="c3359-119">Send a large amount of traffic, overloading the system until it stops responding or responds slowly to legitimate requests.</span></span>

  - <span data-ttu-id="c3359-120">Сокрытие следов атаки.</span><span class="sxs-lookup"><span data-stu-id="c3359-120">Hide the evidence of the attacks.</span></span>

  - <span data-ttu-id="c3359-121">Нарушение доступа пользователей к ресурсам сети.</span><span class="sxs-lookup"><span data-stu-id="c3359-121">Prevent users from accessing network resources.</span></span>

</div>

<div>

## <a name="eavesdropping-sniffing-snooping"></a><span data-ttu-id="c3359-122">Прослушивание (сканирование, слежение)</span><span class="sxs-lookup"><span data-stu-id="c3359-122">Eavesdropping (Sniffing, Snooping)</span></span>

<span data-ttu-id="c3359-p105">*Прослушивание* осуществляется, когда злоумышленнику удается получить доступ к каналам передачи данных в сети с возможностью контролировать и просматривать трафик. Такой тип атаки также называется *сканированием* или *слежением*. Если трафик передается в виде обычного текста, злоумышленник может прочитать его, получив доступ к каналу обмена данными. Примером такой атаки является контроль маршрутизатора в составе такого канала.</span><span class="sxs-lookup"><span data-stu-id="c3359-p105">*Eavesdropping* can occur when an attacker gains access to the data path in a network and has the ability to monitor and read the traffic. This is also called *sniffing* or *snooping*. If the traffic is in plain text, the attacker can read the traffic when the attacker gains access to the path. An example is an attack performed by controlling a router on the data path.</span></span>

<span data-ttu-id="c3359-127">Согласно рекомендациям по умолчанию для трафика в Microsoft Lync Server 2013 вы можете использовать обоюд TLS (MTLS) между доверенными серверами и TLS из клиента на сервер.</span><span class="sxs-lookup"><span data-stu-id="c3359-127">The default recommendation and setting for traffic within Microsoft Lync Server 2013 is to use mutual TLS (MTLS) between trusted servers and TLS from client to server.</span></span> <span data-ttu-id="c3359-128">Такая защитная мера существенно затруднит атаку или сделает ее невозможной в рамках периода, в течение которого осуществляется обмен информацией.</span><span class="sxs-lookup"><span data-stu-id="c3359-128">This protective measure would make an attack very difficult or impossible to achieve within the time period in which a given conversation occurs.</span></span> <span data-ttu-id="c3359-129">При работе по протоколу TLS производится проверка подлинности всех участников и шифруется весь трафик.</span><span class="sxs-lookup"><span data-stu-id="c3359-129">TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="c3359-130">Это не защищает от прослушивания, однако злоумышленнику не удастся прочитать передаваемые данные, если только он не взломает систему шифрования.</span><span class="sxs-lookup"><span data-stu-id="c3359-130">This does not prevent eavesdropping, but the attacker cannot read the traffic unless the encryption is broken.</span></span>

<span data-ttu-id="c3359-p107">Протокол TURN не требует шифрования трафика, и отправляемая с его использованием информация защищается посредством контроля целостности сообщений. Хотя этот протокол открыт для прослушивания, передаваемые по нему данные (IP-адреса и порт) можно получить непосредственно путем простого анализа исходного и конечного адресов пакета. Пограничная служба аудио- и видеоданных проверяет действительность информации посредством контроля целостности сообщений с помощью ключа, основанного на нескольких элементах, включая пароль TURN, который никогда не передается в виде простого текста. При использовании протокола SRTP также шифруются мультимедийные данные.</span><span class="sxs-lookup"><span data-stu-id="c3359-p107">The Traversal Using Relay NAT (TURN) protocol does not mandate the traffic to be encrypted and the information that it is sending is protected by message integrity. Although it is open to eavesdropping, the information it is sending (that is, the IP addresses and port) can be extracted directly by simply looking at the source and destination addresses of the packets. The A/V Edge service ensures that the data is valid by checking the Message Integrity of the message by using the key derived from a few items, including a TURN password, which is never sent in clear text. If Secure Real Time Protocol (SRTP) is used, media traffic is also encrypted.</span></span>

</div>

<div>

## <a name="identity-spoofing-ip-address-spoofing"></a><span data-ttu-id="c3359-135">Подделка подлинности (спуфинг IP-адреса)</span><span class="sxs-lookup"><span data-stu-id="c3359-135">Identity Spoofing (IP Address Spoofing)</span></span>

<span data-ttu-id="c3359-136">*Спуфинг* происходит, когда злоумышленнику удается несанкционированно определить IP-адрес сети, компьютера или элемента сети.</span><span class="sxs-lookup"><span data-stu-id="c3359-136">*Spoofing* occurs when the attacker determines and uses an IP address of a network, computer, or network component without being authorized to do so.</span></span> <span data-ttu-id="c3359-137">Успешная атака позволяет злоумышленнику действовать под видом субъекта, обладающего допустимым IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="c3359-137">A successful attack allows the attacker to operate as if the attacker is the entity normally identified by the IP address.</span></span> <span data-ttu-id="c3359-138">В контексте Microsoft Lync Server 2013 эта ситуация возникает только в том случае, если администратор выполнил оба указанных ниже действия.</span><span class="sxs-lookup"><span data-stu-id="c3359-138">Within the context of Microsoft Lync Server 2013, this situation comes into play only if an administrator has done both of the following:</span></span>

  - <span data-ttu-id="c3359-139">Настроил подключения, поддерживающие только протокол TCP (делать этого не рекомендуется, так как данные, передаваемые по протоколу TCP, не шифруются).</span><span class="sxs-lookup"><span data-stu-id="c3359-139">Configured connections that support only Transmission Control Protocol (TCP) (which is not recommended, because TCP communications are unencrypted).</span></span>

  - <span data-ttu-id="c3359-140">Отметил IP-адреса участников таких подключений как надежные узлы.</span><span class="sxs-lookup"><span data-stu-id="c3359-140">Marked the IP addresses of those connections as trusted hosts.</span></span>

<span data-ttu-id="c3359-141">Эта проблема менее актуальна для подключений по протоколу TLS, так как при обмене данными по этому протоколу производится проверка подлинности всех участников и шифрование всей информации.</span><span class="sxs-lookup"><span data-stu-id="c3359-141">This is less of a problem for Transport Layer Security (TLS) connections, as TLS authenticates all parties and encrypts all traffic.</span></span> <span data-ttu-id="c3359-142">Использование TLS не позволяет злоумышленнику выполнить IP-спуфинг для определенного подключения (например, для соединений, оба участника которых работают по этому протоколу).</span><span class="sxs-lookup"><span data-stu-id="c3359-142">Using TLS prevents an attacker from performing IP address spoofing on a specific connection (for example, mutual TLS connections).</span></span> <span data-ttu-id="c3359-143">Но злоумышленник по-прежнему может подменить адрес DNS-сервера, используемого Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3359-143">But an attacker could still spoof the address of the DNS server that Lync Server 2013 uses.</span></span> <span data-ttu-id="c3359-144">Тем не менее, поскольку проверка подлинности в Lync выполняется с помощью сертификатов, злоумышленнику не нужен действительный сертификат, необходимый для подделки одной из сторон в общении.</span><span class="sxs-lookup"><span data-stu-id="c3359-144">However, because authentication in Lync is performed with certificates, an attacker would not have a valid certificate required to spoof one of the parties in the communication.</span></span>

</div>

<div>

## <a name="man-in-the-middle-attack"></a><span data-ttu-id="c3359-145">Атака "злоумышленник в середине"</span><span class="sxs-lookup"><span data-stu-id="c3359-145">Man-in-the-Middle Attack</span></span>

<span data-ttu-id="c3359-146">Атака типа "злоумышленник в середине" происходит, когда злоумышленнику удается перенаправить данные, которыми обмениваются два пользователя, через свой компьютер без ведома этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="c3359-146">A man-in-the-middle attack occurs when an attacker reroutes communication between two users through the attacker’s computer without the knowledge of the two communicating users.</span></span> <span data-ttu-id="c3359-147">В результате злоумышленник получает возможность контролировать и просматривать трафик перед его отправкой предполагаемому получателю.</span><span class="sxs-lookup"><span data-stu-id="c3359-147">The attacker can monitor and read the traffic before sending it on to the intended recipient.</span></span> <span data-ttu-id="c3359-148">Каждый из участников обмена данными на самом деле обменивается трафиком со злоумышленником, думая при этом, что информация передается второму пользователю.</span><span class="sxs-lookup"><span data-stu-id="c3359-148">Each user in the communication unknowingly sends traffic to and receives traffic from the attacker, all while thinking they are communicating only with the intended user.</span></span> <span data-ttu-id="c3359-149">Такая ситуация может возникнуть, если злоумышленнику удается внести изменения в доменные службы Active Directory и добавить свой сервер в качестве доверенного либо изменить систему доменных имен (DNS) таким образом, чтобы клиенты подключались к серверу через компьютер злоумышленника.</span><span class="sxs-lookup"><span data-stu-id="c3359-149">This can happen if an attacker can modify Active Directory Domain Services to add his or her server as a trusted server or modify Domain Name System (DNS) to get clients to connect through the attacker on their way to the server.</span></span> <span data-ttu-id="c3359-150">Атака "злоумышленник в середине" также может возникнуть при пересылке мультимедийных данных между двумя клиентами.</span><span class="sxs-lookup"><span data-stu-id="c3359-150">A man-in-the-middle attack can also occur with media traffic between two clients.</span></span> <span data-ttu-id="c3359-151">Тем не менее, в Microsoft Lync Server 2013 обмен данными с аудио-и видеофайлами и приложениями, потоки шифруются с помощью SRTP, используя криптографические ключи, согласованные между одноранговыми узлами, использующими протокол запуска сеансов (SIP) в TLS.</span><span class="sxs-lookup"><span data-stu-id="c3359-151">However, in Microsoft Lync Server 2013 point-to-point audio, video, and application sharing, streams are encrypted with SRTP, using cryptographic keys that are negotiated between the peers that are using Session Initiation Protocol (SIP) over TLS.</span></span> <span data-ttu-id="c3359-152">На серверах (например, сервере группового чата) для дополнительной защиты сетевого трафика используется протокол HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c3359-152">Servers such as Group Chat make use of HTTPS to enhance the security of web traffic.</span></span>

</div>

<div>

## <a name="rtp-replay-attack"></a><span data-ttu-id="c3359-153">Атака с воспроизведением RTP</span><span class="sxs-lookup"><span data-stu-id="c3359-153">RTP Replay Attack</span></span>

<span data-ttu-id="c3359-p111">*Атака с воспроизведением пакетов* происходит при перехвате допустимых мультимедийных данных, которыми обмениваются две стороны, и их повторной пересылке в злонамеренных целях. Защитить передаваемые данные от атаки с воспроизведением можно с помощью протокола SRTP в сочетании с протоколом безопасного обмена сигналами, которые позволяют получателю вести учет уже полученных пакетов RTP и сравнивать каждый новый пакет с уже имеющимися в списке.</span><span class="sxs-lookup"><span data-stu-id="c3359-p111">A *replay attack* occurs when a valid media transmission between two parties is intercepted and retransmitted for malicious purposes. SRTP used in connection with a secure signaling protocol protects transmissions from replay attacks by enabling the receiver to maintain an index of already received RTP packets and compare each new packet with those already listed in the index.</span></span>

</div>

<div>

## <a name="spim"></a><span data-ttu-id="c3359-156">Нежелательные мгновенные сообщения</span><span class="sxs-lookup"><span data-stu-id="c3359-156">Spim</span></span>

<span data-ttu-id="c3359-p112">*Нежелательные мгновенные сообщения* — это нежелательные мгновенные сообщения коммерческого характера либо запросы подписки на сведения о присутствии. Хотя такие сообщения сами по себе не нарушают безопасность сети, они как минимум раздражают пользователей, ухудшают их доступность и производительность и в перспективе могут привести к нарушению сетевой безопасности. Примером является отправка пользователями нежелательных запросов друг другу. Чтобы избавиться от таких запросов, пользователи могут блокировать друг друга, однако защититься от скоординированной атаки нежелательными мгновенными сообщениями в федеративной среде сложно без отключения федерации партнера.</span><span class="sxs-lookup"><span data-stu-id="c3359-p112">*Spim* is unsolicited commercial instant messages or presence subscription requests. While not by itself a compromise of the network, it is annoying in the least, can reduce resource availability and production, and can possibly lead to a compromise of the network. An example of this is users spimming each other by sending requests. Users can block each other to prevent this, but with federation, if a coordinated spim attack is established, this can be difficult to overcome unless you disable federation for the partner.</span></span>

</div>

<div>

## <a name="viruses-and-worms"></a><span data-ttu-id="c3359-161">Вирусы и черви</span><span class="sxs-lookup"><span data-stu-id="c3359-161">Viruses and Worms</span></span>

<span data-ttu-id="c3359-p113">*Вирус* — это блок кода, задача которого — воспроизводство идентичных блоков. Для работы вирусу нужен носитель, например файл, сообщение электронной почты или программа. *Вирус-червь* — это блок кода, задача которого —также воспроизводство идентичных блоков, однако носитель ему не нужен. Вирусы и черви в основном появляются при обмене файлами между клиентами, а также при получении URL-адресов от других пользователей. Если вирус находится на компьютере, он может, например, использовать идентификационные данные хозяина для отправки мгновенных сообщений от его имени.</span><span class="sxs-lookup"><span data-stu-id="c3359-p113">A *virus* is a unit of code whose purpose is to reproduce additional, similar code units. To work, a virus needs a host, such as a file, email, or program. A *worm* is a unit of code whose purpose is to reproduce additional, similar code units, but it does not need a host. Viruses and worms primarily show up during file transfers between clients or when URLs are sent from other users. If a virus is on your computer, it can, for example, use your identity and send instant messages on your behalf.</span></span>

</div>

<div>

## <a name="personally-identifiable-information"></a><span data-ttu-id="c3359-167">Личные сведения</span><span class="sxs-lookup"><span data-stu-id="c3359-167">Personally Identifiable Information</span></span>

<span data-ttu-id="c3359-168">Microsoft Lync Server 2013 имеет возможность раскрывать информацию в общедоступной сети, которая может быть связана с отдельным абонентом.</span><span class="sxs-lookup"><span data-stu-id="c3359-168">Microsoft Lync Server 2013 has the potential to disclose information over a public network that might be able to be linked to an individual.</span></span> <span data-ttu-id="c3359-169">Сведения можно отнести к двум категориям.</span><span class="sxs-lookup"><span data-stu-id="c3359-169">The information types can be broken down to two specific categories:</span></span>

  - <span data-ttu-id="c3359-170">**Расширенные данные о присутствии** Расширенные данные о присутствии — это сведения, с помощью которых пользователь может предоставить общий доступ к ссылке на федеративного партнера или с контактами в Организации.</span><span class="sxs-lookup"><span data-stu-id="c3359-170">**Enhanced presence data** Enhanced presence data is information that a user can choose to share or not share over a link to a federated partner or with contacts within an organization.</span></span> <span data-ttu-id="c3359-171">Эти данные не передаются пользователям в общедоступной сети обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="c3359-171">This data is not shared with users on a public IM network.</span></span> <span data-ttu-id="c3359-172">Администратор может в определенной мере контролировать доступ к такой информации с помощью политик и других настроек клиентов.</span><span class="sxs-lookup"><span data-stu-id="c3359-172">Client policies and other client configuration may put some control with the system administrator.</span></span> <span data-ttu-id="c3359-173">В Lync Server 2013 можно настроить режим конфиденциальности расширенного присутствия для отдельного пользователя, чтобы пользователи Lync не могли видеть сведения о присутствии пользователя в списке контактов пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3359-173">In Lync Server 2013, enhanced presence privacy mode can be configured for an individual user to prevent Lync users not on the user’s Contacts list from seeing the user’s presence information.</span></span> <span data-ttu-id="c3359-174">Режим конфиденциальности расширенных возможностей присутствия не мешает пользователям Microsoft Office Communicator 2007 и Microsoft Office Communicator 2007 R2 видеть сведения о присутствии данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="c3359-174">Enhanced presence privacy mode does not prevent users of Microsoft Office Communicator 2007 and Microsoft Office Communicator 2007 R2 from seeing a user’s presence information.</span></span> <span data-ttu-id="c3359-175">Дополнительные сведения можно найти в разделе [новые возможности для клиентов в Lync server 2013](lync-server-2013-what-s-new-for-clients.md) в документации Приступая к работе и [Настройка режима конфиденциальности в Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c3359-175">For details, see [What's new for clients in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md) in the Getting Started documentation and [Configuring enhanced presence privacy mode in Lync Server 2013](lync-server-2013-configuring-enhanced-presence-privacy-mode.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="c3359-176">**Обязательные данные** Обязательные данные необходимы для правильного функционирования сервера или клиента и не управляются администрированием клиента или системы.</span><span class="sxs-lookup"><span data-stu-id="c3359-176">**Mandatory data** Mandatory data is required for the proper operation of the server or the client and is NOT under the control of the client or system administration.</span></span> <span data-ttu-id="c3359-177">Это сведения, которые необходимы на уровне сервера или сети для осуществления маршрутизации, поддержки состояния и передачи сигналов.</span><span class="sxs-lookup"><span data-stu-id="c3359-177">This is information that is necessary at a server or network level for the purposes of routing, state maintenance, and signaling.</span></span>

<span data-ttu-id="c3359-178">В таблицах ниже приведены данные, которые доступны в общедоступной сети.</span><span class="sxs-lookup"><span data-stu-id="c3359-178">The following tables list the data that is exposed over a public network.</span></span>

### <a name="enhanced-presence-data"></a><span data-ttu-id="c3359-179">Расширенные данные о присутствии</span><span class="sxs-lookup"><span data-stu-id="c3359-179">Enhanced Presence Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3359-180">Раскрываемые данные</span><span class="sxs-lookup"><span data-stu-id="c3359-180">Data Disclosed</span></span></th>
<th><span data-ttu-id="c3359-181">Возможные параметры</span><span class="sxs-lookup"><span data-stu-id="c3359-181">Possible Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3359-182">Личные данные</span><span class="sxs-lookup"><span data-stu-id="c3359-182">Personal Data</span></span></p></td>
<td><p><span data-ttu-id="c3359-183">ФИО, должность, организация, адрес электронной почты, часовой пояс</span><span class="sxs-lookup"><span data-stu-id="c3359-183">Name, Title, Company, Email Address, Time Zone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3359-184">Номера телефонов</span><span class="sxs-lookup"><span data-stu-id="c3359-184">Telephone Numbers</span></span></p></td>
<td><p><span data-ttu-id="c3359-185">Рабочий, мобильный, домашний</span><span class="sxs-lookup"><span data-stu-id="c3359-185">Work, Mobile, Home</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3359-186">Данные календаря</span><span class="sxs-lookup"><span data-stu-id="c3359-186">Calendar Information</span></span></p></td>
<td><p><span data-ttu-id="c3359-187">Доступность, уведомление об отсутствии в городе, сведения о собраниях (для пользователей, имеющих доступ к календарю)</span><span class="sxs-lookup"><span data-stu-id="c3359-187">Free/Busy, Out-Of-Town Notice, Meeting Details (to those who have access to your calendar)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3359-188">Состояние присутствия</span><span class="sxs-lookup"><span data-stu-id="c3359-188">Presence Status</span></span></p></td>
<td><p><span data-ttu-id="c3359-189">Отсутствует, доступен, занят, не беспокоить, не в сети</span><span class="sxs-lookup"><span data-stu-id="c3359-189">Away, Available, Busy, Do Not Disturb, Offline</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="mandatory-data"></a><span data-ttu-id="c3359-190">Обязательные данные</span><span class="sxs-lookup"><span data-stu-id="c3359-190">Mandatory Data</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3359-191">Раскрываемые данные</span><span class="sxs-lookup"><span data-stu-id="c3359-191">Data Disclosed</span></span></th>
<th><span data-ttu-id="c3359-192">Пример сведений</span><span class="sxs-lookup"><span data-stu-id="c3359-192">Example Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3359-193">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="c3359-193">IP Address</span></span></p></td>
<td><p><span data-ttu-id="c3359-194">Фактический адрес компьютера или адрес NAT</span><span class="sxs-lookup"><span data-stu-id="c3359-194">Actual address of computer or NATed address</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3359-195">Универсальный код ресурса SIP</span><span class="sxs-lookup"><span data-stu-id="c3359-195">SIP URI</span></span></p></td>
<td><p><span data-ttu-id="c3359-196">jeremylos@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3359-196">jeremylos@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

