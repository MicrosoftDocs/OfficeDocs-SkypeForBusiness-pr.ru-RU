---
title: Установка SQL Server отчетов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
description: Сводка. Сведения о том, куда идти, чтобы найти сведения о SQL Server службах отчетности, используемых Skype для бизнеса Server.
ms.openlocfilehash: 449ca513503209f062b3e35fe7474bd11162790f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101965"
---
# <a name="install-sql-server-reporting-services-in-skype-for-business-server"></a><span data-ttu-id="a25fd-103">Установка SQL Server отчетов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a25fd-103">Install SQL Server Reporting Services in Skype for Business Server</span></span> 
 
<span data-ttu-id="a25fd-104">**Сводка:** Узнайте, куда пойти, чтобы найти сведения о SQL Server службах отчетности, используемых Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a25fd-104">**Summary:** Learn where to go to find information about SQL Server Reporting Services used by Skype for Business Server.</span></span>
  
<span data-ttu-id="a25fd-105">Skype для бизнеса Server может использовать SQL Server службы отчетности (SSRS) для просмотра и мониторинга отчетов.</span><span class="sxs-lookup"><span data-stu-id="a25fd-105">Skype for Business Server can use SQL Server Reporting Services (SSRS) for viewing and monitoring reports.</span></span> <span data-ttu-id="a25fd-106">Для использования этой функции необходимо установить и настроить службы отчетности.</span><span class="sxs-lookup"><span data-stu-id="a25fd-106">In order to use this functionality you will need to have Reporting Services installed and configured.</span></span>
  
## <a name="install-sql-server-reporting-services"></a><span data-ttu-id="a25fd-107">Установка служб SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="a25fd-107">Install SQL Server Reporting Services</span></span>

<span data-ttu-id="a25fd-108">Если вы собираетесь использовать отчеты по мониторингу Skype для бизнес-серверов (см. в следующей статье этой документации дополнительные сведения), сначала необходимо установить SQL Server службы отчетности; Службы отчетов можно установить одновременно с установкой Microsoft SQL Server или в любое время после SQL Server установки.</span><span class="sxs-lookup"><span data-stu-id="a25fd-108">If you intend to use Skype for Business Server Monitoring Reports (see the next article of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="a25fd-109">Если вы не установили SQL Server, следуйте инструкциям, предоставленным ранее в этой документации.</span><span class="sxs-lookup"><span data-stu-id="a25fd-109">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="a25fd-110">При установке SQL Server убедитесь, что на странице Выбор функций выберите службы отчетов.</span><span class="sxs-lookup"><span data-stu-id="a25fd-110">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="a25fd-111">Это позволит установить SQL Server службы отчетности.</span><span class="sxs-lookup"><span data-stu-id="a25fd-111">That will install SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="a25fd-112">Подробнее об установке служб SQL Server отчетов см. в [SQL Server Службы отчетов (SSRS).](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports)</span><span class="sxs-lookup"><span data-stu-id="a25fd-112">To learn how to install SQL Server Reporting Services, see [SQL Server Reporting Services (SSRS)](/sql/reporting-services/create-deploy-and-manage-mobile-and-paginated-reports).</span></span>
  
<span data-ttu-id="a25fd-113">Если вы уже установили SQL Server, но не SQL Server службы отчетности, вы можете добавить эту функцию, следуя соответствующему набору инструкций для служб SQL Server отчетов.</span><span class="sxs-lookup"><span data-stu-id="a25fd-113">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server Reporting Services.</span></span> 
