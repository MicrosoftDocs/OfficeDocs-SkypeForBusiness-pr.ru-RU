---
title: Доступ к данным наблюдения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Сводка: сведения о контрольных данных, используемых в Skype для бизнеса Server.'
ms.openlocfilehash: b4eca36a09c4aa56b7216b476e0f0c5fa06d7a45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818190"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="11b22-103">Доступ к данным наблюдения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="11b22-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="11b22-104">**Сводка:** Сведения о мониторинге данных, используемых в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="11b22-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="11b22-p101">Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="11b22-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="11b22-107">Для получения доступа к данным мониторинга и анализа данных, которые необходимо использовать в Skype для бизнеса Server, следует ознакомиться с отчетами мониторинга.</span><span class="sxs-lookup"><span data-stu-id="11b22-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="11b22-108">Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="11b22-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="11b22-109">Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в базе данных CDR и QoE.</span><span class="sxs-lookup"><span data-stu-id="11b22-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="11b22-110">Наблюдение за отчетами в Skype для бизнеса Server и их установка с помощью мастера развертывания Skype для бизнеса Server после установки и настройки мониторинга в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="11b22-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="11b22-p103">Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="11b22-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="11b22-113">Дополнительные сведения можно найти [в разделе Установка отчетов по мониторингу в Skype для бизнеса Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span><span class="sxs-lookup"><span data-stu-id="11b22-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

