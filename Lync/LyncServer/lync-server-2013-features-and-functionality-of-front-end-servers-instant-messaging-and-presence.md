---
title: 'Lync Server 2013: функции и функции серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии'
description: 'Lync Server 2013: функции и функции серверов переднего плана, обмена мгновенными сообщениями и сведений о присутствии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5c8bc3db255228da3366eb5aa142cd5adc233d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543415"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="9cb17-103">Функции и функции серверов переднего плана, обмена мгновенными сообщениями и присутствия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cb17-103">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cb17-104">_**Последнее изменение темы:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="9cb17-104">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="9cb17-105">Серверы переднего плана обеспечивают большинство функций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9cb17-105">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="9cb17-106">Доступно два выпуска: Lync Server Enterprise Edition, предназначенный в основном для крупных организаций, и Lync Server Standard Edition, предназначенных в основном для небольших организаций, которым требуется меньше аппаратного инвестемент и не требующего высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="9cb17-106">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="9cb17-107">Оба выпуска поддерживают все рабочие нагрузки Lync Server, в том числе обмен мгновенными сообщениями, присутствие, Конференц-связь и корпоративную голосовую связь.</span><span class="sxs-lookup"><span data-stu-id="9cb17-107">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="9cb17-p102">Обмен мгновенными сообщениями дает пользователям возможность общаться друг с другом в режиме реального времени со своих компьютеров, используя текстовые сообщения. Поддерживаются как двухсторонние, так и многосторонние сеансы обмена мгновенными сообщениями. Участник двухсторонней текстовой беседы может в любое время пригласить третьего участника. Когда это происходит, окно беседы изменяется, чтобы поддерживать функции конференции.</span><span class="sxs-lookup"><span data-stu-id="9cb17-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9cb17-112">Клиенты Lync и Communicator, участвующие в одном обмене данными, часто называют одноранговыми узлами.</span><span class="sxs-lookup"><span data-stu-id="9cb17-112">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="9cb17-113">С технической точки зрения два клиента взаимодействуют в одном сеансе, с помощью модуля управления мгновенными сообщениями MultiPoint (ИММКУ) в центре.</span><span class="sxs-lookup"><span data-stu-id="9cb17-113">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="9cb17-114">ИММКУ — это компонент сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9cb17-114">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="9cb17-115">Размещение ИММКУ в требуемом рабочем канале связи позволяет записывать сведения о вызовах и другие функции, которые обеспечивает сервер переднего плана.</span><span class="sxs-lookup"><span data-stu-id="9cb17-115">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="9cb17-116">Обмен данными осуществляется от динамического исходного порта на клиенте к порту TLS/TCP/5061 (при условии использования рекомендуемой безопасности транспортного уровня).</span><span class="sxs-lookup"><span data-stu-id="9cb17-116">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="9cb17-117">Одноранговая связь (а также поддержка обмена мгновенными сообщениями) возможна только в том случае, если Lync Server и ИММКУ активны и доступны.</span><span class="sxs-lookup"><span data-stu-id="9cb17-117">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="9cb17-118">*Функция присутствия* предоставляют пользователям информацию о состоянии других пользователей в сети.</span><span class="sxs-lookup"><span data-stu-id="9cb17-118">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="9cb17-119">Информация о состоянии присутствия пользователя помогает другим пользователям решить, когда следует связаться с этим пользователем, и что лучше использовать — обмен мгновенными сообщениями, телефон или электронную почту.</span><span class="sxs-lookup"><span data-stu-id="9cb17-119">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="9cb17-120">Функция присутствия предлагает обмен мгновенными сообщениями всегда, когда это возможно, но также сообщает, когда пользователь находится на собрании или вне офиса, указывая, что обмен мгновенными сообщениями невозможен.</span><span class="sxs-lookup"><span data-stu-id="9cb17-120">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="9cb17-121">Этот статус присутствия отображается в виде значка присутствия в Lync и других приложений, поддерживающих присутствие, в том числе клиента для обмена сообщениями и совместной работы Microsoft Outlook, технологий Microsoft SharePoint, Microsoft Word и электронных таблиц Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="9cb17-121">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="9cb17-122">Значок присутствия указывает текущую доступность пользователя и готовность к общению.</span><span class="sxs-lookup"><span data-stu-id="9cb17-122">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

