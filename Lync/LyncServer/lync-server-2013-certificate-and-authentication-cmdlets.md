---
title: 'Lync Server 2013: командлеты сертификатов и проверки подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate and authentication cmdlets
ms:assetid: ebb51778-3558-49d2-8343-d83e7a731559
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg415680(v=OCS.15)
ms:contentKeyID: 48185711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe4ff4a1def96863b9586f65be5435e296da453b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-and-authentication-cmdlets-in-lync-server-2013"></a><span data-ttu-id="89f8d-102">Командлеты сертификатов и проверки подлинности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89f8d-102">Certificate and authentication cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89f8d-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="89f8d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="89f8d-104">Командлеты сертификатов и проверки подлинности охватывают широкий диапазон задач, включая управление сертификатами сервера и клиента, управление ПИН-кодами (персональными идентификационными номерами) пользователей и управление доменами SIP и учетными записями Kerberos, используемыми в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="89f8d-104">The certificate and authentication cmdlets cover a wide range of tasks, including the management of server and client certificates; the management of user PINs (personal identification numbers); and the management of both SIP domains and the Kerberos accounts used with Internet Information Services.</span></span>

<div>

## <a name="certificate-and-authentication-cmdlets"></a><span data-ttu-id="89f8d-105">Командлеты сертификатов и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="89f8d-105">Certificate and Authentication Cmdlets</span></span>

<span data-ttu-id="89f8d-106">Далее приводится список командлетов, имеющих прямое отношение к управлению сертификатами и проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="89f8d-106">The following is a list of cmdlets that relate directly to managing certificates and authentication:</span></span>

<span data-ttu-id="89f8d-107">**Сертификаты и проверка подлинности**</span><span class="sxs-lookup"><span data-stu-id="89f8d-107">**Certificates and Authentication**</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-108">[Get — CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-108">[Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-109">[Import — CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-109">[Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-110">[Remove — CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-110">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-111">[Request — CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-111">[Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-112">[Set — CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-112">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-113">[Test-Ксцертификатеконфигуратион](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-113">[Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-114">[Get — CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-114">[Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-115">[REVOKE CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-115">[Revoke-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-116">[Lock — CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-116">[Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-117">[Set — CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-117">[Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-118">[Unlock — CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-118">[Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-119">[Get — CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-119">[Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-120">[New — CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-120">[New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-121">[Get — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-121">[Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-122">[New — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-122">[New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-123">[Remove — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-123">[Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-124">[Set — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-124">[Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-125">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-125">[Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-126">[Set — Кскерберосаккаунтпассворд](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-126">[Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-127">[Get — CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-127">[Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-128">[Granting — CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-128">[Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-129">[New — CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-129">[New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-130">[Remove — CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-130">[Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-131">[Set — CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-131">[Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-132">[Get — CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-132">[Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-133">[New — CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-133">[New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-134">[Remove — CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-134">[Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-135">[Set — CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-135">[Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))</span></span>

<!-- end list -->

  - <span></span>  
    <span data-ttu-id="89f8d-136">[Get — CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-136">[Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-137">[New — CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-137">[New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-138">[Remove — CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-138">[Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))</span></span>

  - <span></span>  
    <span data-ttu-id="89f8d-139">[Set — CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="89f8d-139">[Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89f8d-140">См. также</span><span class="sxs-lookup"><span data-stu-id="89f8d-140">See Also</span></span>


[<span data-ttu-id="89f8d-141">Блог Lync Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="89f8d-141">Lync Server PowerShell Blog</span></span>](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

