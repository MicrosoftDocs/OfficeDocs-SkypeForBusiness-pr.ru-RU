---
title: Добавление хранилища SQL для сервера архивации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
description: Для хранения архивных данных сервер архивации должен поддерживать 64-разрядную выпускную базу данных SQL Server. Вы можете либо выбрать ранее определенную базу данных SQL Server, которая будет использоваться для архивации, либо определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, и экземпляр SQL Server, который Вы хотите использовать для новой базы данных SQL Server (которая может быть задана экземпляром по умолчанию или именованным экземпляром).
ms.openlocfilehash: cda788a83b67b94f4064ca2f967878b88527b0c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304942"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="e52e9-104">Добавление хранилища SQL для сервера архивации</span><span class="sxs-lookup"><span data-stu-id="e52e9-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="e52e9-105">Для хранения архивных данных сервер архивации должен поддерживать 64-разрядную выпускную базу данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e52e9-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="e52e9-106">Вы можете либо выбрать ранее определенную базу данных SQL Server, которая будет использоваться для архивации, либо определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, и экземпляр SQL Server, который Вы хотите использовать для новой базы данных SQL Server (которая может быть задана экземпляром по умолчанию или именованным экземпляром).</span><span class="sxs-lookup"><span data-stu-id="e52e9-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="e52e9-107">Если учетная запись, используемая для публикации топологии, имеет соответствующие права и разрешения пользователей, вы можете создать базу данных архивации (Лкслог) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="e52e9-107">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="e52e9-108">Вы также можете создать базу данных позже в ходе процедуры установки или в других случаях.</span><span class="sxs-lookup"><span data-stu-id="e52e9-108">You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="e52e9-109">Чтобы установить и развернуть базы данных на сервере SQL Server для архивации, необходимо быть членом группы "Администраторы SQL Server" для сервера SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="e52e9-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="e52e9-110">Если вы не являетесь членом группы "Администраторы" сервера SQL Server, вы должны добавить запрос в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="e52e9-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="e52e9-111">Если вы не можете стать членом группы администраторов, вы должны предоставить администратору базы данных SQL Server сценарий для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="e52e9-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="e52e9-112">Подробные сведения о правах пользователей и разрешениях, необходимых для выполнения этих процедур, приведены в разделе [разрешения на развертывание SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e52e9-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


