---
title: Службы SQL Server Reporting Services (необходимые условия не соблюдены)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.
ms.openlocfilehash: 792c9d3b6e7c398d517549eb55aaf85086badb64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100015"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>Службы SQL Server Reporting Services (необходимые условия не соблюдены)

Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.

Чтобы устранить эту проблему, убедитесь, что к домену присоединился сервер мониторинга, что он определен в Topology Builder и топология была опубликована. SQL Server службы отчетности также должны быть доступны в SQL Server и установлены в качестве функции в базе данных monitoring Server на SQL Server.

Дополнительные сведения см. [в материале Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) и [Deploying Monitoring.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)