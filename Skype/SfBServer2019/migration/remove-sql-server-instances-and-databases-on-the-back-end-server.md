---
title: Удаление экземпляров SQL Server и баз данных на фоновый сервер
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных. Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.
ms.openlocfilehash: 648c808ee293c4fa33352d0f68ba337e4a489d27
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027881"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Удаление экземпляров SQL Server и баз данных на фоновый сервер

Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных. Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.
  
Чтобы удалить базы данных или экземпляры для архивации сервера или сервера мониторинга, сначала необходимо удалить роли сервера. Аналогично удаление экземпляров и баз данных для пула переднего плана, необходимо сначала удалить или повторно настройте зависимые серверной роли. Эти процедуры сделать нет различий между выровненные базы данных или отдельных экземпляров для серверов. Процедуры не влияет на выровненное размещение баз данных.
  
## <a name="in-this-section"></a>Содержание

- [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Удаление базы данных SQL Server для сервера мониторинга](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Удаление базы данных SQL Server для сервера архивации](remove-the-sql-server-database-for-an-archiving-server.md)
    

