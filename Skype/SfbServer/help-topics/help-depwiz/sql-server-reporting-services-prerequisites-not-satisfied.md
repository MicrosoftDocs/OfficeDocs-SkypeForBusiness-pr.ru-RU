---
title: Службы SQL Server Reporting Services (необходимые условия не соблюдены)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.
ms.openlocfilehash: af04fd438620bea32bcab95cdbca295c116773b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289558"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="5c6be-104">Службы SQL Server Reporting Services (необходимые условия не соблюдены)</span><span class="sxs-lookup"><span data-stu-id="5c6be-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="5c6be-p102">Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="5c6be-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="5c6be-107">Чтобы устранить эту проблему, убедитесь, что к домену подключен сервер мониторинга, который определен в построителе топологии и что топология опубликована.</span><span class="sxs-lookup"><span data-stu-id="5c6be-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="5c6be-108">Службы SQL Server Reporting Services также должны быть доступны на сервере SQL Server и установлены как функция в базу данных сервера мониторинга на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5c6be-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="5c6be-109">Подробности можно найти [в разделе Установка отчетов мониторинга в Skype для бизнеса Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) и [развертывание мониторинга](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c6be-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


