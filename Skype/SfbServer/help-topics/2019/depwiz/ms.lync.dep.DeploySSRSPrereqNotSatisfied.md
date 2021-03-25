---
title: Службы SQL Server Reporting Services (необходимые условия не соблюдены)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.
ms.openlocfilehash: 657c1b203dd5d01fedde9ad0c5b08c6775f4bd4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118908"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="7f9fa-104">Службы SQL Server Reporting Services (необходимые условия не соблюдены)</span><span class="sxs-lookup"><span data-stu-id="7f9fa-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="7f9fa-p102">Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="7f9fa-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="7f9fa-107">Чтобы устранить эту проблему, убедитесь, что к домену присоединился сервер мониторинга, что он определен в Topology Builder и топология была опубликована.</span><span class="sxs-lookup"><span data-stu-id="7f9fa-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="7f9fa-108">SQL Server службы отчетности также должны быть доступны в SQL Server и установлены в качестве функции в базе данных monitoring Server на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7f9fa-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="7f9fa-109">Дополнительные сведения см. [в материале Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) и [Deploying Monitoring.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)</span><span class="sxs-lookup"><span data-stu-id="7f9fa-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>