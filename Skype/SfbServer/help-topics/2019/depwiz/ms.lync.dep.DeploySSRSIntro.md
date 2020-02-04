---
title: Службы SQL Server Reporting Services (введение)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
ROBOTS: NOINDEX, NOFOLLOW
description: У каждого пула переднего плана и работающего устройства филиала может быть только один сервер мониторинга, связанный с ним. Если на сайте включена поддержка мониторинга, сервер мониторинга обеспечивает запись сведений о вызовах (CDR) и сбор данных о соотношении качества (QoE).
ms.openlocfilehash: e9815ce9ea47e1050cc3e26d9add10d11caab030
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705294"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="63075-104">Службы SQL Server Reporting Services (введение)</span><span class="sxs-lookup"><span data-stu-id="63075-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="63075-105">У каждого пула переднего плана и работающего устройства филиала может быть только один сервер мониторинга, связанный с ним.</span><span class="sxs-lookup"><span data-stu-id="63075-105">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it.</span></span> <span data-ttu-id="63075-106">Если на сайте включена поддержка мониторинга, сервер мониторинга обеспечивает запись сведений о вызовах (CDR) и сбор данных о соотношении качества (QoE).</span><span class="sxs-lookup"><span data-stu-id="63075-106">When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="63075-107">Все пулы на сайте и пулы нескольких центральных сайтов могут использовать один и тот же сервер мониторинга, если использование не превышает емкость сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="63075-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="63075-108">Сведения о разработке топологии для поддержки мониторинга можно найти в разделе [связывание хранилища мониторинга с пулом переднего плана в](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="63075-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

