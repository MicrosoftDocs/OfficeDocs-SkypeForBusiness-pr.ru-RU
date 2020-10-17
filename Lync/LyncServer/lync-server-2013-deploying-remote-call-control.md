---
title: 'Lync Server 2013: развертывание удаленного управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying remote call control
ms:assetid: 763037f7-7a2a-49ae-acc3-9781b0bff7e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558664(v=OCS.15)
ms:contentKeyID: 48184536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d4e388898b36f2eae913a5c34e11119cf95402a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520036"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="93a8b-102">Развертывание удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93a8b-102">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93a8b-103">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="93a8b-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="93a8b-104">В этом разделе описывается процесс развертывания функции удаленного управления вызовами для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="93a8b-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93a8b-105">Хотя функции удаленного управления вызовами доступны удаленным пользователям, когда они находятся за пределами брандмауэра организации, сведения о сценариях развертывания внешнего доступа не рассматриваются в данной документации.</span><span class="sxs-lookup"><span data-stu-id="93a8b-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="93a8b-106">Дополнительные сведения о развертывании доступа внешних пользователей содержатся в документации по развертыванию, посвященной <A href="lync-server-2013-deploying-external-user-access.md">развертыванию доступа внешних пользователей в Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="93a8b-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="93a8b-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="93a8b-107">In This Section</span></span>

  - [<span data-ttu-id="93a8b-108">Настройка Lync Server 2013 для маршрутизации на шлюз SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="93a8b-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="93a8b-109">Настройка статического маршрута для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93a8b-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="93a8b-110">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93a8b-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="93a8b-111">[Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (только в том случае, если шлюз настроен на использование TCP)</span><span class="sxs-lookup"><span data-stu-id="93a8b-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="93a8b-112">Включение удаленного управления звонками для пользователей Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93a8b-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="93a8b-113">Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93a8b-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="93a8b-114">[Удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (только при переносе пользователей, для которых ранее было включено удаленное управление звонками)</span><span class="sxs-lookup"><span data-stu-id="93a8b-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="93a8b-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="93a8b-115">Related Sections</span></span>

[<span data-ttu-id="93a8b-116">Планирование удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93a8b-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

