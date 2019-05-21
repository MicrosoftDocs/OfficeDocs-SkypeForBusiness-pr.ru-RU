---
title: Добавление хранилища архивации переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: Для хранения данных архивации требуется поддерживаемая 64-разрядная версия приложения для работы с базами данных Microsoft SQL Server. Вы можете выбрать ранее определенную базу данных SQL Server, которая будет использоваться для архивации, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, в дополнение к экземпляру SQL SE. рвер, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию, или указанным именованным экземпляром).
ms.openlocfilehash: 5c55567b134af368296cc628e1e1297df1a8389a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283950"
---
# <a name="add-front-end-archiving-store"></a><span data-ttu-id="befcf-104">Добавление хранилища архивации переднего плана</span><span class="sxs-lookup"><span data-stu-id="befcf-104">Add Front End Archiving Store</span></span>

<span data-ttu-id="befcf-105">Для хранения данных архивации требуется поддерживаемая 64-разрядная версия приложения для работы с базами данных Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="befcf-105">Archiving requires a supported 64-bit edition of the Microsoft SQL Server database software to store the archiving data.</span></span> <span data-ttu-id="befcf-106">Вы можете выбрать ранее определенную базу данных SQL Server, которая будет использоваться для архивации, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, в дополнение к экземпляру SQL SE. рвер, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию, или указанным именованным экземпляром).</span><span class="sxs-lookup"><span data-stu-id="befcf-106">You can either select a previously defined SQL Server database to be used for archiving, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, in addition to the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span>

> [!NOTE]
> <span data-ttu-id="befcf-107">Если учетная запись, используемая для публикации топологии, имеет соответствующие права и разрешения пользователей, вы можете создать базу данных мониторинга при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="befcf-107">If the account used to publish the topology has the appropriate user rights and permissions, you can create the monitoring database when you publish your topology.</span></span> <span data-ttu-id="befcf-108">Базу данных можно создать и позднее в ходе процедуры установки.</span><span class="sxs-lookup"><span data-stu-id="befcf-108">You can also create the database later, included as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="befcf-109">Чтобы установить и развернуть базы данных на сервере SQL Server для мониторинга, необходимо быть членом группы "Администраторы SQL Server" на сервере SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="befcf-109">To install and deploy the databases on the SQL Server-based server for monitoring, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="befcf-110">Если вы не являетесь членом группы sysadmin сервера SQL Server, вы должны запросить Добавление в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="befcf-110">If you are not a member of the SQL Server sysadmin group, you must request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="befcf-111">Если вы не можете стать членом группы администраторов, вы должны предоставить администратору базы данных SQL Server сценарий для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="befcf-111">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="befcf-112">Подробные сведения о правах пользователей и разрешениях, необходимых для выполнения этих процедур, приведены в разделе [разрешения на развертывание SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="befcf-112">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx) in the Deployment documentation.</span></span>


