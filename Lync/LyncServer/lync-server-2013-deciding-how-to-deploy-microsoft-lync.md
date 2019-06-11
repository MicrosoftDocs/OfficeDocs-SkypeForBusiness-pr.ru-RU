---
title: 'Lync Server 2013: принятие решения о способе развертывания Microsoft Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deciding how to deploy Microsoft Lync
ms:assetid: 6ca677d3-745d-4935-8f05-19274a8bccf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204979(v=OCS.15)
ms:contentKeyID: 48184423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d641f4da1884c1fb6e84eefb2127490f2ed3c4a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deciding-how-to-deploy-lync-server-2013"></a><span data-ttu-id="493d4-102">Принятие решения о способе развертывания Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="493d4-102">Deciding how to deploy Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="493d4-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="493d4-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="493d4-104">При планировании для Lync первым основным решением будет развертывание Microsoft Lync: в локальной среде Lync Server 2013 или Lync Online с Microsoft Office 365 в облаке.</span><span class="sxs-lookup"><span data-stu-id="493d4-104">When planning for Lync, the first major decision is how to deploy Microsoft Lync: as Lync Server 2013 on premises, or Lync Online with Microsoft Office 365 in the cloud.</span></span>

  - <span data-ttu-id="493d4-105">**Lync Server 2013 в локальной среде** : этот выбор обеспечивает полный комплект функций Lync и обеспечивает максимальную гибкость при настройке, настройке и работе развертывания.</span><span class="sxs-lookup"><span data-stu-id="493d4-105">**Lync Server 2013 on-premises** : This choice provides the complete Lync feature set and provides ultimate flexibility in configuring, customizing, and operating your deployment.</span></span> <span data-ttu-id="493d4-106">Все серверы устанавливаются на сайт и обслуживаются вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="493d4-106">All servers are installed onsite and maintained by your organization.</span></span> <span data-ttu-id="493d4-107">Локальное развертывание обеспечивает полный диапазон возможностей Lync Server.</span><span class="sxs-lookup"><span data-stu-id="493d4-107">An on-premises deployment provides the full range of Lync Server features.</span></span>

  - <span data-ttu-id="493d4-108">**Lync Online в облаке** Lync Online разработан для организаций, которые хотят использовать стоимость и динамичность обмена мгновенными сообщениями, присутствия и собраний на основе облачных служб, не жертвуя возможностями бизнес-класса в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="493d4-108">**Lync Online in the cloud** Lync Online is designed for organizations that want the cost and agility benefits of cloud-based instant messaging, presence, and meetings without sacrificing the business-class capabilities of Lync Server.</span></span> <span data-ttu-id="493d4-109">С помощью Lync Online корпорация Майкрософт развертывает и поддерживает требуемую серверную инфраструктуру, а также обрабатывает непрерывное обслуживание, исправления и обновления.</span><span class="sxs-lookup"><span data-stu-id="493d4-109">With Lync Online, Microsoft deploys and maintains the required server infrastructure, and handles ongoing maintenance, patches, and upgrades.</span></span> <span data-ttu-id="493d4-110">Некоторые возможности, доступные в локальном развертывании, недоступны в Lync Online.</span><span class="sxs-lookup"><span data-stu-id="493d4-110">Some features available in an on-premises deployment are not available in Lync Online.</span></span>

<span data-ttu-id="493d4-111">Какой тип развертывания наилучшим образом зависит от нагрузки, которую вы хотите развернуть, а также от географического и бизнес-статуса Организации.</span><span class="sxs-lookup"><span data-stu-id="493d4-111">Which type of deployment would be best for you depends on the workloads you want to deploy, and your organization’s geographical and business status.</span></span>

<div>

## <a name="lync-server"></a><span data-ttu-id="493d4-112">Lync Server</span><span class="sxs-lookup"><span data-stu-id="493d4-112">Lync Server</span></span>

