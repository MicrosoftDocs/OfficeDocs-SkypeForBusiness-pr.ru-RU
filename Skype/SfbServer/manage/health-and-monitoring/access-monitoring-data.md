---
title: Мониторинг данных в Скайп для Business Server Access
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Сводка: Сведения о данных наблюдения, используемые в Скайп для Business Server.'
ms.openlocfilehash: 096a20119f0d7f368165aae53e2b3164cb817d63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885050"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Мониторинг данных в Скайп для Business Server Access
 
**Сводка:** Сведения о данных наблюдения, используемые в Скайп для Business Server.
  
Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.
  
Одно средство, которое необходимо учитывать на доступ и анализ данных наблюдения является Скайп для отчетов мониторинга Business Server. Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service. Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в базе данных CDR и QoE. Отчетов мониторинга имеющимся в Скайп для Business Server и может быть установлена из Скайп для мастер развертывания Business Server после установки Скайп для Business Server и настроить мониторинг.
  
Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.
  
Дополнительные сведения см в разделе [Установка отчетов мониторинга в Скайп для Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

