---
title: Добавление хранилища SQL для сервера архивации
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Сервер архива требует поддерживаемого 64-битного выпуска программного обеспечения SQL Server базы данных для хранения архивных данных. Вы можете выбрать ранее указанную базу данных SQL Server, которая будет использоваться для архива, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, и экземпляр SQL Server, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию или именем, который вы указываете).
ms.openlocfilehash: 813b6f75db61153c704d2300341cac28bd16cc3c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119838"
---
# <a name="add-archiving-server-sql-server-store"></a><span data-ttu-id="5670b-104">Добавление хранилища SQL для сервера архивации</span><span class="sxs-lookup"><span data-stu-id="5670b-104">Add Archiving Server SQL Server Store</span></span>

<span data-ttu-id="5670b-105">Сервер архива требует поддерживаемого 64-битного выпуска программного обеспечения SQL Server базы данных для хранения архивных данных.</span><span class="sxs-lookup"><span data-stu-id="5670b-105">Archiving Server requires a supported 64-bit edition of the SQL Server database software to store the archive data.</span></span> <span data-ttu-id="5670b-106">Вы можете выбрать ранее указанную базу данных SQL Server, которая будет использоваться для архива, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, и экземпляр SQL Server, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию или именем, который вы указываете).</span><span class="sxs-lookup"><span data-stu-id="5670b-106">You can either select a previously defined SQL Server database to be used for archiving or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database will reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="5670b-p103">Если учетная запись, используемая для публикации топологии, имеет соответствующие пользовательские права и разрешения, можно создать базу данных архивации (LcsLog) непосредственно при публикации топологии. Можно также создать эту базу данных позже, в рамках процедуры установки или в другое время.</span><span class="sxs-lookup"><span data-stu-id="5670b-p103">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the archiving database (LcsLog) when you publish your topology. You can also create the database later, as part of the installation procedure, or otherwise.</span></span>

> [!NOTE]
> <span data-ttu-id="5670b-109">Чтобы установить и развернуть базы данных на сервере SQL Server для архива, необходимо быть членом группы SQL Server sysadmins для сервера на SQL Server, на котором устанавливаются файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="5670b-109">To install and deploy the databases on the SQL Server-based server for archiving, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="5670b-110">Если вы не входите в группу SQL Server sysadmins, необходимо попросить добавить их в группу до развертывания файлов баз данных.</span><span class="sxs-lookup"><span data-stu-id="5670b-110">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="5670b-111">Если вы не можете быть членом группы sysadmins, необходимо предоставить администратору SQL Server базы данных сценарий для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="5670b-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="5670b-112">Сведения о пользовательских правах и разрешениях, необходимых для выполнения соответствующих процедур, см. в разделе [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="5670b-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>