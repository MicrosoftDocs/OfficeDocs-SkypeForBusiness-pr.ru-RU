---
title: 'Lync Server 2013: планирование контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1af07a3f0b067f4dae3835c682cb51e6fefdcf21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="2d2b6-102">Планирование контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2b6-102">Planning for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d2b6-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2d2b6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2d2b6-104">Для приложений Объединенных коммуникаций (UC), использующих протокол IP, таких как телефония, видео и общий доступ к приложениям, доступная пропускная способность сетей предприятий, как правило, не рассматривается как ограничивающий фактор в среде ЛВС.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-104">For unified communications (UC) applications that are IP-based, such as telephony, video, and application sharing, the available bandwidth of enterprise networks is not generally considered to be a limiting factor within LAN environments.</span></span> <span data-ttu-id="2d2b6-105">Однако на WAN-каналах, которые соединяют узлы, пропускная полоса сети может быть ограничена.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-105">However, on WAN links that interconnect sites, network bandwidth can be limited.</span></span> <span data-ttu-id="2d2b6-106">Когда инфлукс сетевой трафик переписывается на ГЛОБАЛЬную ссылку, для устранения перегрузки используются текущие механизмы, такие как очередь, буферизация и сбрасывание пакетов.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-106">When an influx of network traffic oversubscribes a WAN link, current mechanisms such as queuing, buffering, and packet dropping are used to resolve the congestion.</span></span> <span data-ttu-id="2d2b6-107">Дополнительный трафик, как правило, задерживается, пока перегрузка сети не будет устранена или, при необходимости, пока трафик не будет отброшен.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-107">The extra traffic is typically delayed until the network congestion eases or, if necessary, the traffic is dropped.</span></span> <span data-ttu-id="2d2b6-108">Для обычного трафика данных в подобных ситуациях принимающий клиент может восстановиться.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-108">For conventional data traffic in such situations, the receiving client can recover.</span></span> <span data-ttu-id="2d2b6-109">Для трафика в реальном времени, такого как единая связь, перегрузка сети не может быть разрешена таким образом, так как трафик единой системы обмена сообщениями чувствителен к задержке и потере пакетов.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-109">For real-time traffic such as unified communications, network congestion cannot be resolved in this manner, because the unified communications traffic is sensitive to both latency and packet loss.</span></span> <span data-ttu-id="2d2b6-110">Перегрузка канала глобальной сети может привести к ухудшению качества взаимодействия (QoE) для пользователей.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-110">Congestion on the WAN can result in a poor Quality of Experience (QoE) for users.</span></span> <span data-ttu-id="2d2b6-111">Для трафика в режиме реального времени в перегруженных условиях лучше запретить звонки, чем предоставлять соединения с низким качеством.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-111">For real-time traffic in congested conditions, it is better to deny calls than to provide connections with poor quality.</span></span>

<span data-ttu-id="2d2b6-112">Контроль допуска звонков (CAC) определяет, достаточно ли пропускной полосы для установления сеанса связи допустимого качества в реальном времени.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-112">Call admission control (CAC) determines whether there is sufficient network bandwidth to establish a real-time session of acceptable quality.</span></span> <span data-ttu-id="2d2b6-113">В Lync Server 2013 CAC управляет трафиком в реальном времени только для звуковых и видеофайлов, но не влияет на трафик данных.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-113">In Lync Server 2013, CAC controls real-time traffic only for audio and video, but it does not affect data traffic.</span></span> <span data-ttu-id="2d2b6-114">Если у WAN-канала по умолчанию нет необходимой пропускной полосы, CAC может попытаться направить вызов через Интернет или телефонную сеть общего пользования (ТСОП).</span><span class="sxs-lookup"><span data-stu-id="2d2b6-114">If the default WAN path does not have the required bandwidth, CAC can attempt to route the call through an Internet path or the public switched telephone network (PSTN).</span></span> <span data-ttu-id="2d2b6-115">CAC поддерживается только в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-115">CAC is available only in Lync Server.</span></span>

<span data-ttu-id="2d2b6-116">В этом разделе приведено описание функций контроля допуска звонков и планирование использования CAC.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-116">This section describes the call admission control functionality and explains how to plan for CAC.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2d2b6-117">На сервере Lync Server есть три опытных услуги голосовой связи: управление допуском звонков (CAC), службы экстренной помощи (E9-1) и обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-117">Lync Server has three advanced Enterprise Voice features: call admission control (CAC), emergency services (E9-1-1), and media bypass.</span></span> <span data-ttu-id="2d2b6-118">Общие сведения о планировании, которые являются общими для всех трех из этих функций, приведены в разделе <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Параметры сети для опытных функций корпоративного голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2d2b6-118">For an overview of planning information that is common to all three of these features, see <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Network settings for the advanced Enterprise Voice features in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2d2b6-119">Содержание</span><span class="sxs-lookup"><span data-stu-id="2d2b6-119">In This Section</span></span>

  - [<span data-ttu-id="2d2b6-120">Общие сведения об управлении допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2b6-120">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)

  - [<span data-ttu-id="2d2b6-121">Определение своих требований для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2b6-121">Defining your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="2d2b6-122">Пример: сбор требований к управлению допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2b6-122">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [<span data-ttu-id="2d2b6-123">Компоненты и топологии для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2b6-123">Components and topologies for CAC in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-cac.md)

  - [<span data-ttu-id="2d2b6-124">Рекомендации по контролю допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2b6-124">Best practices for call admission control in Lync Server 2013</span></span>](lync-server-2013-best-practices-for-call-admission-control.md)

  - [<span data-ttu-id="2d2b6-125">Контрольный список развертывания для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d2b6-125">Deployment checklist for call admission control in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

