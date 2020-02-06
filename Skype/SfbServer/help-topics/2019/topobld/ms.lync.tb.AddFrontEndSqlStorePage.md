---
title: Добавление хранилища SQL Server для сервера переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Развертывание сервера Standard Edition автоматически устанавливает необходимое программное обеспечение Microsoft SQL Server Express Database Server и базу данных SQL Server. Таким образом, все параметры предварительно заполнены, и вы не можете изменить конфигурацию по умолчанию.
ms.openlocfilehash: 58b0af996e418a3db5852571cec6fa82380dde76
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798516"
---
# <a name="add-front-end-sql-server-store"></a><span data-ttu-id="16e33-104">Добавление хранилища SQL Server для сервера переднего плана</span><span class="sxs-lookup"><span data-stu-id="16e33-104">Add Front End SQL Server Store</span></span>

<span data-ttu-id="16e33-105">Развертывание сервера Standard Edition автоматически устанавливает необходимое программное обеспечение Microsoft SQL Server Express Database Server и базу данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="16e33-105">A Standard Edition server deployment automatically installs the required Microsoft SQL Server Express database software and SQL Server database.</span></span> <span data-ttu-id="16e33-106">Таким образом, все параметры предварительно заполнены, и вы не можете изменить конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="16e33-106">Therefore, all options are prepopulated, and you can't make changes to the default configuration.</span></span>

<span data-ttu-id="16e33-107">В пуле переднего плана для развертывания сервера Enterprise Edition требуется поддерживаемая версия 64 для базы данных SQL Server для серверной части базы данных.</span><span class="sxs-lookup"><span data-stu-id="16e33-107">The Front End pool of an Enterprise Edition server deployment requires a supported 64-bit edition of the SQL Server database software for the back-end database.</span></span> <span data-ttu-id="16e33-108">Вы можете либо выбрать ранее определенную базу данных SQL Server, которая будет использоваться для серверной базы данных, либо определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором находится база данных SQL Server, и экземпляр SQL S. ервер, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию, или указанным именованным экземпляром).</span><span class="sxs-lookup"><span data-stu-id="16e33-108">You can either select a previously defined SQL Server database to be used for the back-end database, or define a new SQL Server database by specifying a fully qualified domain name (FQDN) of the server on which the SQL Server database is to reside, and the instance of SQL Server that you want to use for the new SQL Server database (which can be the default instance, or a named instance that you specify).</span></span> <span data-ttu-id="16e33-109">Вы также можете включить зеркальное отображение в хранилище SQL Server и задать следящий сервер зеркального отображения для автоматического перехода на другой ресурс.</span><span class="sxs-lookup"><span data-stu-id="16e33-109">You can also choose to enable mirroring on the SQL Server store, and specify a mirroring witness for automatic failover.</span></span>

<span data-ttu-id="16e33-110">Подробные сведения о поддержке сервера SQL Server можно найти в документации по [базам данных и поддержке кластеров](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) .</span><span class="sxs-lookup"><span data-stu-id="16e33-110">For details about SQL Server support, see [Database Software and Clustering Support](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="16e33-111">Подробные сведения о настройке SQL Server для серверной базы данных можно найти в разделе [Настройка SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="16e33-111">For details about setting up SQL Server for the back-end database, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) in the Deployment documentation.</span></span>

> [!NOTE]
> <span data-ttu-id="16e33-112">Если учетная запись, используемая для публикации топологии, имеет соответствующие права и разрешения, вы можете создать серверную базу данных (в режиме реального времени) при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="16e33-112">If the account that is used to publish the topology has the appropriate user rights and permissions, you can create the back-end database (real-time communications (RTC)) when you publish your topology.</span></span> <span data-ttu-id="16e33-113">Кроме того, вы можете создать базу данных позже, в том числе в ходе процедуры установки.</span><span class="sxs-lookup"><span data-stu-id="16e33-113">You can also create the database later, including as part of the installation procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="16e33-114">Чтобы установить и развернуть базы данных на сервере SQL Server для развертывания Enterprise Edition, вы должны быть участником группы "Администраторы SQL Server" на сервере SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="16e33-114">To install and deploy the databases on the SQL Server-based server for an Enterprise Edition deployment, you must be a member of the SQL Server sysadmins group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="16e33-115">Если вы не являетесь членом группы "Администраторы" сервера SQL Server, вы должны добавить запрос в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="16e33-115">If you are not a member of the SQL Server sysadmins group, you must request to be added to the group until the database files are deployed.</span></span> <span data-ttu-id="16e33-116">Если вы не можете стать членом группы администраторов, вы должны предоставить администратору базы данных SQL Server сценарий для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="16e33-116">If you cannot be made a member of the sysadmins group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="16e33-117">Подробные сведения о правах пользователей и разрешениях, необходимых для выполнения этих процедур, приведены в разделе [разрешения на развертывание для SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span><span class="sxs-lookup"><span data-stu-id="16e33-117">For details about the user rights and permissions that you need to accomplish the procedures, see [Deployment Permissions for SQL Server](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx).</span></span>


