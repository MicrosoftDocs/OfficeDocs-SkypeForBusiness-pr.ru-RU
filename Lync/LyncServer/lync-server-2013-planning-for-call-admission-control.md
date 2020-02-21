---
title: 'Lync Server 2013: Планирование контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19c5729989334297d4a6b368808079b0a7b0f4cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="5f870-102">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f870-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f870-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5f870-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5f870-104">Для приложений Объединенных коммуникаций (UC), использующих протокол IP, таких как телефония, видео и общий доступ к приложениям, доступная пропускная способность корпоративных сетей, как правило, не считается ограничивающим фактором в средах ЛВС.</span><span class="sxs-lookup"><span data-stu-id="5f870-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="5f870-105">Однако в каналах глобальной сети, соединяющих сайты, пропускная способность сети может быть ограничена.</span><span class="sxs-lookup"><span data-stu-id="5f870-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="5f870-106">Когда наплыва сетевого трафика записывает связь WAN, для устранения перегрузки используются текущие механизмы, такие как очередь, буферизация и удаление пакетов.</span><span class="sxs-lookup"><span data-stu-id="5f870-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="5f870-107">Дополнительный трафик обычно задерживается до тех пор, пока перегрузка сети не задерживается или при необходимости отклоняется трафик.</span><span class="sxs-lookup"><span data-stu-id="5f870-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="5f870-108">Для обычного трафика данных в таких ситуациях принимающий клиент может выполнить восстановление.</span><span class="sxs-lookup"><span data-stu-id="5f870-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="5f870-109">Для трафика в режиме реального времени, например единой системы обмена сообщениями, перегрузка сети не может быть разрешена таким образом, так как трафик единой системы обмена сообщениями зависит как от задержки, так и от потери пакетов.</span><span class="sxs-lookup"><span data-stu-id="5f870-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="5f870-110">Перегрузка WAN может привести к неудовлетворительному качеству работы (QoE) для пользователей.</span><span class="sxs-lookup"><span data-stu-id="5f870-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="5f870-111">Для трафика в режиме реального времени в перегруженных условиях лучше отклонять вызовы, а не предоставлять подключения с низким качеством.</span><span class="sxs-lookup"><span data-stu-id="5f870-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="5f870-112">Контроль допуска звонков (CAC) определяет, достаточно ли пропускной способности сети для установления сеанса в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="5f870-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="5f870-113">В Lync Server 2013 CAC управляет трафиком в режиме реального времени только для аудио и видео, но не влияет на трафик данных.</span><span class="sxs-lookup"><span data-stu-id="5f870-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="5f870-114">Если канал глобальной сети по умолчанию не имеет необходимой пропускной способности, CAC может попытаться маршрутизировать вызов через Интернет или телефонную сеть общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="5f870-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="5f870-115">CAC можно использовать только в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f870-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="5f870-116">В этом разделе описываются функции контроля допуска звонков и описано, как спланировать CAC.</span><span class="sxs-lookup"><span data-stu-id="5f870-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f870-117">Lync Server включает три расширенные функции корпоративной голосовой связи: контроль допуска звонков (CAC), экстренные службы (E9-1-1) и обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="5f870-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="5f870-118">Общие сведения о планировании, которые являются общими для всех трех этих функций, приведены в разделе <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Параметры сети для расширенных функций корпоративной голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5f870-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f870-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="5f870-119">In This Section</span></span>

  - [<span data-ttu-id="5f870-120">Обзор контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f870-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="5f870-121">Определение требований для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f870-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="5f870-122">Пример: сбор требований для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f870-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="5f870-123">Компоненты и топологии для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f870-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="5f870-124">Рекомендации по контролю допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f870-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="5f870-125">Контрольный список развертывания для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f870-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

