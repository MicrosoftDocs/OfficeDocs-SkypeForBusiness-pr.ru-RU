---
title: Добавление файлового хранилища Директора
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
- ms.lync.tb.AddDirectorFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a15b69e0-d3d1-4648-af25-1c0f25e5da8e
description: Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для директоров. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: 2c7ad609ea3e58f0368f8c1e3d8716223aa68700
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824289"
---
# <a name="add-director-file-store"></a><span data-ttu-id="49138-104">Добавление файлового хранилища директора</span><span class="sxs-lookup"><span data-stu-id="49138-104">Add Director File Store</span></span>

<span data-ttu-id="49138-p102">Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для директоров. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="49138-p102">You must specify a file share to be used as the file store for Directors. You can use an existing file share for the file store, or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49138-p103">При добавлении директоров в топологию для публикации топологии требуется доступ, позволяющий настроить хранилище файлов и сконфигурировать списки управления доступом на уровне пользователей (DACL) для общего файлового ресурса, который используется для хранилища файлов. При запуске построителя топологии и публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса.</span><span class="sxs-lookup"><span data-stu-id="49138-p103">When you add Directors to a topology, topology publication requires appropriate access to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store. This requires that, when you run Topology Builder and publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span>

<span data-ttu-id="49138-109">Подробные сведения о поддержке хранилища [](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) для файловых файловых файлов см. в документации по поддержке хранилища SQL Server [и](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) размещении данных и файлов журнала в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="49138-109">For details about storage support for file shares, see [File Storage Support](https://technet.microsoft.com/library/ed66430d-3c19-4267-938c-956a51005073.aspx) in the Supportability documentation and [SQL Server Data and Log File Placement](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx) in the Deployment documentation.</span></span> <span data-ttu-id="49138-110">Дополнительные сведения о выровненном размещении общего файлового ресурса см. в разделе [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="49138-110">For details about collocation of the file share, see [Supported Server Collocation](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="49138-111">Дополнительные сведения о разработке топологии для директоров см. в разделе [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="49138-111">For details about designing the topology for Directors, see [Define a Single Director in Topology Builder](https://technet.microsoft.com/library/8e9a659d-23b0-401d-b296-59c7df414d49.aspx) in the Deployment documentation.</span></span>


