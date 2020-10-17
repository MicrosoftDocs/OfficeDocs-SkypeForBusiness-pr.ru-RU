---
title: 'Lync Server 2013: интеграция единой системы обмена сообщениями Exchange Hosted'
description: 'Lync Server 2013: интеграция единой системы обмена сообщениями Exchange Hosted Exchange.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Unified Messaging integration
ms:assetid: f4de0165-da3b-499e-98fc-28ddd0db02d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413027(v=OCS.15)
ms:contentKeyID: 48185829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 980c0bc47258e9fae94ff623559342ca36eea145
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550125"
---
# <a name="hosted-exchange-unified-messaging-integration-in-lync-server-2013"></a><span data-ttu-id="dd7c9-103">Интеграция единой системы обмена сообщениями Exchange в среде Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd7c9-103">Hosted Exchange Unified Messaging integration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd7c9-104">_**Последнее изменение темы:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="dd7c9-104">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="dd7c9-105">Помимо поддержки предыдущих выпусков Lync Server 2013 для интеграции с *локальными* развертываниями единой системы обмена сообщениями Exchange, Lync Server 2013 предоставляет поддержку интеграции с *размещенной* единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="dd7c9-105">In addition to the support that previous Lync Server 2013 releases have provided for integration with *on-premises* deployments of Exchange Unified Messaging (UM), Lync Server 2013 introduces support for integration with *hosted* Exchange UM.</span></span> <span data-ttu-id="dd7c9-106">Размещенная единая система обмена сообщениями Exchange позволяет Lync Server 2013 предоставлять пользователям голосовые сообщения, если вы переносите их на размещенный поставщик услуг Exchange, такой как Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dd7c9-106">Hosted Exchange UM enables Lync Server 2013 to provide voice messaging to your users if you transfer some or all of them to a hosted Exchange service provider such as Microsoft Exchange Online.</span></span>

<span data-ttu-id="dd7c9-107">Lync Server 2013 Enterprise Voice использует инфраструктуру единой системы обмена сообщениями Exchange для предоставления автоответчика, уведомления о вызовах, голосового доступа (в том числе голосовой почты) и служб автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="dd7c9-107">Lync Server 2013 Enterprise Voice uses the Exchange UM infrastructure to provide call answering, call notification, voice access (including voice mail), and auto attendant services.</span></span> <span data-ttu-id="dd7c9-108">Дополнительные сведения: [функции интегрированной единой системы обмена сообщениями и Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="dd7c9-108">For details, see [Features of integrated Unified Messaging and Lync Server 2013](lync-server-2013-features-of-integrated-unified-messaging.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd7c9-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="dd7c9-109">In This Section</span></span>

  - [<span data-ttu-id="dd7c9-110">Архитектура и маршрутизация размещенной единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd7c9-110">Hosted Exchange UM architecture and routing in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-um-architecture-and-routing.md)

  - [<span data-ttu-id="dd7c9-111">Политики размещенной голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd7c9-111">Hosted voice mail policies in Lync Server 2013</span></span>](lync-server-2013-hosted-voice-mail-policies.md)

  - [<span data-ttu-id="dd7c9-112">Управление пользователями размещенного сервера Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd7c9-112">Hosted Exchange user management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-user-management.md)

  - [<span data-ttu-id="dd7c9-113">Управление объектом контакта размещенного сервера Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd7c9-113">Hosted Exchange Contact object management in Lync Server 2013</span></span>](lync-server-2013-hosted-exchange-contact-object-management.md)

  - [<span data-ttu-id="dd7c9-114">Процесс развертывания для интеграции размещенной единой системы обмена сообщениями Exchange с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd7c9-114">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-integrating-hosted-exchange-um.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

