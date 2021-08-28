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
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.
ms.openlocfilehash: 235dec8ce462a6aafe7a1c4746cdb01d5169d4b3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615975"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>Службы SQL Server Reporting Services (необходимые условия не соблюдены)

Эта страница появляется, если в вашей инфраструктуре не развернут сервер мониторинга. Это означает, что не соблюдены минимальные требования для развертывания сервера мониторинга.

Чтобы устранить эту проблему, убедитесь, что к домену присоединился сервер мониторинга, что он определен в Topology Builder и топология была опубликована. SQL Server Reporting Services также должен быть доступен в SQL Server и установлен в качестве функции в базе данных monitoring Server на SQL Server.

Дополнительные сведения см. [в материале Install Monitoring Reports in Skype для бизнеса Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) и [Deploying Monitoring.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)