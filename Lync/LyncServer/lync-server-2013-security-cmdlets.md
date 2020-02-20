---
title: 'Lync Server 2013: командлеты безопасности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b1461c006a68dff3241d859f5daf91db09e4be0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a>Командлеты безопасности в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Командлеты безопасности, включенные в Microsoft Lync Server 2013, в основном используются для управления проверкой подлинности, а также правами и разрешениями пользователей. Широкий спектр командлетов доступен для управления проверкой подлинности, включая командлеты для проверки подлинности с помощью сертификатов и персональных идентификационных номеров (ПИН-кодов). Кроме того, несколько командлетов позволяют использовать новую функцию управления доступом на основе ролей (RBAC) для делегирования административного управления Lync Server.

<div>

## <a name="security-cmdlets"></a>Командлеты обеспечения безопасности

Многие задачи управления, применимые к параметрам безопасности, можно выполнить на панели управления Lync Server. Одно главное исключение — командлеты пользовательских разрешений. Тем не менее, все задачи управления безопасностью можно выполнить с помощью командлетов в командной консоли Lync Server или из скрипта; Использование сценария позволяет автоматизировать некоторые задачи. Далее приводится список командлетов, которые непосредственно относятся к управления параметрами безопасности.

**[Командлеты сертификатов и проверки подлинности в Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  - <span></span>  
    [Get — CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - <span></span>  
    [Import — CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - <span></span>  
    [Remove — CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - <span></span>  
    [Request — CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - <span></span>  
    [Set — CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-Ксцертификатеконфигуратион](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - <span></span>  
    [REVOKE CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Lock — CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - <span></span>  
    [Set — CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - <span></span>  
    [Unlock — CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New — CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Remove — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Set — CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set — Кскерберосаккаунтпассворд](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - <span></span>  
    [Granting — CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - <span></span>  
    [New — CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Remove — CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Set — CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - <span></span>  
    [New — CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - <span></span>  
    [Remove — CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - <span></span>  
    [Set — CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New — CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - <span></span>  
    [Remove — CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - <span></span>  
    [Set — CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

**[Командлеты прав и разрешений пользователей в Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  - <span></span>  
    [Get — CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - <span></span>  
    [New — CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - <span></span>  
    [Remove — CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - <span></span>  
    [Set — CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - <span></span>  
    [Update — CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Granting — CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - <span></span>  
    [Revoke CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - <span></span>  
    [Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Granting — CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - <span></span>  
    [REVOKE CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - <span></span>  
    [Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

**[Командлеты взаимодействия в Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**

  - [Get — CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Set — CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

<!-- end list -->

  - [Get — CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [New — CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [Remove — CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Set — CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

<!-- end list -->

  - [Get — CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [New — CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Remove — CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Set — CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>См. также


[Блог Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