<span data-ttu-id="493d4-113">Развертывание с помощью локального сервера Lync Server наилучшим образом подходит для следующих сценариев:</span><span class="sxs-lookup"><span data-stu-id="493d4-113">An on-premises Lync Server deployment is best for the following scenarios:</span></span>

  - <span data-ttu-id="493d4-114">**Возможности поддержки голосовой связи в масштабах предприятия**   если вы планируете развернуть полноценную корпоративную голосовую почту, чтобы заменить АТС или использовать дополнительные функции звонков, требуется локальное развертывание Lync Server.</span><span class="sxs-lookup"><span data-stu-id="493d4-114">**Full Enterprise Voice Capabilities**   If you plan to deploy a full Enterprise Voice solution to replace your PBX or which uses advanced calling features, an on-premises Lync Server deployment is required.</span></span> <span data-ttu-id="493d4-115">Локальная поддержка прямого подключения к системам АТС и магистрали и дополнительным функциям, таким как группы ответа и переадресация звонков.</span><span class="sxs-lookup"><span data-stu-id="493d4-115">On-premises supports direct connectivity with PBX systems and trunks, and advanced phone features such as response groups and call park.</span></span> <span data-ttu-id="493d4-116">Lync Online в настоящее время не поддерживает эти функции.</span><span class="sxs-lookup"><span data-stu-id="493d4-116">Lync Online does not currently support these features.</span></span>

  - <span data-ttu-id="493d4-117">**Управление качеством мультимедиа**   если вы хотите использовать полный диапазон возможностей контроля качества мультимедиа, например управление допуском (CAC) и функцию качества обслуживания (QoS), вам потребуется локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="493d4-117">**Media Quality Controls**   If you want the full range of media quality assurance features, such as Call Admission Control (CAC) and Quality of Service (QoS) features, you will want an on-premises deployment .</span></span>

  - <span data-ttu-id="493d4-118">**Сохраняемый чат**   если вам нужно развернуть сохраняемый чат для Организации, необходимо выбрать локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="493d4-118">**Persistent Chat**   If you need to deploy Persistent chat for your organization, you must choose an on-premises deployment.</span></span>

  - <span data-ttu-id="493d4-119">**серверные приложения**   третьих лиц только локальные развертывания могут работать с надежными приложениями сторонних разработчиков, которые используют API Microsoft единой системы обмена мгновенными сообщениями (УКМА).</span><span class="sxs-lookup"><span data-stu-id="493d4-119">**3rd-Party Server Applications**   Only on-premises deployments can work with trusted 3rd-party applications that use the Microsoft Unified Communications Managed API (UCMA).</span></span>

  - <span data-ttu-id="493d4-120">\*\*\*\* Если у вас есть центры обработки данных в нескольких странах или регионах и вам нужны серверы для развертывания и управления на региональном уровне, лучше использовать локальное развертывание, так как это обеспечивает этот тип.    из региональных возможностей управления.</span><span class="sxs-lookup"><span data-stu-id="493d4-120">**Multi-National/Multi-Regional Companies Needing Regional Support**   If you have datacenters in multiple countries or regions and need servers to be deployed and managed on a regional basis, an on-premises deployment is best, as it provides this type of regional management capabilities.</span></span>

  - <span data-ttu-id="493d4-121">**Полный контроль над политиками, отчетами и обновлениями**   с помощью локального развертывания Lync Server позволяет получить доступ ко всем наборам политик сервера и клиента, мониторингу и другим отчетам, а также времени обновления.</span><span class="sxs-lookup"><span data-stu-id="493d4-121">**Complete control over policies, reports, and upgrades**   With an on premises Lync Server deployment, you have access to the full set of server and client policies, Monitoring and other reports, and timing of upgrades.</span></span> <span data-ttu-id="493d4-122">Lync Online предоставляет подмножество параметров политики и отчетов, а также предоставляет ограниченные, но важные окна для принятия обновлений.</span><span class="sxs-lookup"><span data-stu-id="493d4-122">Lync Online provides a subset of policy setting and reports, and provides a limited, though significant, window for accepting upgrades.</span></span>

</div>

<div>

## <a name="lync-online"></a><span data-ttu-id="493d4-123">Lync Online</span><span class="sxs-lookup"><span data-stu-id="493d4-123">Lync Online</span></span>

<span data-ttu-id="493d4-124">Если ни один из перечисленных выше факторов не является критическим, вы можете выбрать Lync Online для упрощения развертывания и управления.</span><span class="sxs-lookup"><span data-stu-id="493d4-124">If none of the factors in the preceding list are critical for you, you may want to choose Lync Online, for simpler deployment and manageability.</span></span> <span data-ttu-id="493d4-125">Lync Online обеспечивает надежное средство обмена мгновенными сообщениями, присутствие и конференц-связь, а также включает голосовые и видеозвонки по протоколу IP между пользователями в Организации.</span><span class="sxs-lookup"><span data-stu-id="493d4-125">Lync Online provides a robust IM, presence and conferencing feature set, and also enables voice and video calls over IP between users in your organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

