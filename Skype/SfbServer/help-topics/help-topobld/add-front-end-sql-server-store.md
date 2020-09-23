---
title: Добавление хранилища SQL Server для сервера переднего плана
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
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: Развертывание сервера Standard Edition автоматически устанавливает необходимое программное обеспечение баз данных Microsoft SQL Server Express и базу данных SQL Server. Таким образом, все параметры заполняются заранее, и вы не можете вносить изменения в конфигурацию по умолчанию.
ms.openlocfilehash: 614c3a852bb52a73c8a3f71ee467a2d71f82e9b6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216500"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="d3a2d-104">Добавление хранилища SQL Server для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="d3a2d-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="d3a2d-105">Развертывание сервера Standard Edition автоматически устанавливает необходимое программное обеспечение баз данных Microsoft SQL Server Express и базу данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="d3a2d-106">Таким образом, все параметры заполняются заранее, и вы не можете вносить изменения в конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="d3a2d-107">Интерфейсный пул развертывания Enterprise Edition Server требует наличия поддерживаемого 64 (разрядного) выпуска программного обеспечения базы данных SQL Server для серверной базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="d3a2d-108">Вы можете выбрать ранее определенную базу данных SQL Server, которая будет использоваться для внутренней базы данных, или определить новую базу данных SQL Server, указав полное доменное имя сервера, на котором находится база данных SQL Server, и экземпляр SQL Server, который будет использоваться для новой базы данных SQL Server (который может быть экземпляром по умолчанию). или именованный экземпляр, который вы указали.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="d3a2d-109">Вы также можете включить зеркальное отображение для хранилища SQL Server и указать свидетеля зеркалирования для автоматической отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="d3a2d-110">Подробные сведения о поддержке SQL Server можно найти в статье по поддержке [баз данных и кластеризации](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="d3a2d-111">Подробнее о настройке SQL Server для серверной базы данных можно узнать в статье [Настройка SQL Server для Lync server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server for Lync Server 2010](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="d3a2d-p105">Если учетная запись, использованная для публикации топологии, обладает достаточными правами и разрешениями, при публикации топологии вы можете создать внутреннюю базу данных (связь в реальном времени — RTC). Эту базу данных можно создать и позднее — в рамках процедуры установки.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-p105">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology. You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="d3a2d-114">Чтобы установить и развернуть базы данных на сервере SQL Server для развертывания Enterprise Edition, необходимо быть участником группы администраторов SQL Server для сервера SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="d3a2d-115">Если вы не являетесь членом группы администраторов SQL Server, вам необходимо добавить запрос в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="d3a2d-116">Если вы не можете быть участником группы администраторов, необходимо предоставить администратору базы данных SQL Server скрипт для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="d3a2d-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="d3a2d-117">Дополнительные сведения о правах и разрешениях, требуемых для выполнения описанных процедур, см. в разделе [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="d3a2d-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


