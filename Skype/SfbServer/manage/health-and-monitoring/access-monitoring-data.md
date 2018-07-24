---
title: Мониторинг данных в Скайп для Business Server Access
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Сводка: Сведения о данных наблюдения, используемые в Скайп для Business Server.'
ms.openlocfilehash: 4bd7d7c55f2d041d1bd3d80cf056544cd5bf5ee1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986588"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>Мониторинг данных в Скайп для Business Server Access
 
**Сводка:** Сведения о данных наблюдения, используемые в Скайп для Business Server.
  
Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.
  
Одно средство, которое необходимо учитывать на доступ и анализ данных наблюдения является Скайп для отчетов мониторинга Business Server. Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service. Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в базе данных CDR и QoE. Отчетов мониторинга имеющимся в Скайп для Business Server и может быть установлена из Скайп для мастер развертывания Business Server после установки Скайп для Business Server и настроить мониторинг.
  
Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.
  
Дополнительные сведения см в разделе [Установка отчетов мониторинга в Скайп для Business Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

