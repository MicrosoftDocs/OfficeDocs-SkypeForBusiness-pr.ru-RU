---
title: Добавление хранилища SQL для сервера архивации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Для хранения архивных данных сервер архивации требует поддерживаемый 64 bit выпуск программного обеспечения базы данных SQL Server. Вы можете выбрать ранее определенную базу данных SQL Server для архивации или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет размещаться база данных SQL Server, и экземпляр SQL Server, который будет использоваться для новой базы данных SQL Server (например, экземпляр по умолчанию или именованный экземпляр, который вы указали).
ms.openlocfilehash: eb25152916c61ff40274705a408fe0a7a618cbcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217440"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="7c4ca-104">Добавление хранилища SQL для сервера архивации</span><span class="sxs-lookup"><span data-stu-id="7c4ca-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="7c4ca-105">Для хранения архивных данных сервер архивации требует поддерживаемый 64 bit выпуск программного обеспечения базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7c4ca-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="7c4ca-106">Вы можете выбрать ранее определенную базу данных SQL Server для архивации или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет размещаться база данных SQL Server, и экземпляр SQL Server, который будет использоваться для новой базы данных SQL Server (например, экземпляр по умолчанию или именованный экземпляр, который вы указали).</span><span class="sxs-lookup"><span data-stu-id="7c4ca-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="7c4ca-p103">Если учетная запись, используемая для публикации топологии, имеет соответствующие пользовательские права и разрешения, можно создать базу данных архивации (LcsLog) непосредственно при публикации топологии. Можно также создать эту базу данных позже, в рамках процедуры установки или в другое время.</span><span class="sxs-lookup"><span data-stu-id="7c4ca-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="7c4ca-109">Чтобы установить и развернуть базы данных на сервере SQL Server для архивации, необходимо быть участником группы администраторов SQL Server для сервера SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="7c4ca-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="7c4ca-110">Если вы не являетесь членом группы администраторов SQL Server, вам необходимо добавить запрос в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="7c4ca-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="7c4ca-111">Если вы не можете быть участником группы администраторов, необходимо предоставить администратору базы данных SQL Server скрипт для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="7c4ca-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="7c4ca-112">Сведения о пользовательских правах и разрешениях, необходимых для выполнения соответствующих процедур, см. в разделе [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="7c4ca-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


