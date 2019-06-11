---
title: 'Lync Server 2013: возможности и функции серверов переднего плана, службы обмена мгновенными сообщениями и сведениями о присутствии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739825eed3c8a3ba8239849e0c17c449180a2d95
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="e39c1-102">Возможности и функции серверов переднего плана, службы обмена мгновенными сообщениями и сведениями о присутствии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e39c1-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e39c1-103">_**Тема последнего изменения:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="e39c1-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="e39c1-104">Серверы переднего плана обеспечивают большую функциональность Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e39c1-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="e39c1-105">Доступно два выпусков: Lync Server Enterprise Edition, предназначенный для крупных организаций, и Lync Server Standard Edition, разработанный преимущественно для малых организаций, которым требуется более мелкий аппаратный инвестемент требуется высокая доступность.</span><span class="sxs-lookup"><span data-stu-id="e39c1-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="e39c1-106">В обоих выпусках поддерживаются все рабочие нагрузки Lync Server, включая обмен мгновенными сообщениями, присутствие, Конференц-связь и корпоративный голос.</span><span class="sxs-lookup"><span data-stu-id="e39c1-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="e39c1-107">Обмен мгновенными сообщениями дает пользователям возможность общаться друг с другом в режиме реального времени со своих компьютеров, используя текстовые сообщения.</span><span class="sxs-lookup"><span data-stu-id="e39c1-107">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages.</span></span> <span data-ttu-id="e39c1-108">Поддерживаются как двухсторонние, так и многосторонние сеансы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e39c1-108">Both two-party and multiparty IM sessions are supported.</span></span> <span data-ttu-id="e39c1-109">Участник двухсторонней текстовой беседы может в любое время пригласить третьего участника.</span><span class="sxs-lookup"><span data-stu-id="e39c1-109">A participant in a two-party IM conversation can add a third participant to the conversation at any time.</span></span> <span data-ttu-id="e39c1-110">Когда это происходит, окно беседы изменяется, чтобы поддерживать функции конференции.</span><span class="sxs-lookup"><span data-stu-id="e39c1-110">When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e39c1-111">Клиенты Lync и Communicator, вовлеченные в одну и ту же связь, часто называют одноранговой.</span><span class="sxs-lookup"><span data-stu-id="e39c1-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="e39c1-112">Технически, эти два клиента взаимодействуют между собой в одном сеансе, с помощью управляющего блока обмена мгновенными сообщениями (ИММКУ) в центре.</span><span class="sxs-lookup"><span data-stu-id="e39c1-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="e39c1-113">ИММКУ является компонентом сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="e39c1-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="e39c1-114">Размещение ИММКУ в требуемом рабочем канале связи позволяет записывать сведения о вызове и другие возможности, которые сервер переднего плана включит.</span><span class="sxs-lookup"><span data-stu-id="e39c1-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="e39c1-115">Взаимодействие осуществляется из динамического исходного порта на клиенте на серверный порт TLS/TCP/5061 (предполагается использование рекомендуемой безопасности транспортного уровня).</span><span class="sxs-lookup"><span data-stu-id="e39c1-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="e39c1-116">Связь между одноранговым и одноранговой связью (а также многосторонним СООБЩЕНИЕм) возможна только в том случае, если Lync Server и ИММКУ активны и доступны.</span><span class="sxs-lookup"><span data-stu-id="e39c1-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="e39c1-117">\*\* Сведения о присутствии предоставляют пользователям информацию о состоянии другого в сети.</span><span class="sxs-lookup"><span data-stu-id="e39c1-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="e39c1-118">Информация о состоянии присутствия пользователя помогает другим пользователям решить, когда следует связаться с этим пользователем, и что лучше использовать – обмен мгновенными сообщениями, телефон или электронную почту.</span><span class="sxs-lookup"><span data-stu-id="e39c1-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="e39c1-119">Функция присутствия предлагает обмен мгновенными сообщениями всегда, когда это возможно, но также сообщает, когда пользователь находится на собрании или вне офиса, указывая, что обмен мгновенными сообщениями невозможен.</span><span class="sxs-lookup"><span data-stu-id="e39c1-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="e39c1-120">Это состояние присутствия отображается как значок присутствия в Lync и другие приложения, поддерживающие присутствие, в том числе клиент Microsoft Outlook для обмена сообщениями и совместной работы, технологии Microsoft SharePoint, Microsoft Word и электронная таблица Microsoft Excel. программах.</span><span class="sxs-lookup"><span data-stu-id="e39c1-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="e39c1-121">Значок присутствия указывает текущую доступность пользователя и готовность к общению.</span><span class="sxs-lookup"><span data-stu-id="e39c1-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

