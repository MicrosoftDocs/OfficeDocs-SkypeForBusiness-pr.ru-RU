---
title: Добавление хранилища архивации переднего плана
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: Архивация требует с поддерживаемой 64-разрядной версией программного обеспечения баз данных Microsoft SQL Server для хранения архивных данных. Можно выбрать ранее заданных базы данных SQL Server, которое будет использоваться для архивации, или определите новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором размещаются в дополнение к экземпляру SQL Se базы данных SQL Server на сервере, который вы хотите использовать для новой базы данных SQL Server (который может быть экземпляр по умолчанию или именованный экземпляр, который указан).
ms.openlocfilehash: bbdcd20333897078dea7deddc716d67dcca1b2f5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873495"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="69fb2-104">Добавление хранилища архивации переднего плана</span><span class="sxs-lookup"><span data-stu-id="69fb2-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="69fb2-105">Архивация требует с поддерживаемой 64-разрядной версией программного обеспечения баз данных Microsoft SQL Server для хранения архивных данных.</span><span class="sxs-lookup"><span data-stu-id="69fb2-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="69fb2-106">Можно выбрать ранее заданных базы данных SQL Server, которое будет использоваться для архивации, или определите новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором размещаются в дополнение к экземпляру SQL Se базы данных SQL Server на сервере, который вы хотите использовать для новой базы данных SQL Server (который может быть экземпляр по умолчанию или именованный экземпляр, который указан).</span><span class="sxs-lookup"><span data-stu-id="69fb2-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="69fb2-107">Если учетная запись, используемая для публикации топологии есть соответствующие права и разрешения, можно создать базу данных мониторинга при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="69fb2-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="69fb2-108">Базу данных можно создать и позднее в ходе процедуры установки.</span><span class="sxs-lookup"><span data-stu-id="69fb2-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="69fb2-109">Установка и развертывание базы данных на сервере под управлением SQL Server для мониторинга, необходимо быть членом группы системных администраторов SQL Server для сервера под управлением SQL Server, где выполняется установка файлов базы данных.</span><span class="sxs-lookup"><span data-stu-id="69fb2-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="69fb2-110">Если вы не должна быть членом группы системных администраторов SQL Server, необходимо запросить, что вы добавляется в группу, пока не развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="69fb2-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="69fb2-111">Если невозможно выполнить должна быть членом группы системных администраторов, предоставьте администратору базы данных SQL Server с помощью сценария для настройки и развертывания базы данных.</span><span class="sxs-lookup"><span data-stu-id="69fb2-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="69fb2-112">Для получения дополнительных сведений о правах пользователей и разрешения, которые необходимы для выполнения процедур содержатся в документации по развертыванию [Разрешения на развертывание для SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) .</span><span class="sxs-lookup"><span data-stu-id="69fb2-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


