---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных. Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.
ms.openlocfilehash: 531d4c06daa7dacd2a616244c13207b3e79dca4c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898742"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Удаление экземпляров и баз данных SQL Server на внутреннем сервере

Удаление базы данных Microsoft SQL Server и экземпляры после удаления серверы, работающие с их, либо после повторно настройте серверы для другой базы данных. Необходимо выполнить процедуры в данном разделе при удаление текущего сервера SQL или перенастройте текущего сервера таким образом, что он функционирует баз данных устаревший или недоступен.
  
Чтобы удалить базы данных или экземпляры для архивации сервера или сервера мониторинга, сначала необходимо удалить роли сервера. Аналогично удаление экземпляров и баз данных для пула переднего плана, необходимо сначала удалить или повторно настройте зависимые серверной роли. Эти процедуры сделать нет различий между выровненные базы данных или отдельных экземпляров для серверов. Процедуры не влияет на выровненное размещение баз данных.
  
## <a name="in-this-section"></a>Содержание

- [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Удаление базы данных SQL Server для сервера мониторинга](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Удаление базы данных SQL Server для сервера архивирования](remove-the-sql-server-database-for-an-archiving-server.md)
    

