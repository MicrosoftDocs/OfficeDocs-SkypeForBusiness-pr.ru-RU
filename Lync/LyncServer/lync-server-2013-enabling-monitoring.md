---
title: 'Lync Server 2013: Включение мониторинга'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ceef06ca0078b9a34c9f02e1ed3be91ab9b34aa
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="1be13-102">Включение мониторинга в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1be13-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1be13-103">_**Последнее изменение темы:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="1be13-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="1be13-104">Несмотря на то, что агенты унифицированного сбора данных автоматически устанавливаются и активируются на каждом сервере переднего плана, это не означает, что вы автоматически начнете сбор данных мониторинга, пока не завершите установку Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1be13-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="1be13-105">Для этого необходимо выполнить два действия: необходимо связать серверы переднего плана/интерфейсные пулы с базой данных мониторинга, а также разрешить мониторинг регистрации вызовов (CDR) и/или качества взаимодействия (QoE) в глобальной области и/или области сайта.</span><span class="sxs-lookup"><span data-stu-id="1be13-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="1be13-106">Пошаговые инструкции по связыванию серверов переднего плана и интерфейсных пулов с базой данных мониторинга представлены в разделе [связь хранилища мониторинга с пулом переднего плана в Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) в руководстве по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="1be13-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="1be13-107">После выполнения привязки и публикации новой топологии Lync Server, сбор данных мониторинга будет по-прежнему невозможен.</span><span class="sxs-lookup"><span data-stu-id="1be13-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="1be13-108">Это связано с тем, что по умолчанию сбор данных CDR и QoE отключен при установке Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1be13-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="1be13-109">Чтобы начать сбор данных, необходимо включить мониторинг CDR и/или QoE.</span><span class="sxs-lookup"><span data-stu-id="1be13-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="1be13-110">(Обратите внимание, что вам не нужно включать мониторинг CDR и QoE; при желании вы можете включить один тип мониторинга, оставив другой отключенный.) Чтобы включить мониторинг CDR в глобальной области, выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1be13-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="1be13-111">Кроме того, вы можете включить мониторинг CDR в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1be13-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="1be13-112">В панели управления Lync Server выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1be13-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="1be13-113">Щелкните **Мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="1be13-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="1be13-114">На вкладке **Регистрация вызовов** дважды щелкните параметр **Глобальные**.</span><span class="sxs-lookup"><span data-stu-id="1be13-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="1be13-115">В области **Изменить настройку регистрации вызовов (CDR)** выберите **Разрешить мониторинг регистрации вызовов** и нажмите **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="1be13-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="1be13-116">Чтобы включить мониторинг QoE в глобальной области, выполните следующую команду в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="1be13-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="1be13-117">При желании вы также можете включить мониторинг QoE в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1be13-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="1be13-118">На панели управления выполните следующую процедуру:</span><span class="sxs-lookup"><span data-stu-id="1be13-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="1be13-119">Щелкните **Мониторинг**.</span><span class="sxs-lookup"><span data-stu-id="1be13-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="1be13-120">На вкладке **Данные о качестве взаимодействия** дважды щелкните параметр **Глобальные**.</span><span class="sxs-lookup"><span data-stu-id="1be13-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="1be13-121">В области **Изменить настройку качества взаимодействия (CDR)** выберите **Разрешить мониторинг качества взаимодействия** и нажмите **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="1be13-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="1be13-122">Как уже отмечено ранее, предыдущие примеры демонстрируют включение мониторинга в глобальной области, то есть, включение мониторинга регистрации вызовов и качества взаимодействия в пределах организации.</span><span class="sxs-lookup"><span data-stu-id="1be13-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="1be13-123">Как вариант, можно также создать отдельные параметры конфигурации регистрации вызовов и качества взаимодействия в области сайта, после чего выборочно включить или отключить мониторинг для каждого из сайтов.</span><span class="sxs-lookup"><span data-stu-id="1be13-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="1be13-124">Например, можно включить мониторинг регистрации вызовов для сайта Redmond и отключить при этом мониторинг регистрации вызовов для сайта Dublin.</span><span class="sxs-lookup"><span data-stu-id="1be13-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="1be13-125">Дополнительные сведения об управлении параметрами конфигурации мониторинга содержатся в руководстве по развертыванию, в котором описывается [Настройка регистрации вызовов и параметров качества взаимодействия в Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="1be13-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

