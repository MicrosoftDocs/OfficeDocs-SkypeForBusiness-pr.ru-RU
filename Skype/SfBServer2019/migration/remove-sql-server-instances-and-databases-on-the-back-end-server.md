---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления серверов, которые зависят от них, или после повторной настройки серверов для использования другой базы данных. Если вы выпустили текущий SQL-сервер или перенастройте текущий сервер таким образом, чтобы они выглядели устаревшими или недоступными, необходимо выполнить описанные в этой статье действия.
ms.openlocfilehash: 01552fcd494514802fffb35de7db7643f8cc26fd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812987"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Удаление экземпляров и баз данных SQL Server на внутреннем сервере

Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления серверов, которые зависят от них, или после повторной настройки серверов для использования другой базы данных. Если вы выпустили текущий SQL-сервер или перенастройте текущий сервер таким образом, чтобы они выглядели устаревшими или недоступными, необходимо выполнить описанные в этой статье действия.
  
Чтобы удалить базы данных или экземпляры сервера архивирования или сервера мониторинга, необходимо сначала удалить роль сервера. Аналогичным образом для удаления экземпляров или баз данных в пуле переднего плана необходимо сначала удалить или перенастроить роль зависимого сервера. Эти процедуры не различаются между выровненными базами данных и отдельными экземплярами серверов. Расгруппировка баз данных не влияет на эти процедуры.
  
## <a name="in-this-section"></a>В этом разделе

- [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Удаление базы данных SQL Server для сервера мониторинга](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Удаление базы данных SQL Server для сервера архивирования](remove-the-sql-server-database-for-an-archiving-server.md)
    

