---
title: Добавление хранилища SQL Server для сервера переднего плана
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
ROBOTS: NOINDEX, NOFOLLOW
description: Развертывание выпуск Standard автоматически устанавливает необходимое программное обеспечение Microsoft SQL Server Express базы данных и SQL Server базы данных. Таким образом, все параметры являются преднаселенной, и вы не можете внести изменения в конфигурацию по умолчанию.
ms.openlocfilehash: 211e3213489d26682e12b8b39955ad4e1577abf6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776779"
---
# <a name="add-front-end-sql-server-store"></a>Добавление хранилища SQL Server для сервера переднего плана

Развертывание выпуск Standard автоматически устанавливает необходимое программное обеспечение Microsoft SQL Server Express базы данных и SQL Server базы данных. Таким образом, все параметры являются преднаселенной, и вы не можете внести изменения в конфигурацию по умолчанию.

Для переднего выпуск Enterprise серверов требуется поддерживаемое 64-битное издание программного обеспечения SQL Server базы данных для задней базы данных. Вы можете выбрать ранее указанную базу данных SQL Server, которая будет использоваться для базы данных задней части, или определить новую базу данных SQL Server, указав полностью квалифицированное доменное имя (FQDN) сервера, на котором должна находиться база данных SQL Server, и экземпляр SQL Server, который вы хотите использовать для новой базы данных SQL Server (которая может быть экземпляром по умолчанию или именем, который вы указываете). Вы также можете включить зеркальное отображение для хранилища SQL Server и указать свидетеля зеркалирования для автоматической отработки отказа.

Сведения о поддержке SQL Server см. в документации по поддержке программного обеспечения базы данных и кластерной поддержки. [](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support) Сведения о настройке SQL Server для базы данных задней части см. в SQL Server документации по развертыванию. [](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)

> [!NOTE]
> Если учетная запись, использованная для публикации топологии, обладает достаточными правами и разрешениями, при публикации топологии вы можете создать внутреннюю базу данных (связь в реальном времени — RTC). Эту базу данных можно создать и позднее — в рамках процедуры установки.

> [!NOTE]
> Чтобы установить и развернуть базы данных на SQL Server сервере для развертывания выпуск Enterprise, необходимо быть членом группы SQL Server sysadmins для сервера SQL Server, на котором вы устанавливаете файлы баз данных. Если вы не входите в группу SQL Server sysadmins, необходимо попросить добавить их в группу до развертывания файлов баз данных. Если вы не можете быть членом группы sysadmins, необходимо предоставить администратору SQL Server базы данных сценарий для настройки и развертывания баз данных. Дополнительные сведения о правах и разрешениях, требуемых для выполнения описанных процедур, см. в разделе [Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server).