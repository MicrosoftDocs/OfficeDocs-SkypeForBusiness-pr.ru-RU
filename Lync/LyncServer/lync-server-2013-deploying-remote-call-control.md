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
ms.openlocfilehash: 6651c9cb15322498d68fa9b6cd705b68dc601c6d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="02e9d-102">Развертывание удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e9d-102">Deploying remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02e9d-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="02e9d-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="02e9d-104">В этом разделе описывается процесс развертывания функций удаленного управления звонками для пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="02e9d-104">This section guides you through the process of deploying remote call control functionality to users in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02e9d-105">Несмотря на то что функции удаленного управления звонками доступны удаленным пользователям за пределами брандмауэра организации, сведения о развертывании внешних сценариев доступа выходят за рамки данной документации.</span><span class="sxs-lookup"><span data-stu-id="02e9d-105">Although remote call control features are available to remote users while they are outside of your organization’s firewall, details about deploying external access scenarios are beyond the scope of this documentation.</span></span> <span data-ttu-id="02e9d-106">Дополнительные сведения о развертывании внешних пользователей можно найти <A href="lync-server-2013-deploying-external-user-access.md">в разделе Развертывание внешних пользователей Access в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="02e9d-106">For details about deploying external user access, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02e9d-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="02e9d-107">In This Section</span></span>

  - [<span data-ttu-id="02e9d-108">Настройка Lync Server 2013 для маршрутизации к шлюзу SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="02e9d-108">Configuring Lync Server 2013 to route to a SIP/CSTA gateway</span></span>](lync-server-2013-configuring-lync-server-to-route-to-a-sip-csta-gateway.md)

  - [<span data-ttu-id="02e9d-109">Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e9d-109">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)

  - [<span data-ttu-id="02e9d-110">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e9d-110">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)

  - <span data-ttu-id="02e9d-111">[Определение IP-адреса шлюза SIP/кста в Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (только в том случае, если шлюз настроен на использование TCP)</span><span class="sxs-lookup"><span data-stu-id="02e9d-111">[Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md) (only if the gateway is configured to use TCP)</span></span>

  - [<span data-ttu-id="02e9d-112">Включение удаленного управления звонками для пользователей Lync в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e9d-112">Enable Lync users for remote call control in Lync Server 2013</span></span>](lync-server-2013-enable-lync-users-for-remote-call-control.md)

  - [<span data-ttu-id="02e9d-113">Удаленное управление звонками и нормализация телефонных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e9d-113">Remote call control and phone number normalization in Lync Server 2013</span></span>](lync-server-2013-remote-call-control-and-phone-number-normalization.md)

  - <span data-ttu-id="02e9d-114">[Удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (только если вы переносите пользователей, для которых уже разрешено удаленное управление звонками)</span><span class="sxs-lookup"><span data-stu-id="02e9d-114">[Remove a legacy authorized host in Lync Server 2013 (optional)](lync-server-2013-remove-a-legacy-authorized-host-optional.md) (only if you are migrating users previously enabled for remote call control)</span></span>

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="02e9d-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="02e9d-115">Related Sections</span></span>

[<span data-ttu-id="02e9d-116">Планирование удаленного управления звонком в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02e9d-116">Planning for remote call control in Lync Server 2013</span></span>](lync-server-2013-planning-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

