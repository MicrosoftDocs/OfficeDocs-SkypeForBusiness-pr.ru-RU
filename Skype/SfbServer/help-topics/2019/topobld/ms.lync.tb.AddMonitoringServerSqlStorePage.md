---
title: Добавление хранилища SQL Server для сервера мониторинга
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: Для хранения данных мониторинга на сервере мониторинга требуется поддерживаемое 64-битное SQL Server программного обеспечения базы данных. Вы можете выбрать ранее SQL Server базу данных, которая будет использоваться для мониторинга, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который вы хотите использовать для нового SQL Server базы данных (которая может быть экземпляром по умолчанию или названным экземпляром, который вы указываете).
ms.openlocfilehash: ca7f2e407bf367a7ff544d08105e6af533454ba2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395961"
---
# <a name="add-monitoring-server-sql-server-store"></a>Добавление хранилища SQL Server для сервера мониторинга

Для хранения данных мониторинга на сервере мониторинга требуется поддерживаемое 64-битное SQL Server программного обеспечения базы данных. Вы можете выбрать ранее SQL Server базу данных, которая будет использоваться для мониторинга, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который вы хотите использовать для нового SQL Server базы данных (которая может быть экземпляром по умолчанию или названным экземпляром, который вы указываете).

Сведения о поддержке SQL Server см. в документации по [](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) поддержке программного обеспечения базы данных и кластерной поддержки. Подробные сведения о базе данных мониторинга, в том числе коллокация базы данных мониторинга, см. в документе Support [Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation, [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.

> [!NOTE]
> Если учетная запись, использованная для публикации топологии, обладает достаточными правами и разрешениями, при публикации топологии вы можете создать базу данных мониторинга. Эту базу данных можно создать и позднее — в рамках процедуры установки. > Для установки и развертывания баз данных на сервере SQL Server для мониторинга необходимо быть членом группы SQL Server sysadmins для сервера на SQL Server, на котором устанавливаются файлы баз данных. Если вы не входите в группу SQL Server sysadmin, необходимо попросить добавить их в группу до развертывания файлов баз данных. Если вы не можете быть членом группы sysadmins, необходимо предоставить администратору SQL Server базы данных сценарий для настройки и развертывания баз данных. Дополнительные сведения о правах и разрешениях, требуемых для выполнения описанных процедур, см. в разделе [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) документации по развертыванию.