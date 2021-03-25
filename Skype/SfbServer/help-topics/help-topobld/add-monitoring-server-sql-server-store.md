---
title: Добавление хранилища SQL Server для сервера мониторинга
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: Для мониторинга Server требуется поддерживаемое 64-битное издание программного SQL Server базы данных для хранения данных мониторинга. Вы можете выбрать ранее SQL Server базу данных, которая будет использоваться для мониторинга, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию). , или имени экземпляра, который вы указываете).
ms.openlocfilehash: 5c1ef4c7b2474a094492aa7905c044a5da145ff5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119728"
---
# <a name="add-monitoring-server-sql-server-store"></a>Добавление хранилища SQL Server для сервера мониторинга

Для мониторинга Server требуется поддерживаемое 64-битное издание программного SQL Server базы данных для хранения данных мониторинга. Вы можете выбрать ранее SQL Server базу данных, которая будет использоваться для мониторинга, или определить новую базу данных SQL Server, указав полное доменное имя (FQDN) сервера, на котором будет находиться база данных SQL Server, в дополнение к экземпляру SQL Server, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию). , или имени экземпляра, который вы указываете).

Сведения о поддержке SQL Server см. [](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) в документации по поддержке программного обеспечения базы данных и кластерной поддержки. Подробные сведения о базе данных мониторинга, в том [](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) числе коллокация базы данных[](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) мониторинга, см. в документации по поддержке серверов [SQL Server,](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) планировании мониторинга в документации по планированию и размещении данных и файлов журналов в документации по развертыванию.

> [!NOTE]
> Если учетная запись, использованная для публикации топологии, обладает достаточными правами и разрешениями, при публикации топологии вы можете создать базу данных мониторинга. Эту базу данных можно создать и позднее — в рамках процедуры установки. > для установки и развертывания баз данных на сервере SQL Server для мониторинга необходимо быть членом группы SQL Server sysadmins для сервера на SQL Server, на котором устанавливаются файлы баз данных. Если вы не входите в группу SQL Server sysadmin, необходимо попросить добавить их в группу до развертывания файлов баз данных. Если вы не можете быть членом группы sysadmins, необходимо предоставить администратору SQL Server базы данных сценарий для настройки и развертывания баз данных. Дополнительные сведения о правах и разрешениях, требуемых для выполнения описанных процедур, см. в разделе [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) документации по развертыванию.