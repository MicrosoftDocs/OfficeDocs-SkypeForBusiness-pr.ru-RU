---
title: Добавление хранилища SQL Server для сервера архивации
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Сервер архивации требует с поддерживаемой 64-разрядной версией программного обеспечения баз данных SQL Server для хранения данных архива. Можно выбрать ранее заданных базы данных SQL Server для архивирования, или определите новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором размещаются базы данных SQL Server и экземпляр SQL Server, Вы хотите использовать для новой базы данных SQL Server (который может быть экземпляр по умолчанию или именованный экземпляр, который указан).
ms.openlocfilehash: 80b77efdda5f2a844f92d30fe76a584e8ef25b7e
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988987"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="33207-104">Добавление хранилища SQL Server для сервера архивации</span><span class="sxs-lookup"><span data-stu-id="33207-104">Add Archiving Server SQL Server Store</span></span>
 
<span data-ttu-id="33207-105">Сервер архивации требует с поддерживаемой 64-разрядной версией программного обеспечения баз данных SQL Server для хранения данных архива.</span><span class="sxs-lookup"><span data-stu-id="33207-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="33207-106">Можно выбрать ранее заданных базы данных SQL Server для архивирования, или определите новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором размещаются базы данных SQL Server и экземпляр SQL Server, Вы хотите использовать для новой базы данных SQL Server (который может быть экземпляр по умолчанию или именованный экземпляр, который указан).</span><span class="sxs-lookup"><span data-stu-id="33207-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>
  
> [!NOTE]
> <span data-ttu-id="33207-107">Если учетная запись, используемая для публикации топологии есть соответствующие права и разрешения, можно создать базу данных архивации (LcsLog) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="33207-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="33207-108">Можно также создать базу данных более поздней версии, как часть процесса установки или каким- либо.</span><span class="sxs-lookup"><span data-stu-id="33207-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="33207-109">Установка и развертывание базы данных на сервере под управлением SQL Server для архивации, необходимо быть членом группы системных администраторов SQL Server для сервера под управлением SQL Server, где выполняется установка файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="33207-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="33207-110">Если вы не должна быть членом группы системных администраторов SQL Server, необходимо запрос на добавление в группу до развертывания файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="33207-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="33207-111">Если невозможно выполнить должна быть членом группы системных администраторов, предоставьте администратору базы данных SQL Server с помощью сценария для настройки и развертывания базы данных.</span><span class="sxs-lookup"><span data-stu-id="33207-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="33207-112">Для получения дополнительных сведений о правах пользователей и разрешения, которые необходимы для выполнения процедур содержатся в документации по развертыванию [Разрешения на развертывание для SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) .</span><span class="sxs-lookup"><span data-stu-id="33207-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](http://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>
  

