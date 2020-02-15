---
title: 'Lync Server 2013: Настройка контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ebe3fbdd60409523755c865f4b4f34025acf15d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="e6f45-102">Настройка контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-102">Configure call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e6f45-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="e6f45-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="e6f45-104">Контроль допуска звонков (CAC) — это решение, которое определяет, можно ли установить сеанс реального времени на основе доступной полосы пропускания, чтобы предотвратить плохое качество звука и видео для пользователей в перегруженных сетях.</span><span class="sxs-lookup"><span data-stu-id="e6f45-104">Call admission control (CAC) is a solution that determines whether a real-time session can be established based on the available bandwidth to help prevent poor audio/video quality for users on congested networks.</span></span> <span data-ttu-id="e6f45-105">CAC управляет трафиком в режиме реального времени только для аудио и видео и не влияет на трафик данных.</span><span class="sxs-lookup"><span data-stu-id="e6f45-105">CAC controls real-time traffic only for audio and video, and does not affect data traffic.</span></span> <span data-ttu-id="e6f45-106">С помощью функции CAC можно направить вызов через Интернет, если по умолчанию для канала глобальной сети нет необходимой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="e6f45-106">CAC may route the call through an Internet path when the default WAN path does not have the required bandwidth.</span></span> <span data-ttu-id="e6f45-107">Дополнительные сведения приведены в статье [Планирование контроля допуска звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e6f45-107">For details, see [Planning for call admission control in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="e6f45-108">В этом разделе представлен набор примеров процедур, иллюстрирующих развертывание и Управление CAC в сети.</span><span class="sxs-lookup"><span data-stu-id="e6f45-108">This section provides a set of example procedures that illustrate how to deploy and manage CAC in your network.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e6f45-109">Перед развертыванием CAC необходимо собрать всю необходимую информацию для топологии корпоративной сети, как описано в <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">примере: сбор требований для контроля допуска звонков в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e6f45-109">Before you deploy CAC, you must gather all of the required information for your enterprise network topology, as described in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Example: Gathering your requirements for call admission control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="e6f45-110">Кроме того, убедитесь, что компоненты CAC установлены и активированы, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e6f45-110">Also be sure that CAC components have been installed and activated, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e6f45-111">Все примеры развертывания и управления CAC, описанные в этом разделе, выполняются с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e6f45-111">All CAC deployment and management examples in this section are performed by using the Lync Server Management Shell.</span></span> <span data-ttu-id="e6f45-112">В качестве альтернативы вы также можете использовать раздел <STRONG>Конфигурация сети</STRONG> в панели управления Lync Server для управления CAC.</span><span class="sxs-lookup"><span data-stu-id="e6f45-112">As an alternative, you can also use the <STRONG>Network Configuration</STRONG> section of Lync Server Control Panel to manage CAC.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e6f45-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="e6f45-113">In This Section</span></span>

  - [<span data-ttu-id="e6f45-114">Настройка сетевых регионов для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-114">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)

  - [<span data-ttu-id="e6f45-115">Создание профилей политики пропускной способности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-115">Create bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="e6f45-116">Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-116">Configure network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-sites-for-cac.md)

  - [<span data-ttu-id="e6f45-117">Связывание подсетей с сетевыми сайтами для контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-117">Associate subnets with network sites for CAC in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [<span data-ttu-id="e6f45-118">Создание связей между областями сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-118">Create network region links in Lync Server 2013</span></span>](lync-server-2013-create-network-region-links.md)

  - [<span data-ttu-id="e6f45-119">Создание маршрутов между межсетевыми областями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-119">Create network interregion routes in Lync Server 2013</span></span>](lync-server-2013;-create-network-interregion-routes.md)

  - [<span data-ttu-id="e6f45-120">Создание межсайтовых политик для сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-120">Create network intersite policies in Lync Server 2013</span></span>](lync-server-2013-create-network-intersite-policies.md)

  - [<span data-ttu-id="e6f45-121">Включение контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-121">Enable call admission control in Lync Server 2013</span></span>](lync-server-2013-enable-call-admission-control.md)

  - [<span data-ttu-id="e6f45-122">Контрольный список развертывания контроля допуска звонков для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e6f45-122">Call admission control deployment checklist for Lync Server 2013</span></span>](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

