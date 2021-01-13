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
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Доступ к данным мониторинга в Skype для бизнеса Server
 
**Сводка:** Сведения о данных мониторинга, используемых в Skype для бизнеса Server.
  
Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.
  
Одним из средств, которые следует рассмотреть для доступа к данным мониторинга и их анализа, является отчеты мониторинга Skype для бизнеса Server. Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service. Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в база данных CDR и QoE. Отчеты мониторинга погрузят в Skype для бизнеса Server и могут быть установлены с помощью мастера развертывания Skype для бизнеса Server после установки Skype для бизнеса Server и настройки мониторинга.
  
Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.
  
Дополнительные сведения см. в разделе "Установка отчетов [мониторинга в Skype для бизнеса Server".](../../deploy/deploy-monitoring/install-monitoring-reports.md)
  

