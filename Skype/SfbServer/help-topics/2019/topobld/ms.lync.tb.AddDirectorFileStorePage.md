---
title: Добавление файлового хранилища Директора
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
ROBOTS: NOINDEX, NOFOLLOW
description: Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для директоров. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: 47ff804eec897d1bf54dd2d012b777b022cd515e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62400933"
---
# <a name="add-director-file-store"></a>Добавление файлового хранилища директора

Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для директоров. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.

> [!IMPORTANT]
> При добавлении директоров в топологию для публикации топологии требуется доступ, позволяющий настроить хранилище файлов и сконфигурировать списки управления доступом на уровне пользователей (DACL) для общего файлового ресурса, который используется для хранилища файлов. При запуске построителя топологии и публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса.

Сведения о поддержке хранения для файловых акций см. в служба хранилища [в](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) документации по поддержке и SQL Server и размещении файлов журнала в документации развертывания.[](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) Дополнительные сведения о выровненном размещении общего файлового ресурса см. в разделе [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) в документации по поддержке. Дополнительные сведения о разработке топологии для директоров см. в разделе [Define a Single Director in Topology Builder](/previous-versions/office/lync-server-2013/lync-server-2013-define-optional-director-topologies-in-your-topology) документации по развертыванию.