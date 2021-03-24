---
title: Добавление хранилища архивации переднего плана
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Архивативная обработка требует поддерживаемого 64-битного выпуска программного Microsoft SQL Server базы данных для хранения данных архива. Вы можете выбрать ранее указанную базу данных SQL Server, которая будет использоваться для архива, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором должна находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию). , или имени экземпляра, который вы указываете).
ms.openlocfilehash: 9f3ee74944ca19f827229bcfcaea2a1e37d2bfcb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107845"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="d5833-104">Добавление хранилища архивации переднего плана</span><span class="sxs-lookup"><span data-stu-id="d5833-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="d5833-105">Архивативная обработка требует поддерживаемого 64-битного выпуска программного Microsoft SQL Server базы данных для хранения данных архива.</span><span class="sxs-lookup"><span data-stu-id="d5833-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="d5833-106">Вы можете выбрать ранее указанную базу данных SQL Server, которая будет использоваться для архива, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором должна находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию). , или имени экземпляра, который вы указываете).</span><span class="sxs-lookup"><span data-stu-id="d5833-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="d5833-107">Если учетная запись, использованная для публикации топологии, обладает достаточными правами и разрешениями, при публикации топологии вы можете создать базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="d5833-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="d5833-108">Вы также можете создать базу данных позже, включив ее в процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="d5833-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="d5833-109">Чтобы установить и развернуть базы данных на сервере SQL Server для мониторинга, необходимо быть членом группы SQL Server sysadmins для сервера SQL Server, на котором вы устанавливаете файлы баз данных.</span><span class="sxs-lookup"><span data-stu-id="d5833-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="d5833-110">Если вы не входите в группу SQL Server sysadmin, необходимо запросить, чтобы вы были добавлены в группу до развертывания файлов баз данных.</span><span class="sxs-lookup"><span data-stu-id="d5833-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="d5833-111">Если вы не можете быть членом группы sysadmins, необходимо предоставить администратору SQL Server базы данных сценарий для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="d5833-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="d5833-112">Сведения о пользовательских правах и разрешениях, необходимых для выполнения соответствующих процедур, см. в разделе [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d5833-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) in the Deployment documentation.</span></span>