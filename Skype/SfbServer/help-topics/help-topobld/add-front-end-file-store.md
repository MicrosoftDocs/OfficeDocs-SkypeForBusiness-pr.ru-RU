---
title: Добавление хранилища файлов переднего плана
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.
ms.openlocfilehash: 2427c5c90fb60d5a0ddef0ca428d336406e15c03
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739455"
---
# <a name="add-front-end-file-store"></a>Добавление хранилища файлов переднего плана

Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.

> [!IMPORTANT]
> Файл не может быть расположен на переднем выпуск Enterprise сервере, но может быть расположен на выпуск Standard сервере.

> [!IMPORTANT]
> Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии.

> [!IMPORTANT]
> При добавлении в топологию интерфейсного пула Enterprise или сервера Standard Edition построитель топологий должен иметь возможность настройки файлового хранилища и списков управления доступом на уровне пользователей (DACL) для общей папке файлов, которая будет использоваться для файлового хранилища. Для этого требуется войти в систему под учетной записью, имеющей права полного доступа (чтение, запись, изменение) к общей папке файлов при публикации новой топологии в построителей топологий.

Подробные сведения о поддержке хранения для файловых акций [см.](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) в служба хранилища в документации по поддержке и [SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) и размещении файлов журнала в документации развертывания. Дополнительные сведения о выровненном размещении общего файлового ресурса см. в разделе [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) в документации по поддержке. Сведения о разработке топологии для интерфейсного пула Enterprise Edition см. в разделе [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) документации по развертыванию.