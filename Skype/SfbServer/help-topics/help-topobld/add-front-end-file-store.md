---
title: Добавление хранилища файлов переднего плана
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d18a648-a0e1-4401-a1e6-7a2755ba8c66
description: Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.
ms.openlocfilehash: a7ba229b22715880a496f811344f44fd18740650
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-file-store"></a><span data-ttu-id="53ddb-104">Добавление хранилища файлов переднего плана</span><span class="sxs-lookup"><span data-stu-id="53ddb-104">Add Front End File Store</span></span>
 
<span data-ttu-id="53ddb-p102">Необходимо указать общую папку файлов, которая будет использоваться как файловое хранилище для сервера Standard Edition или интерфейсного пула Enterprise Edition. Можно использовать существующую общую папку файлов для файлового хранилища или определить новую общую папку файлов, указав полное доменное имя файлового сервера, на котором будет располагаться общая папка файлов, и имя этой папки.</span><span class="sxs-lookup"><span data-stu-id="53ddb-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53ddb-107">Общий файловый ресурс может быть расположен на сервере переднего плана только для Standard Edition (не для Enterprise Edition).</span><span class="sxs-lookup"><span data-stu-id="53ddb-107">The file share cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="53ddb-108">Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="53ddb-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="53ddb-p103">При добавлении в топологию интерфейсного пула Enterprise или сервера Standard Edition построитель топологий должен иметь возможность настройки файлового хранилища и списков управления доступом на уровне пользователей (DACL) для общей папке файлов, которая будет использоваться для файлового хранилища. Для этого требуется войти в систему под учетной записью, имеющей права полного доступа (чтение, запись, изменение) к общей папке файлов при публикации новой топологии в построителей топологий.</span><span class="sxs-lookup"><span data-stu-id="53ddb-p103">When you add an Enterprise Front End pool or Standard Edition server to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
<span data-ttu-id="53ddb-111">Для получения дополнительных сведений о поддержке хранения для общих файлов видеть [Поддерживает хранение файлов](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) в документации по технической поддержке и [данных SQL Server и размещение файлов журнала](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="53ddb-111">For details about storage support for file shares, see [File Storage Support](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="53ddb-112">Для получения дополнительных сведений о выровненное размещение общей папки, просмотрите [Поддерживаемые выровненное размещение серверов](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="53ddb-112">For details about collocation of the file share, see [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="53ddb-113">Для получения дополнительных сведений о разработке топологии для пула переднего плана Enterprise Edition содержатся в документации по развертыванию [Определение и настройка пула переднего плана](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) .</span><span class="sxs-lookup"><span data-stu-id="53ddb-113">For details about designing the topology for an Enterprise Edition Front End pool, see [Define and Configure a Front End Pool](http://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx) in the Deployment documentation.</span></span>
  

