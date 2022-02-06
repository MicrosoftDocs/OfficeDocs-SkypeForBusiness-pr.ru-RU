---
title: Доступ к данным мониторинга в Skype для бизнеса Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: 'Сводка. Сведения о данных мониторинга, используемых в Skype для бизнеса Server.'
---

# <a name="access-monitoring-data-in-skype-for-business-server"></a>Доступ к данным мониторинга в Skype для бизнеса Server
 
**Сводка:** Сведения о данных мониторинга, используемых в Skype для бизнеса Server.
  
Данные мониторинга хранятся в двух базах данных SQL Server: LcsCdr для данных регистрации звонков и QoEMetrics для данных качества взаимодействия. Эти базы данных ничем особенным не выделяются, т. е. доступ к данным в них можно получить с помощью любого средства, которое вы обычно используете для просмотра и анализа данных SQL Server.
  
Одним из средств, которые необходимо учитывать для доступа к данным мониторинга и анализа, является Skype для бизнеса Server отчеты по мониторингу. Отчеты мониторинга — это набор стандартных отчетов, публикуемых службой Microsoft SQL Server Reporting Service. Эти отчеты, доступные в браузере, предоставляют сведения об использовании, диагностики звонков и качестве медиаданных на основе записей регистрации вызовов (CDR) и качества взаимодействия (QoE) в база данных CDR и QoE. Отчеты мониторинга Skype для бизнеса Server и могут быть установлены Skype для бизнеса Server мастером развертывания Skype для бизнеса Server после установки и настройки мониторинга.
  
Как было отмечено, для отчетов мониторинга требуется служба SQL Server Reporting Service, которую можно установить вместе с SQL Server в любое время после установки SQL Server.
  
Дополнительные сведения см. в разделе [Install Monitoring Reports in Skype для бизнеса Server](../../deploy/deploy-monitoring/install-monitoring-reports.md).
  

