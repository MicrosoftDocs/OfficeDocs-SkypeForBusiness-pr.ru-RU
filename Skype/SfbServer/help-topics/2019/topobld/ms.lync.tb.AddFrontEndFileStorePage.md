---
title: Добавление хранилища файлов переднего плана
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.
ms.openlocfilehash: 10b07e5bbe075194e393fce8ac9a9c99bc85c01e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397032"
---
# <a name="add-front-end-file-store"></a>Добавление хранилища файлов переднего плана

Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.

> [!IMPORTANT]
> Файл не может быть расположен на переднем выпуск Enterprise сервере, но может быть расположен на выпуск Standard сервере.

> [!IMPORTANT]
> Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии.

> [!IMPORTANT]
> При добавлении в топологию интерфейсного пула Enterprise или сервера Standard Edition построитель топологий должен иметь возможность настройки файлового хранилища и списков управления доступом на уровне пользователей (DACL) для общей папке файлов, которая будет использоваться для файлового хранилища. Для этого требуется войти в систему под учетной записью, имеющей права полного доступа (чтение, запись, изменение) к общей папке файлов при публикации новой топологии в построителей топологий.

Сведения о поддержке хранения для файловых акций см. в служба хранилища [в](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) документации по поддержке и SQL Server и размещении файлов журнала в документации развертывания.[](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) Дополнительные сведения о выровненном размещении общего файлового ресурса см. в разделе [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) в документации по поддержке. Сведения о разработке топологии для интерфейсного пула Enterprise Edition см. в разделе [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) документации по развертыванию.