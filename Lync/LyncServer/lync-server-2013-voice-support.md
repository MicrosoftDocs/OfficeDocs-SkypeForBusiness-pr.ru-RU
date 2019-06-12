---
title: 'Lync Server 2013: поддержка голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Voice support
ms:assetid: d151caa8-2ee4-4bfa-be53-428570aae1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398896(v=OCS.15)
ms:contentKeyID: 48185436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6658fa4d62445cb160bf1acbab9e40056c447b52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voice-support-in-lync-server-2013"></a><span data-ttu-id="57ce4-102">Поддержка голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ce4-102">Voice support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57ce4-103">_**Тема последнего изменения:** 2012-06-29_</span><span class="sxs-lookup"><span data-stu-id="57ce4-103">_**Topic Last Modified:** 2012-06-29_</span></span>

<span data-ttu-id="57ce4-104">Если в развертывании есть пул переднего плана, вы можете развернуть поддержку корпоративной голосовой связи — решение для передачи голоса по протоколу IP (VoIP), предлагаемое корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="57ce4-104">If your deployment includes a Front End pool, you can deploy support for Enterprise Voice, the Voice over IP (VoIP) solution offered by Microsoft.</span></span> <span data-ttu-id="57ce4-105">Голосовая связь по протоколу IP (VoIP) — это программная альтернатива обычной телефонной связи на основе УАТС.</span><span class="sxs-lookup"><span data-stu-id="57ce4-105">Voice over IP (VoIP) is a software-based alternative to traditional PBX-based telephony.</span></span> <span data-ttu-id="57ce4-106">Несмотря на то, что звонки VoIP похожи на традиционный интерфейс телефонной связи, в корпоративной голосовой связи используются функции, обеспечивающие более широкие возможности общения и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="57ce4-106">Although the VoIP call experience is similar to the traditional telephony experience, Enterprise Voice includes features that enable richer communication and collaboration.</span></span> <span data-ttu-id="57ce4-107">Например, вы можете настроить свое корпоративное развертывание для пользователей Lync 2013 и Lync Phone Edition для просмотра расширенных сведений о присутствии или сведений о расположении контактов в адресной книге организации.</span><span class="sxs-lookup"><span data-stu-id="57ce4-107">For example, your Enterprise Voice deployment can be configured to make it possible for Lync 2013 and Lync Phone Edition users to view enhanced presence information or location information for contacts in your organization’s address book.</span></span> <span data-ttu-id="57ce4-108">Некоторые функции Lync Server 2013 включены с помощью интеграции с другими рабочими нагрузками Lync Server 2013 и единой системой обмена сообщениями Exchange (UM).</span><span class="sxs-lookup"><span data-stu-id="57ce4-108">Some Lync Server 2013 features are enabled through integration with other Lync Server 2013 workloads and with Exchange Unified Messaging (UM).</span></span> <span data-ttu-id="57ce4-109">Подробные сведения о функциях и возможностях, доступных в корпоративной голосовой связи, а также о том, как планировать развертывание, приведены в разделе [планирование корпоративных голосов в Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="57ce4-109">For details about the features and functionality available with Enterprise Voice and how to plan for deployment, see [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="57ce4-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="57ce4-110">In This Section</span></span>

  - [<span data-ttu-id="57ce4-111">Поддержка распределения каналов SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ce4-111">SIP trunking support in Lync Server 2013</span></span>](lync-server-2013-sip-trunking-support.md)

  - [<span data-ttu-id="57ce4-112">Поддержка прямых SIP-подключений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ce4-112">Direct SIP connections support in Lync Server 2013</span></span>](lync-server-2013-direct-sip-connections-support.md)

  - [<span data-ttu-id="57ce4-113">Поддержка единой системы обмена сообщениями Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ce4-113">Exchange Unified Messaging (UM) support in Lync Server 2013</span></span>](lync-server-2013-exchange-unified-messaging-um-support.md)

  - [<span data-ttu-id="57ce4-114">Поддержка E9-1-1 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ce4-114">E9-1-1 support in Lync Server 2013</span></span>](lync-server-2013-e9-1-1-support.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

