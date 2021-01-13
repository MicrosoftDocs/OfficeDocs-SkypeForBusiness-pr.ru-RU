---
title: Доступ к данным мониторинга в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: Сводка. Сведения о данных мониторинга, используемых в Skype для бизнеса Server.
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826549"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a><span data-ttu-id="0ab77-103">Доступ к данным мониторинга в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0ab77-103">Access monitoring data in Skype for Business Server</span></span>
 
<span data-ttu-id="0ab77-104">**Сводка:** Сведения о данных мониторинга, используемых в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0ab77-104">**Summary:** Learn about the monitoring data used in Skype for Business Server.</span></span>
  
<span data-ttu-id="0ab77-p101">Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ab77-p101">Monitoring data is stored in a pair of SQL Server databases: LcsCdr for call detail recording data, and QoEMetrics for Quality of Experience data. There is nothing special about these two databases; that means that the data stored in those databases can be accessed using any of the tools you typically use for accessing and analyzing SQL Server data.</span></span>
  
<span data-ttu-id="0ab77-107">Одним из средств, которые следует рассмотреть для доступа к данным мониторинга и их анализа, является отчеты мониторинга Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0ab77-107">One tool you should consider for accessing and analyzing monitoring data is the Skype for Business Server Monitoring Reports.</span></span> <span data-ttu-id="0ab77-108">Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service.</span><span class="sxs-lookup"><span data-stu-id="0ab77-108">Monitoring Reports are a set of standard reports that are published by Microsoft SQL Server Reporting Service.</span></span> <span data-ttu-id="0ab77-109">Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в база данных CDR и QoE.</span><span class="sxs-lookup"><span data-stu-id="0ab77-109">These reports, which are accessible by using a web browser, provide usage, call diagnostic information, and media quality information, all based on call detail recording (CDR) and Quality of Experience (QoE) records stored in the CDR and QoE databases.</span></span> <span data-ttu-id="0ab77-110">Отчеты мониторинга погрузят в Skype для бизнеса Server и могут быть установлены с помощью мастера развертывания Skype для бизнеса Server после установки Skype для бизнеса Server и настройки мониторинга.</span><span class="sxs-lookup"><span data-stu-id="0ab77-110">Monitoring Reports ship with Skype for Business Server and can be installed from the Skype for Business Server Deployment Wizard after Skype for Business Server has been installed and monitoring has been configured.</span></span>
  
<span data-ttu-id="0ab77-p103">Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0ab77-p103">As noted, Monitoring Reports requires the use of SQL Server Reporting Service. SQL Server Reporting Service can be installed at the same time you install SQL Server or can be installed any time after SQL Server itself has been installed.</span></span>
  
<span data-ttu-id="0ab77-113">Дополнительные сведения см. в разделе "Установка отчетов [мониторинга в Skype для бизнеса Server".](../../deploy/deploy-monitoring/install-monitoring-reports.md)</span><span class="sxs-lookup"><span data-stu-id="0ab77-113">For more information, see the topic [Install Monitoring Reports in Skype for Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).</span></span>
  

