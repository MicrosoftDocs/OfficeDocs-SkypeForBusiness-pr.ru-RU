---
title: Доступ к данным наблюдения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Сводка: сведения о контрольных данных, используемых в Skype для бизнеса Server.'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303890"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Доступ к данным наблюдения в Skype для бизнеса Server
 
**Сводка:** Сведения о мониторинге данных, используемых в Skype для бизнеса Server.
  
Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.
  
Для получения доступа к данным мониторинга и анализа данных, которые необходимо использовать в Skype для бизнеса Server, следует ознакомиться с отчетами мониторинга. Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service. Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в базе данных CDR и QoE. Наблюдение за отчетами в Skype для бизнеса Server и их установка с помощью мастера развертывания Skype для бизнеса Server после установки и настройки мониторинга в Skype для бизнеса Server.
  
Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.
  
Дополнительные сведения можно найти [в разделе Установка отчетов по мониторингу в Skype для бизнеса Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

