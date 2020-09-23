---
title: Добавление хранилища архивации переднего плана
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
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Для хранения архивных данных требуется поддерживаемый 64 (bit) выпуск программного обеспечения базы данных Microsoft SQL Server. Вы можете выбрать ранее определенную базу данных SQL Server для архивации или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет размещаться база данных SQL Server, а также экземпляр SQL Server, который нужно использовать для новой базы данных SQL Server (который может быть экземпляром по умолчанию). или именованный экземпляр, который вы указали.
ms.openlocfilehash: 0cf61aa758b2228c065659f518c81d637022ff47
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216720"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="490d9-104">Добавление хранилища архивации переднего плана</span><span class="sxs-lookup"><span data-stu-id="490d9-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="490d9-105">Для хранения архивных данных требуется поддерживаемый 64 (bit) выпуск программного обеспечения базы данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="490d9-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="490d9-106">Вы можете выбрать ранее определенную базу данных SQL Server для архивации или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет размещаться база данных SQL Server, а также экземпляр SQL Server, который нужно использовать для новой базы данных SQL Server (который может быть экземпляром по умолчанию). или именованный экземпляр, который вы указали.</span><span class="sxs-lookup"><span data-stu-id="490d9-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="490d9-107">Если учетная запись, использованная для публикации топологии, обладает достаточными правами и разрешениями, при публикации топологии вы можете создать базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="490d9-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="490d9-108">Кроме того, вы можете создать базу данных позже, включенную в процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="490d9-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="490d9-109">Чтобы установить и развернуть базы данных на сервере SQL Server для мониторинга, необходимо быть участником группы администраторов SQL Server для сервера SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="490d9-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="490d9-110">Если вы не являетесь участником группы администраторов SQL Server, необходимо запросить Добавление в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="490d9-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="490d9-111">Если вы не можете быть участником группы администраторов, необходимо предоставить администратору базы данных SQL Server скрипт для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="490d9-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="490d9-112">Сведения о пользовательских правах и разрешениях, необходимых для выполнения соответствующих процедур, см. в разделе [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="490d9-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


