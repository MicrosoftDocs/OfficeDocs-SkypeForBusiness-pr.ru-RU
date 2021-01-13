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
description: Для архивных данных требуется поддерживаемый 64-Microsoft SQL Server программного обеспечения базы данных архива. Можно выбрать ранее задаваемую базу данных SQL Server для архива или определить новую базу данных SQL Server, указав полное доменное имя сервера, на котором должна находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который требуется использовать для новой базы данных SQL Server (который может быть экземпляром по умолчанию). , или именуемом экземпляре, который вы указали).
ms.openlocfilehash: 9e094bacca87e6b70a7caa1db9c43a5c98c0edbd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824219"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="556d5-104">Добавление хранилища архивации переднего плана</span><span class="sxs-lookup"><span data-stu-id="556d5-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="556d5-105">Для архивных данных требуется поддерживаемый 64-Microsoft SQL Server программного обеспечения базы данных архива.</span><span class="sxs-lookup"><span data-stu-id="556d5-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="556d5-106">Можно выбрать ранее задаваемую базу данных SQL Server для архива или определить новую базу данных SQL Server, указав полное доменное имя сервера, на котором должна находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который требуется использовать для новой базы данных SQL Server (который может быть экземпляром по умолчанию). , или именуемом экземпляре, который вы указали).</span><span class="sxs-lookup"><span data-stu-id="556d5-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="556d5-107">Если учетная запись, использованная для публикации топологии, обладает достаточными правами и разрешениями, при публикации топологии вы можете создать базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="556d5-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="556d5-108">Вы также можете создать базу данных позже, включив ее в процедуру установки.</span><span class="sxs-lookup"><span data-stu-id="556d5-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="556d5-109">Чтобы установить и развернуть базы данных на сервере SQL Server для мониторинга, необходимо быть участником группы SQL Server sysadmins для сервера SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="556d5-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="556d5-110">Если вы не входите в группу SQL Server sysadmin, необходимо запросить, чтобы вы были добавлены в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="556d5-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="556d5-111">Если вы не можете быть членом группы sysadmins, необходимо предоставить администратору SQL Server базы данных сценарий для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="556d5-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="556d5-112">Сведения о пользовательских правах и разрешениях, необходимых для выполнения соответствующих процедур, см. в разделе [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="556d5-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


