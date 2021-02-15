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
ms.openlocfilehash: b7b6e65fd1fc9c361a06281794363cd32e3807e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836729"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="769c0-104">Службы SQL Server Reporting Services (необходимые условия не соблюдены)</span><span class="sxs-lookup"><span data-stu-id="769c0-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="769c0-p102">Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="769c0-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="769c0-107">Чтобы устранить эту проблему, убедитесь, что к домену присоединился сервер мониторинга, что он определен в построитель топологий и что топология опубликована.</span><span class="sxs-lookup"><span data-stu-id="769c0-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="769c0-108">SQL Server Службы Reporting Services также должны быть доступны на SQL Server и установлены в качестве функции в базе данных сервера мониторинга на SQL Server.</span><span class="sxs-lookup"><span data-stu-id="769c0-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="769c0-109">Дополнительные сведения см. в сведениях об [установке](../../../deploy/deploy-monitoring/install-monitoring-reports.md) отчетов мониторинга в Skype для бизнеса Server и [развертывании мониторинга.](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)</span><span class="sxs-lookup"><span data-stu-id="769c0-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


