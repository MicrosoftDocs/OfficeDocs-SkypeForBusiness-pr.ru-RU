---
title: Lync Server 2013 — поддержка инфраструктуры сертификатов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56582d57400bb59e55978caf67a6b957fc91f47d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a><span data-ttu-id="875cd-102">Поддержка инфраструктуры сертификатов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="875cd-102">Certificate infrastructure support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="875cd-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="875cd-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="875cd-104">Для Lync Server 2013 требуется инфраструктура открытых ключей (PKI), поддерживающая подключения TLS и взаимное TLS (MTLS).</span><span class="sxs-lookup"><span data-stu-id="875cd-104">Lync Server 2013 requires a public key infrastructure (PKI) to support Transport Layer Security (TLS) and mutual TLS (MTLS) connections.</span></span> <span data-ttu-id="875cd-105">По умолчанию Lync Server 2013 настроен для использования протокола TLS для подключений между серверами.</span><span class="sxs-lookup"><span data-stu-id="875cd-105">By default, Lync Server 2013 is configured to use TLS for client-to-server connections.</span></span> <span data-ttu-id="875cd-106">MTLS используется в подключениях между серверами.</span><span class="sxs-lookup"><span data-stu-id="875cd-106">MTLS is used for connections between servers.</span></span>

<span data-ttu-id="875cd-107">Сертификаты MTLS должны выдаваться доверенными центрами сертификации (CAs) для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="875cd-107">MTLS certificates must be issued by trusted certification authorities (CAs) for Lync Server 2013.</span></span> <span data-ttu-id="875cd-108">Lync Server поддерживает сертификаты, выданные из следующих ЦС:</span><span class="sxs-lookup"><span data-stu-id="875cd-108">Lync Server supports certificates that are issued from the following CAs:</span></span>

  - <span data-ttu-id="875cd-109">Сертификаты, выданные внутренним ЦС:</span><span class="sxs-lookup"><span data-stu-id="875cd-109">Certificates issued from an internal CA:</span></span>
    
      - <span data-ttu-id="875cd-110">ЦС операционной системы Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="875cd-110">The Windows Server 2003 operating system CA</span></span>
    
      - <span data-ttu-id="875cd-111">ЦС операционной системы Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="875cd-111">The Windows Server 2008 operating system CA</span></span>
    
      - <span data-ttu-id="875cd-112">ЦС операционной системы Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="875cd-112">The Windows Server 2008 R2 operating system CA</span></span>
    
      - <span data-ttu-id="875cd-113">ЦС операционной системы Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="875cd-113">The Windows Server 2012 operating system CA</span></span>
    
      - <span data-ttu-id="875cd-114">ЦС операционной системы Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="875cd-114">The Windows Server 2012 R2 operating system CA</span></span>

  - <span data-ttu-id="875cd-115">Сертификаты, выданные общедоступным ЦС.</span><span class="sxs-lookup"><span data-stu-id="875cd-115">Certificates issued from a public CA</span></span>

<span data-ttu-id="875cd-116">Для связи с другими приложениями и серверами, например Exchange 2013, необходим сертификат, который поддерживается другими приложениями и продуктами.</span><span class="sxs-lookup"><span data-stu-id="875cd-116">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="875cd-117">Для выпусков 2013, Lync Server 2013 и других серверных продуктов Майкрософт, в том числе Exchange 2013 и SharePoint Server, поддерживается протокол OAuth для проверки подлинности и авторизации "сервер-сервер".</span><span class="sxs-lookup"><span data-stu-id="875cd-117">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="875cd-118">Дополнительные сведения: [Управление проверкой подлинности между серверами (OAuth) и партнерских приложений в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) в документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="875cd-118">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="875cd-119">Для подключений клиентов, работающих под управлением операционной системы Windows 7, Windows Server 2008 R2 и Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 включает поддержку (но не обязательно) сертификатов, подписанных с помощью SHA-256 криптографическая хэш-функция.</span><span class="sxs-lookup"><span data-stu-id="875cd-119">For connections from clients running Windows 7 operating system, Windows Server 2008 R2 operating system, and Microsoft Office Communicator 2007 Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="875cd-120">Для поддержки внешнего доступа с использованием SHA-256 внешний сертификат выдается общедоступным ЦС с использованием SHA-256.</span><span class="sxs-lookup"><span data-stu-id="875cd-120">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="875cd-121">Сведения о требованиях к сертификатам приведены в статье [требования к инфраструктуре сертификатов для Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="875cd-121">For details about certificate requirements, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="875cd-122">Для получения подробных сведений об использовании подстановочных знаков с сертификатами, обратитесь к разделу [Поддержка сертификатов с помощью подстановочных знаков в Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="875cd-122">For details about use of wildcards with certificates, see [Wildcard certificate support in Lync Server 2013](lync-server-2013-wildcard-certificate-support.md) in the Supportability documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

