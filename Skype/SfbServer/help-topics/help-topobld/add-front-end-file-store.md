---
title: Добавление хранилища файлов переднего плана
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
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.
ms.openlocfilehash: 4fb23aa6d7e436fd089c6a1912c450304bf189c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119788"
---
# <a name="add-front-end-file-store"></a>Добавление хранилища файлов переднего плана

Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.

> [!IMPORTANT]
> Доля файлов не может быть расположена на переднем сервере корпоративного выпуска, но может быть расположена на сервере Standard Edition.

> [!IMPORTANT]
> Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии.

> [!IMPORTANT]
> При добавлении в топологию интерфейсного пула Enterprise или сервера Standard Edition построитель топологий должен иметь возможность настройки файлового хранилища и списков управления доступом на уровне пользователей (DACL) для общей папке файлов, которая будет использоваться для файлового хранилища. Для этого требуется войти в систему под учетной записью, имеющей права полного доступа (чтение, запись, изменение) к общей папке файлов при публикации новой топологии в построителей топологий.

Подробные сведения о поддержке хранения [](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) для файловых акций см. в документации по поддержке хранения файлов и [SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) и размещении файлов журнала в документации развертывания. Дополнительные сведения о выровненном размещении общего файлового ресурса см. в разделе [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) в документации по поддержке. Сведения о разработке топологии для интерфейсного пула Enterprise Edition см. в разделе [Define and Configure a Front End Pool](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server) документации по развертыванию.