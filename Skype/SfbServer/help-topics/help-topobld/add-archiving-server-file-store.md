---
title: Добавление файлового хранилища сервера архивации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddArchivingServerFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e95f938e-4dd2-48b8-95a3-05b4c63d4810
description: Для архивации сеансов мгновенных сообщений и веб-конференций (собрания) необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища копий всего контента веб-конференций. В качестве хранилища файлов архива можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: 99527455af38211ab788676b1072069924da9935
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304928"
---
# <a name="add-archiving-server-file-store"></a><span data-ttu-id="f1b53-104">Добавление файлового хранилища сервера архивации</span><span class="sxs-lookup"><span data-stu-id="f1b53-104">Add Archiving Server File Store</span></span>

<span data-ttu-id="f1b53-p102">Для архивации сеансов мгновенных сообщений и веб-конференций (собрания) необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища копий всего контента веб-конференций. В качестве хранилища файлов архива можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="f1b53-p102">To enable the archiving of both instant messaging (IM) and web conferencing (meeting) content, you must specify a file share to be used as the file store for copies of all web conferencing content. You can use an existing file share for the archiving file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1b53-107">Вы можете определить общий файловый ресурс в построителе топологий перед его созданием, однако вам следует поместить этот ресурс в расположение, заданное до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="f1b53-107">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location before you publish the topology.</span></span> <span data-ttu-id="f1b53-108">_Гт_. при добавлении сервера архивации в топологию построитель топологии должен иметь возможность настроить хранилище файлов для архивации и настроить избирательные списки управления доступом (DACL) для файлов, которые будут использоваться для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="f1b53-108">> When you add an Archiving Server to your topology, Topology Builder must be able to set up the Archiving file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="f1b53-109">При запуске построителя топологии для публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="f1b53-109">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="f1b53-p104">О поддержке хранилища для общих файловых ресурсов см. в разделе [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) документации по поддержке и в разделе [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) документации по развертыванию. О выровненном размещении общего файлового ресурса см. в разделе [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="f1b53-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span>


