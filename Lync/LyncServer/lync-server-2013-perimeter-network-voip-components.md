---
title: 'Lync Server 2013: компоненты VoIP для сети периметра'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 605cee3c683ea9b22998de6c218978954907ca52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="932f9-102">Компоненты VoIP для сети периметра для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="932f9-102">Perimeter network VoIP components for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="932f9-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="932f9-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="932f9-104">За пределами абонентов, использующих единые коммуникационные клиенты для индивидуальных и конференц-связи, на пограничном сервере подается пограничный голосовую связь с коллегами.</span><span class="sxs-lookup"><span data-stu-id="932f9-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="932f9-105">На пограничном сервере служба доступа Edge предоставляет сигналы SIP для звонков из пользователей Lync, которые находятся за пределами брандмауэра организации.</span><span class="sxs-lookup"><span data-stu-id="932f9-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="932f9-106">Пограничная служба аудио- и видеоданных обеспечивает обход трансляторов сетевых адресов и брандмауэров.</span><span class="sxs-lookup"><span data-stu-id="932f9-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="932f9-107">Вызывающий абонент, работающий с клиентом объединенных коммуникаций (UC) за пределами корпоративного брандмауэра, пользуется пограничной службой аудио- и видеоданных как для индивидуальных вызовов, так и для вызовов конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="932f9-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="932f9-p102">Служба проверки подлинности аудио и видео связана с пограничной службой аудио- и видеоданных и предоставляет услуги проверки подлинности. Внешним пользователям, которые пытаются подключиться к пограничной службе аудио- и видеоданных, требуется маркер проверки подлинности, предоставляемый службой проверки подлинности аудио и видео, для прохождения вызовов.</span><span class="sxs-lookup"><span data-stu-id="932f9-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

