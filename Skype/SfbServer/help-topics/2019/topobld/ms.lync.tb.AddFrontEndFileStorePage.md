---
title: Добавление хранилища файлов переднего плана
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
ROBOTS: NOINDEX, NOFOLLOW
description: Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.
ms.openlocfilehash: 7bfcf204a16468b1de7a24e1f6eee8c611bb2da8
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702954"
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="c5aa9-104">Добавление хранилища файлов переднего плана</span><span class="sxs-lookup"><span data-stu-id="c5aa9-104">Add Front End File Store</span></span>

<span data-ttu-id="c5aa9-p102">Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.</span><span class="sxs-lookup"><span data-stu-id="c5aa9-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5aa9-107">Общий файловый ресурс может быть расположен на сервере переднего плана только для Standard Edition (не для Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="c5aa9-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5aa9-108">Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="c5aa9-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c5aa9-p103">При добавлении в топологию интерфейсного пула Enterprise или сервера Standard Edition построитель топологий должен иметь возможность настройки файлового хранилища и списков управления доступом на уровне пользователей (DACL) для общей папке файлов, которая будет использоваться для файлового хранилища. Для этого требуется войти в систему под учетной записью, имеющей права полного доступа (чтение, запись, изменение) к общей папке файлов при публикации новой топологии в построителей топологий.</span><span class="sxs-lookup"><span data-stu-id="c5aa9-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="c5aa9-p104">О поддержке хранилища для общих файловых ресурсов см. в разделе [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) документации по поддержке и в разделе [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) документации по развертыванию. О совмещенном расположении общего файлового ресурса см. в разделе [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) документации по поддержке. О разработке топологии для пула переднего плана корпоративного выпуска см. в разделе [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="c5aa9-p104">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation. For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation. For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>


