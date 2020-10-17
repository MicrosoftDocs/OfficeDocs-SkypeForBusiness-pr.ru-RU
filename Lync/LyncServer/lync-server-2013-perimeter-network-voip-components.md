---
title: 'Lync Server 2013: компоненты VoIP для сети периметра'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Perimeter network VoIP components
ms:assetid: 74230008-695d-436a-90b9-9cd060c70f7b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398559(v=OCS.15)
ms:contentKeyID: 48184514
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16c823d290c52f91d8a25e2b9f76c36bf54c9145
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524336"
---
# <a name="perimeter-network-voip-components-for-lync-server-2013"></a><span data-ttu-id="76f32-102">Компоненты VoIP для сети периметра для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76f32-102">Perimeter network VoIP components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76f32-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="76f32-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="76f32-104">Внешние абоненты, использующие единые клиенты связи для отдельных вызовов или конференций, основываются на пограничном сервере для голосовой связи с коллегами.</span><span class="sxs-lookup"><span data-stu-id="76f32-104">Outside callers who use unified communications clients for individual or conference calls rely on Edge Server for voice communication with coworkers.</span></span>

<span data-ttu-id="76f32-105">На пограничном сервере служба пограничного доступа предоставляет сигналы SIP для вызовов от пользователей Lync, находящихся за прев брандмауэре организации.</span><span class="sxs-lookup"><span data-stu-id="76f32-105">On an Edge Server, the Access Edge service provides SIP signaling for calls from Lync users who are outside your organization’s firewall.</span></span> <span data-ttu-id="76f32-106">Служба A/V Edge обеспечивает обход NAT и брандмауэров.</span><span class="sxs-lookup"><span data-stu-id="76f32-106">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="76f32-107">Абонент, использующий унифицированный коммуникационный клиент (UC) за пределами корпоративного брандмауэра, применяет службу для выполнения индивидуальных вызовов или конференц-вызовов.</span><span class="sxs-lookup"><span data-stu-id="76f32-107">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>

<span data-ttu-id="76f32-p102">Служба проверки подлинности аудио и видео связана с пограничной службой аудио- и видеоданных и предоставляет услуги проверки подлинности. Внешним пользователям, которые пытаются подключиться к пограничной службе аудио- и видеоданных, требуется маркер проверки подлинности, предоставляемый службой проверки подлинности аудио и видео, для прохождения вызовов.</span><span class="sxs-lookup"><span data-stu-id="76f32-p102">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

