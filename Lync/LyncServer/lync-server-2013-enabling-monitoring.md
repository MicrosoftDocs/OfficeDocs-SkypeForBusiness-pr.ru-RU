---
title: 'Lync Server 2013: Включение мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="aa830-102">Включение мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa830-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa830-103">_**Тема последнего изменения:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="aa830-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="aa830-104">Несмотря на то, что агенты Объединенного сбора данных автоматически устанавливаются и активируются на каждом сервере переднего плана, это не значит, что при установке Microsoft Lync Server 2013 автоматически начинается сбор данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="aa830-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="aa830-105">Вместо этого необходимо выполнить два действия: вы должны связать серверы переднего плана и пулы переднего плана с базой данных мониторинга, а также включить мониторинг сведений о вызове (CDR) и/или качества взаимодействия (QoE) в глобальной области и/или области сайта.</span><span class="sxs-lookup"><span data-stu-id="aa830-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="aa830-106">Пошаговые инструкции по связыванию серверов переднего плана и пулов переднего плана с базой данных мониторинга можно найти в разделе [сопоставление хранилища мониторинга с пулом переднего плана в Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) в руководстве по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="aa830-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="aa830-107">После того как эти ассоциации будут сделаны, после публикации новой топологии Lync Server вы по-прежнему сможете собирать данные наблюдения.</span><span class="sxs-lookup"><span data-stu-id="aa830-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="aa830-108">Это объясняется тем, что по умолчанию при установке Lync Server 2013 CDR и QoE не отключаются.</span><span class="sxs-lookup"><span data-stu-id="aa830-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="aa830-109">Сбор данных начинается только после включения мониторинга регистрации вызовов и качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="aa830-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="aa830-110">(Обратите внимание, что вам не нужно включать мониторинг CDR и QoE; при желании вы можете включить один тип наблюдения, не выходя из другого типа.) Чтобы включить мониторинг CDR в глобальной области, выполните в командной консоли Lync Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="aa830-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="aa830-111">Кроме того, вы можете включить мониторинг CDR в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aa830-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="aa830-112">В панели управления Lync Server выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="aa830-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="aa830-113">Щелкните **Мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="aa830-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="aa830-114">На вкладке **Регистрация вызовов** дважды щелкните параметр **Глобально**.</span><span class="sxs-lookup"><span data-stu-id="aa830-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="aa830-115">На панели **изменения настройки регистрации вызовов (CDR)** выберите **Разрешить отслеживание регистрации вызовов**, затем нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa830-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="aa830-116">Чтобы включить мониторинг QoE в глобальной области, выполните эту команду в командной консоли Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="aa830-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="aa830-117">При желании вы также можете включить мониторинг QoE с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aa830-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="aa830-118">На панели управления выполните следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="aa830-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="aa830-119">Щелкните **Мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="aa830-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="aa830-120">На вкладке **Данные о качестве взаимодействия** дважды щелкните параметр **Глобально**.</span><span class="sxs-lookup"><span data-stu-id="aa830-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="aa830-121">На панели **изменения настройки качества взаимодействия (CDR)** выберите **Разрешить отслеживание данных о качестве взаимодействия** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa830-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="aa830-122">Как отмечено выше, команды в предыдущих примерах позволяют включить мониторинг регистрации вызовов и качества взаимодействия глобально, то есть в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="aa830-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="aa830-123">Можно также создавать для регистрации вызовов и качества взаимодействия отдельные параметры конфигурации на уровне сайта, после чего выборочно включать и отключать мониторинг для отдельных сайтов.</span><span class="sxs-lookup"><span data-stu-id="aa830-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="aa830-124">Например, мониторинг регистрации вызовов может быть включен для сайта Redmond и отключен для сайта Dublin.</span><span class="sxs-lookup"><span data-stu-id="aa830-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="aa830-125">Дополнительные сведения об управлении параметрами конфигурации мониторинга можно найти в разделе Руководство по развертыванию: [Настройка записи сведений о звонке и параметров качества обслуживания в Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="aa830-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

