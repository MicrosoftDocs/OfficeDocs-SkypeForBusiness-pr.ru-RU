---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Удаляйте Microsoft SQL Server базы данных и экземпляры после удаления зависимых от них серверов или после перенастройки серверов для использования другой базы данных. Вам необходимо выполнить процедуру в этом разделе, когда вы SQL Server текущего сервера или перенастроить текущий сервер таким образом, чтобы он делает базы данных устаревшими или недоступными.
ms.openlocfilehash: dafd1589bc4d1624a71998813fe785841cbfb713
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582033"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Удаление экземпляров и баз данных SQL Server на внутреннем сервере

Удаляйте Microsoft SQL Server базы данных и экземпляры после удаления зависимых от них серверов или после перенастройки серверов для использования другой базы данных. Вам необходимо выполнить процедуру в этом разделе, когда вы SQL Server текущего сервера или перенастроить текущий сервер таким образом, чтобы он делает базы данных устаревшими или недоступными.
  
Чтобы удалить базы данных или экземпляры сервера архива или сервера мониторинга, сначала необходимо удалить роль сервера. Кроме того, чтобы удалить экземпляры или базы данных для пула переднего плана, необходимо сначала удалить или перенастроить зависимую роль сервера. Эти процедуры одинаково подходят для баз данных с выровненным размещением и отдельных экземпляров, относящихся к серверам. Выровненное размещение баз данных не влияет на выполнение этих процедур.
  
## <a name="in-this-section"></a>В этой статье

- [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [Удаление базы данных SQL Server для сервера мониторинга](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [Удаление базы данных SQL Server для сервера архивирования](remove-the-sql-server-database-for-an-archiving-server.md)
    

