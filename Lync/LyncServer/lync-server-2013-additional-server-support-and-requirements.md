---
title: 'Lync Server 2013: поддержка дополнительных серверов и соответствующие требования'
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
ms.openlocfilehash: 3f111b80bc88b632ff1020f45e899f220edeb7d5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="191dc-102">Поддержка дополнительных серверов и соответствующие требования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="191dc-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="191dc-103">_**Тема последнего изменения:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="191dc-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="191dc-104">В дополнение к поддержке программного обеспечения, описанной в других разделах документации по поддержке, Lync Server 2013 имеет следующие ограничения поддержки:</span><span class="sxs-lookup"><span data-stu-id="191dc-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="191dc-105">Lync Server 2013 поддерживает систему доменных имен (DNS) и аппаратную балансировку нагрузки для конкретных ролей сервера.</span><span class="sxs-lookup"><span data-stu-id="191dc-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="191dc-106">Она также поддерживает балансировку нагрузки приложений для серверов обновлений, где это уместно.</span><span class="sxs-lookup"><span data-stu-id="191dc-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="191dc-107">Сведения о том, когда использовать каждый из них, можно найти в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="191dc-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="191dc-108">Lync Server 2013 использует протокол расширения списка рассылки (ДЛКС), чтобы развернуть списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="191dc-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="191dc-109">Этот протокол также указывает метод веб-службы, который используется для получения членства в списке рассылки.</span><span class="sxs-lookup"><span data-stu-id="191dc-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="191dc-110">Сервер Microsoft Exchange поддерживает динамические группы, которым не назначены статические члены.</span><span class="sxs-lookup"><span data-stu-id="191dc-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="191dc-111">Вместо этого они хранят запросы, которые оцениваются при разворачивании группы.</span><span class="sxs-lookup"><span data-stu-id="191dc-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="191dc-112">ДЛКС не поддерживает динамические списки рассылки.</span><span class="sxs-lookup"><span data-stu-id="191dc-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="191dc-113">Это ограничение ДЛКС распространяется на все версии Lync Server.</span><span class="sxs-lookup"><span data-stu-id="191dc-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="191dc-114">Мастер включения пользователей не поддерживает автоматическое преобразование символов, отличных от английского, в универсальный код ресурса (URI), совместимый с SIP, поэтому вы должны изменить адрес SIP вручную.</span><span class="sxs-lookup"><span data-stu-id="191dc-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="191dc-115">Для серверов с установленным антивирусным программным обеспечением ознакомьтесь со сведениями [об исключении антивирусной программы для Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) для предложенных исключений вирусов и других рекомендаций, касающихся безопасности.</span><span class="sxs-lookup"><span data-stu-id="191dc-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="191dc-116">Если вы используете IPsec, рекомендуем отключить IPsec для диапазонов портов, используемых для звуковых и видеофайлов.</span><span class="sxs-lookup"><span data-stu-id="191dc-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="191dc-117">Дополнительные сведения можно найти [в разделе исключения IPSec в Lync Server 2013](lync-server-2013-ipsec-exceptions.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="191dc-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="191dc-118">Если в вашей организации используется инфраструктура качества обслуживания (QoS), подсистема передачи мультимедиа настроена на работу в этой существующей инфраструктуре.</span><span class="sxs-lookup"><span data-stu-id="191dc-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="191dc-119">Подробные сведения о реализации QoS можно найти [в разделе Управление качеством обслуживания (QoS) в Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="191dc-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="191dc-120">Использование брандмауэра операционной системы поддерживается.</span><span class="sxs-lookup"><span data-stu-id="191dc-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="191dc-121">Lync Server 2013 управляет исключениями брандмауэра для брандмауэра операционной системы, за исключением программного обеспечения баз данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="191dc-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="191dc-122">Дополнительные сведения о требованиях брандмауэра SQL Server можно найти в документации по SQL Server.</span><span class="sxs-lookup"><span data-stu-id="191dc-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="191dc-123">Внешние интерфейсы, используемые для реализации поддержки внешних пользователей, должны находиться в отдельной подсети, а *не* в той же сети, что и внутренние интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="191dc-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="191dc-p106">Возможность XMPP сервера Lync Server 2013 была протестирована корпорацией Microsoft и поддерживается в части федеративного обмена мгновенными сообщениями с использованием Google Talk. По вопросам использования других XMPP-систем обращайтесь к сторонним поставщикам, чтобы выяснить, поддерживают ли они федерацию с Lync Server 2013, а также чтобы получить рекомендации по вопросам, связанным с устранением неполадок и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="191dc-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="191dc-126">При выпуске накопительных обновлений для Lync Server 2013: Июль 2013, Lync Server 2013 теперь поддерживает двухфакторную проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="191dc-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="191dc-127">Дополнительные сведения можно найти [в разделе двухфакторная проверка подлинности в Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="191dc-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="191dc-128">Для большинства внутренних серверов требуется тип сертификата, определенный как **открытая проверка подлинности** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="191dc-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="191dc-129">Вы должны запросить и назначить сертификат OAuth на этапе **запроса, установки и назначения сертификатов** мастером развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="191dc-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="191dc-130">Минимальный размер ключа сертификата OAuth — 1024 бит.</span><span class="sxs-lookup"><span data-stu-id="191dc-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="191dc-131">Предупреждение может выводиться, если вы запрашиваете сертификат с длиной ключа менее 2048 бит.</span><span class="sxs-lookup"><span data-stu-id="191dc-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="191dc-132">Чтобы избежать потенциальных проблем, связанных с тем, что при использовании ключа в 2048 вместо предупреждения настоятельно рекомендуется всегда использовать для сертификатов OAuth длину ключа 2048.</span><span class="sxs-lookup"><span data-stu-id="191dc-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="191dc-133">Сервер Lync Server 2013 и Microsoft Exchange Server 2010 с пакетом обновления 1 (SP1) используют поддержку алгоритмов FIPS 140-2, если операционная система Windows Server 2008 R2 настроена на использование алгоритмов FIPS 140-2 для Системная криптография.</span><span class="sxs-lookup"><span data-stu-id="191dc-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="191dc-134">Для реализации поддержки FIPS необходимо настроить каждый сервер, на котором работает Lync Server 2013, чтобы его поддерживать.</span><span class="sxs-lookup"><span data-stu-id="191dc-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="191dc-135">Подробные сведения о алгоритмах, совместимых с FIPS, и о том, как реализовать поддержку FIPS, можно найти в статье 811833 базы знаний Майкрософт: использование алгоритмов, совместимых с FIPS, для шифрования, хеширования и подписания параметров безопасности в [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)Windows XP и более поздних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="191dc-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="191dc-136">Дополнительные сведения о поддержке FIPS 140-2 и ограничениях в Exchange 2010 можно найти в [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)разделе "Exchange 2010 SP1 и поддержка алгоритмов, совместимых с FIPS".</span><span class="sxs-lookup"><span data-stu-id="191dc-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="191dc-137">Lync Server 2013 требует установки другого программного обеспечения для определенных компонентов до или во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="191dc-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="191dc-138">Это относится к программному обеспечению, которое доступно для операционной системы, загружаемого программного обеспечения и программного обеспечения, которое автоматически устанавливается во время установки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="191dc-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="191dc-139">Ниже приведен список дополнительного программного обеспечения, которое может потребоваться.</span><span class="sxs-lookup"><span data-stu-id="191dc-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="191dc-140">Обновление Windows</span><span class="sxs-lookup"><span data-stu-id="191dc-140">Windows Update</span></span>

  - <span data-ttu-id="191dc-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="191dc-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="191dc-142">Microsoft .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="191dc-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="191dc-143">Распространяемый пакет Microsoft Visual C++ 2012</span><span class="sxs-lookup"><span data-stu-id="191dc-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="191dc-144">Распространяемый пакет Microsoft Visual C++ 2012 автоматически устанавливается при установке Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="191dc-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="191dc-145">Не устанавливайте и не используйте другую версию.</span><span class="sxs-lookup"><span data-stu-id="191dc-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="191dc-146">Повторное создание распространяемого модуля URL версии 2,0</span><span class="sxs-lookup"><span data-stu-id="191dc-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="191dc-147">Windows Media Format Runtime</span><span class="sxs-lookup"><span data-stu-id="191dc-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="191dc-148">Windows PowerShell версии 3,0</span><span class="sxs-lookup"><span data-stu-id="191dc-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="191dc-149">Подключаемый модуль браузера Microsoft Silverlight 4 (Silverlight 4.0.50524.0 или новейшая версия панели управления Lync Server)</span><span class="sxs-lookup"><span data-stu-id="191dc-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="191dc-150">Средства доменных служб Active Directory</span><span class="sxs-lookup"><span data-stu-id="191dc-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="191dc-151">Некоторые из этих требований к программному обеспечению применимы только к определенным ролям и компонентам сервера.</span><span class="sxs-lookup"><span data-stu-id="191dc-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="191dc-152">Подробнее об этих требованиях к программному обеспечению можно узнать в разделе [Дополнительные требования к программному обеспечению для Lync Server 2013](lync-server-2013-additional-software-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="191dc-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

