---
title: 'Lync Server 2013: решение о развертывании Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31a765d6b682e504839aa24962356f5524801d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516526"
---
# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="37dde-102">Принятие решения о развертывании Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37dde-102">Deciding how to deploy Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37dde-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="37dde-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="37dde-104">При планировании Lync первое основное решение заключается в развертывании Microsoft Lync: в локальной среде Lync Server 2013 или Lync Online с Microsoft 365 или Office 365 в облаке.</span><span class="sxs-lookup"><span data-stu-id="37dde-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft 365 or Office 365 in the cloud.</span></span>

  - <span data-ttu-id="37dde-105">**Lync Server 2013 локальный** : этот вариант обеспечивает полный набор функций Lync и предоставляет максимальную гибкость при настройке, настройке и эксплуатации развертывания.</span><span class="sxs-lookup"><span data-stu-id="37dde-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="37dde-106">Все серверы устанавливаются на предприятии и поддерживаются вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="37dde-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="37dde-107">Локальное развертывание предоставляет полный диапазон функций Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37dde-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="37dde-108">**Lync Online в облаке** Lync Online предназначен для организаций, которым требуются преимущества затрат и гибкого обмена мгновенными сообщениями на основе облачных служб, без ущерба для возможностей корпоративного класса Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37dde-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="37dde-109">С помощью Lync Online корпорация Майкрософт развертывает и поддерживает необходимую серверную инфраструктуру, а также обрабатывает текущие исправления и обновления.</span><span class="sxs-lookup"><span data-stu-id="37dde-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="37dde-110">Некоторые функции, доступные в локальном развертывании, недоступны в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="37dde-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="37dde-111">Лучший для вас тип развертывания зависит от рабочей нагрузки, которую вы хотите развернуть, а также географического и коммерческого состояния вашей организации.</span><span class="sxs-lookup"><span data-stu-id="37dde-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="37dde-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="37dde-112">Lync Server</span></span>

<span data-ttu-id="37dde-113">Локальное развертывание Lync Server лучше всего подходит для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="37dde-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="37dde-114">**Полные возможности**     голосовой связи предприятия Если вы планируете развернуть полное корпоративное корпоративное решение для замены УАТС или использования расширенных функций звонков, требуется локальное развертывание Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37dde-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="37dde-115">Локальное решение поддерживает прямое подключение к УАТС и магистралям, а также дополнительные функции телефонной связи, такие как группы ответа и парковка звонков.</span><span class="sxs-lookup"><span data-stu-id="37dde-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="37dde-116">Lync Online в настоящее время не поддерживает эти функции.</span><span class="sxs-lookup"><span data-stu-id="37dde-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="37dde-117">**Элементы управления**     качеством мультимедиа Если вам нужен полный спектр функций контроля качества мультимедиа, таких как функции контроля допуска звонков (CAC) и качества обслуживания (QoS), вам потребуется локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="37dde-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="37dde-118">**Сохраняемый чат**     Если необходимо развернуть сохраняемый чат для Организации, необходимо выбрать локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="37dde-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="37dde-119">**серверные приложения**     сторонних производителей Только локальные развертывания могут работать с доверенными сторонними приложениями, использующими Microsoft Unified Communications Managed API (UCMA).</span><span class="sxs-lookup"><span data-stu-id="37dde-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="37dde-120">Для **компаний с поддержкой нескольких национальных и национальных регионов необходима региональная поддержка**     Если у вас есть центры обработки данных в нескольких странах или регионах и требуется развертывать и управлять ими на региональном уровне, то лучше всего использовать локальное развертывание, так как предоставляет этот тип возможностей региональных функций управления.</span><span class="sxs-lookup"><span data-stu-id="37dde-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="37dde-121">**Полный контроль над политиками, отчетами и обновлениями**     При локальном развертывании Lync Server у вас есть доступ к полному набору политик серверов и клиентов, мониторингу и другим отчетам, а также времени обновления.</span><span class="sxs-lookup"><span data-stu-id="37dde-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="37dde-122">Lync Online предоставляет подмножество параметров политики и отчетов, а также предоставляет ограниченные, хотя важные, окна для принятия обновлений.</span><span class="sxs-lookup"><span data-stu-id="37dde-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="37dde-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="37dde-123">Lync Online</span></span>

<span data-ttu-id="37dde-124">Если ни один из факторов из предыдущего списка не важен для вашей компании, вы можете выбрать Lync Online, чтобы упростить развертывание и управление.</span><span class="sxs-lookup"><span data-stu-id="37dde-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="37dde-125">Lync Online обеспечивает надежный набор функций для обмена мгновенными сообщениями, присутствия и конференций, а также обеспечивает голосовые и видеозвонки по протоколу IP между пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="37dde-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
