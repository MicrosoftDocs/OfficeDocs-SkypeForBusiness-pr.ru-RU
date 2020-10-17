---
title: 'Lync Server 2013: развертывание удаленного управления звонками'
description: 'Lync Server 2013: развертывание удаленного управления звонками.'
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
ms.openlocfilehash: 4cc5e79f3ee44c354baf435585d304574d6a980c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566085"
---
# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="3df0f-103">Развертывание удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3df0f-103">Deploying remote call control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3df0f-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="3df0f-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="3df0f-105">В этом разделе описывается процесс развертывания функции удаленного управления вызовами для пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="3df0f-105">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3df0f-106">Хотя функции удаленного управления вызовами доступны удаленным пользователям, когда они находятся за пределами брандмауэра организации, сведения о сценариях развертывания внешнего доступа не рассматриваются в данной документации.</span><span class="sxs-lookup"><span data-stu-id="3df0f-106">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="3df0f-107">Дополнительные сведения о развертывании доступа внешних пользователей содержатся в документации по развертыванию, посвященной <A href="lync-server-2013-deploying-external-user-access.md">развертыванию доступа внешних пользователей в Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="3df0f-107">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3df0f-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="3df0f-108">In This Section</span></span>

  - [<span data-ttu-id="3df0f-109">Настройка Lync Server 2013 для маршрутизации на шлюз SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="3df0f-109">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="3df0f-110">Настройка статического маршрута для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3df0f-110">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="3df0f-111">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3df0f-111">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="3df0f-112">[Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (только в том случае, если шлюз настроен на использование TCP)</span><span class="sxs-lookup"><span data-stu-id="3df0f-112">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="3df0f-113">Включение удаленного управления звонками для пользователей Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3df0f-113">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="3df0f-114">Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3df0f-114">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="3df0f-115">[Удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (только при переносе пользователей, для которых ранее было включено удаленное управление звонками)</span><span class="sxs-lookup"><span data-stu-id="3df0f-115">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="3df0f-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3df0f-116">Related Sections</span></span>

[<span data-ttu-id="3df0f-117">Планирование удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3df0f-117">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

