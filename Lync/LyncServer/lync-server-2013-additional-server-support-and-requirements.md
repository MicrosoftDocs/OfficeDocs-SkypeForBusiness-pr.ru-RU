---
title: 'Lync Server 2013: дополнительная поддержка и требования к серверу'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fa21b481d58d149bcc4c8189e210dfc23647a673
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="b3f51-102">Дополнительная поддержка и требования к серверу в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3f51-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3f51-103">_**Последнее изменение темы:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="b3f51-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="b3f51-104">В дополнение к поддержке программного обеспечения, описанной в других разделах этой документации по поддержке, Lync Server 2013 имеет следующие ограничения поддержки:</span><span class="sxs-lookup"><span data-stu-id="b3f51-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="b3f51-105">Lync Server 2013 поддерживает систему доменных имен (DNS) и аппаратную балансировку нагрузки для определенных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="b3f51-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="b3f51-106">Он также поддерживает балансировку нагрузки приложений для серверов-посредников, когда это целесообразно.</span><span class="sxs-lookup"><span data-stu-id="b3f51-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="b3f51-107">Подробные сведения о том, когда уместно использование этих видов балансировки нагрузки, см. в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b3f51-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="b3f51-108">Lync Server 2013 использует протокол расширения списка рассылки (ДЛКС), чтобы развернуть списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="b3f51-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="b3f51-109">Этот протокол также указывает метод веб-службы, используемый для получения членства списка рассылки.</span><span class="sxs-lookup"><span data-stu-id="b3f51-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="b3f51-110">Microsoft Exchange Server поддерживает динамические группы, которым не назначены статические члены.</span><span class="sxs-lookup"><span data-stu-id="b3f51-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="b3f51-111">Эти группы хранят запросы, которые оцениваются при разворачивании группы.</span><span class="sxs-lookup"><span data-stu-id="b3f51-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="b3f51-112">Протокол DLX не поддерживает динамические списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="b3f51-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="b3f51-113">Это ограничение ДЛКС применяется ко всем версиям Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3f51-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="b3f51-114">Мастер включения пользователя не поддерживает автоматическое преобразование символов, не входящих в английский язык, в URI, совместимый с SIP, поэтому необходимо изменять SIP-адрес вручную.</span><span class="sxs-lookup"><span data-stu-id="b3f51-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="b3f51-115">Для серверов, на которых работает антивирусное программное обеспечение, обратитесь к разделу [исключения сканирования антивирусной программы для Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) для предлагаемых исключений и других рекомендаций по обеспечению безопасности.</span><span class="sxs-lookup"><span data-stu-id="b3f51-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="b3f51-116">Если вы используете набор протоколов IPsec, мы рекомендуем отключить его для диапазона портов, используемого для аудио- и видеотрафика.</span><span class="sxs-lookup"><span data-stu-id="b3f51-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="b3f51-117">Дополнительные сведения см. [в статье исключения IPSec в Lync Server 2013](lync-server-2013-ipsec-exceptions.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b3f51-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="b3f51-118">Если в вашей организации используется инфраструктура качества обслуживания (QoS), подсистема передачи мультимедиа настроена на работу в этой существующей инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="b3f51-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="b3f51-119">Подробные сведения о реализации QoS приведены в статье [Управление качеством обслуживания (QoS) в Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="b3f51-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="b3f51-120">Поддерживается использование брандмауэра операционной системы.</span><span class="sxs-lookup"><span data-stu-id="b3f51-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="b3f51-121">Lync Server 2013 управляет исключениями брандмауэра для брандмауэра операционной системы, за исключением программного обеспечения базы данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3f51-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="b3f51-122">Подробные сведения о требованиях к брандмауэру SQL Server см. в документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b3f51-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="b3f51-123">Внешние интерфейсы, используемые для реализации поддержки доступа внешних пользователей, должны находиться в отдельной подсети, *не* в одной сети со внутренними интерфейсами.</span><span class="sxs-lookup"><span data-stu-id="b3f51-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="b3f51-124">Функция XMPP Lync Server 2013 тестируется и поддерживается корпорацией Майкрософт для федерации обмена мгновенными сообщениями с Google говорите.</span><span class="sxs-lookup"><span data-stu-id="b3f51-124">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="b3f51-125">Для любой другой системы XMPP обратитесь к сторонним поставщикам, чтобы убедиться, что они поддерживают Федерацию с Lync Server 2013, а также рекомендации по развертыванию и устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="b3f51-125">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="b3f51-126">С выпуском накопительных обновлений Lync Server 2013:2013 июля, Lync Server 2013 теперь поддерживает двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="b3f51-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="b3f51-127">Для получения дополнительных сведений см [в статье двухфакторную проверку подлинности в Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b3f51-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="b3f51-128">Для большинства внутренних серверов требуется тип сертификата **Open Authentication** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="b3f51-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="b3f51-129">Вы должны запросить и назначить сертификат OAuth на этапе **запроса, установки и назначения сертификатов** в мастере развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3f51-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="b3f51-130">Минимальный размер ключа сертификата OAuth — 1024 разрядов.</span><span class="sxs-lookup"><span data-stu-id="b3f51-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="b3f51-131">Если запросить сертификат с длиной ключа меньше 2048 разрядов, может появиться предупреждение.</span><span class="sxs-lookup"><span data-stu-id="b3f51-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="b3f51-132">Чтобы избежать потенциальных проблем в случае принудительного применения 2048-разрядного ключа, настоятельно рекомендуется всегда использовать 2048-разрядные ключи для сертификатов OAuth.</span><span class="sxs-lookup"><span data-stu-id="b3f51-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="b3f51-133">Lync Server 2013 и Microsoft Exchange Server 2010 с пакетом обновления 1 (SP1) работают с поддержкой алгоритмов федерального стандарта обработки информации (FIPS) 140-2, если операционные системы Windows Server 2008 R2 настроены для использования алгоритмов FIPS 140-2 для Системная криптография.</span><span class="sxs-lookup"><span data-stu-id="b3f51-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="b3f51-134">Для реализации поддержки FIPS необходимо настроить каждый сервер, на котором работает Lync Server 2013, для его поддержки.</span><span class="sxs-lookup"><span data-stu-id="b3f51-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="b3f51-135">Дополнительные сведения о алгоритмах, совместимых с FIPS, и о том, как реализовать поддержку FIPS, можно найти в статье базы знаний Майкрософт 811833 "Системная криптография: использование FIPS-совместимых алгоритмов для шифрования, хеширования и подписания [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)параметров безопасности в Windows XP и более поздних версиях Windows по адресу.</span><span class="sxs-lookup"><span data-stu-id="b3f51-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="b3f51-136">Подробные сведения о поддержке FIPS 140-2 и ограничениях в Exchange 2010 приведены в разделе "Exchange 2010 SP1 и поддержка алгоритмов, совместимых с FIPS" [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span><span class="sxs-lookup"><span data-stu-id="b3f51-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="b3f51-137">Lync Server 2013 требует установки другого программного обеспечения на определенных компонентах до или во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="b3f51-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="b3f51-138">Это включает программное обеспечение, которое доступно в операционной системе, загружаемом программном обеспечении и программном обеспечении, которое автоматически устанавливается во время установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3f51-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="b3f51-139">Далее приводится список дополнительного ПО, которое может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="b3f51-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="b3f51-140">Обновление Windows</span><span class="sxs-lookup"><span data-stu-id="b3f51-140">Windows Update</span></span>

  - <span data-ttu-id="b3f51-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b3f51-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="b3f51-142">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b3f51-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="b3f51-143">Распространяемый компонент Microsoft Visual C++ 2012</span><span class="sxs-lookup"><span data-stu-id="b3f51-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b3f51-144">Распространяемый пакет Microsoft Visual C++ 2012 автоматически устанавливается при установке Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b3f51-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="b3f51-145">Не следует устанавливать и использовать никакую другую версию.</span><span class="sxs-lookup"><span data-stu-id="b3f51-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="b3f51-146">Распространяемая версия модуля переопределения URL-адресов 2.0</span><span class="sxs-lookup"><span data-stu-id="b3f51-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="b3f51-147">Windows Media Format Runtime</span><span class="sxs-lookup"><span data-stu-id="b3f51-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="b3f51-148">Windows PowerShell версии 3.0</span><span class="sxs-lookup"><span data-stu-id="b3f51-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="b3f51-149">Подключаемый модуль браузера Microsoft Silverlight 4 (Silverlight 4.0.50524.0 или последующие версии для панели управления Lync Server)</span><span class="sxs-lookup"><span data-stu-id="b3f51-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="b3f51-150">Средства доменных служб Active Directory</span><span class="sxs-lookup"><span data-stu-id="b3f51-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="b3f51-151">Некоторые из этих требований к программному обеспечению относятся только к определенным ролям сервера или компонентам.</span><span class="sxs-lookup"><span data-stu-id="b3f51-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="b3f51-152">Сведения о требованиях к программному обеспечению приведены в разделе [Дополнительные требования к программному обеспечению для Lync Server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b3f51-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

