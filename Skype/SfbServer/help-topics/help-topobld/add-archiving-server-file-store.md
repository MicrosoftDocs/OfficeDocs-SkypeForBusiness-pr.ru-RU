---
title: Добавление файлового хранилища сервера архивации
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Для архивации сеансов мгновенных сообщений и веб-конференций (собрания) необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища копий всего контента веб-конференций. В качестве хранилища файлов архива можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: bd904a746cad5765fafa42d8bff6ea0611311a32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119858"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="e15ee-104">Добавление файлового хранилища сервера архивации</span><span class="sxs-lookup"><span data-stu-id="e15ee-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="e15ee-p102">Для архивации сеансов мгновенных сообщений и веб-конференций (собрания) необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища копий всего контента веб-конференций. В качестве хранилища файлов архива можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="e15ee-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e15ee-107">Вы можете определить общий файловый ресурс в построителе топологий перед его созданием, однако вам следует поместить этот ресурс в расположение, заданное до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="e15ee-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="e15ee-108">> При добавлении серверов архива в топологию, topology Builder должен иметь возможность настроить хранилище файлов архива и настроить дискреционные списки управления доступом (DACLs) в файле, который будет использоваться для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="e15ee-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="e15ee-109">При запуске построителя топологии для публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="e15ee-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="e15ee-110">Подробные сведения о поддержке хранения [](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) для файловых акций см. в документации по поддержке хранения файлов и [SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) и размещении файлов журнала в документации развертывания.</span><span class="sxs-lookup"><span data-stu-id="e15ee-110">For details about storage support for file shares, see [File Storage Support](/previous-versions/office/lync-server-2013/lync-server-2013-file-storage-support) in the Supportability documentation and [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement) in the Deployment documentation.</span></span> <span data-ttu-id="e15ee-111">Дополнительные сведения о выровненном размещении общего файлового ресурса см. в разделе [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="e15ee-111">For details about collocation of the file share, see [Supported Server Collocation](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation) in the Supportability documentation.</span></span>