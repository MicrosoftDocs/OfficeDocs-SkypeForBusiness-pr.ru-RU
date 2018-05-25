---
title: Добавление файлового хранилища Директора
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для директоров. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: b8873ed9a7fd4f66f60c4f1e8836c2d7a06b5f2e
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="add-director-file-store"></a><span data-ttu-id="2f1a0-104">Добавление файлового хранилища Директора</span><span class="sxs-lookup"><span data-stu-id="2f1a0-104">Add Director File Store</span></span>
 
<span data-ttu-id="2f1a0-p102">Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для директоров. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f1a0-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2f1a0-p103">При добавлении директоров в топологию для публикации топологии требуется доступ, позволяющий настроить хранилище файлов и сконфигурировать списки управления доступом на уровне пользователей (DACL) для общего файлового ресурса, который используется для хранилища файлов. При запуске построителя топологии и публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="2f1a0-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
<span data-ttu-id="2f1a0-109">Для получения дополнительных сведений о поддержке хранения для общих файлов видеть [Поддерживает хранение файлов](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) в документации по технической поддержке и [данных SQL Server и размещение файлов журнала](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2f1a0-109">For details about storage support for file shares, see [File Storage Support](http://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](http://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="2f1a0-110">Для получения дополнительных сведений о выровненное размещение общей папки, просмотрите [Поддерживаемые выровненное размещение серверов](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="2f1a0-110">For details about collocation of the file share, see [Supported Server Collocation](http://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="2f1a0-111">Для получения дополнительных сведений о разработке топологии для директоров просмотрите [Определение единственный директор в построителе топологий](http://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="2f1a0-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](http://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>
  

