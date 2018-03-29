---
title: Вызов установки локального хранилища конфигурации (Настройка)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Чтобы начать установку базы данных, который будет использоваться для хранения локальной копии только для чтения из центрального хранилища управления, выберите между получение определенных конфигурации публикации с помощью построителя топологий с уже установлена и настроена Central Хранилище управления или чтение определенные конфигурации с другими носителя. Для компьютера, который размещается на внутренней сети вашей организации выберите получить автоматически из центрального хранилища управления.
ms.openlocfilehash: 74269ee40116b91097c77702942f42de9f7d882a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="99f01-104">Вызов установки локального хранилища конфигурации (Настройка)</span><span class="sxs-lookup"><span data-stu-id="99f01-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="99f01-105">Чтобы начать установку базы данных, который будет использоваться для хранения локальной копии только для чтения из центрального хранилища управления, выберите между получение определенных конфигурации публикации с помощью построителя топологий с уже установлена и настроена Central Хранилище управления или чтение определенные конфигурации с другими носителя.</span><span class="sxs-lookup"><span data-stu-id="99f01-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="99f01-106">Для компьютера, который размещается на внутренней сети вашей организации выберите **получить непосредственно из центрального хранилища управления**.</span><span class="sxs-lookup"><span data-stu-id="99f01-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="99f01-107">При установке реплики хранилища централизованного управления на пограничном сервере, установите для чтения экспортированного копию документа конфигурации из съемный носитель, например флэш-накопитель USB, жесткий диск USB, компакт-диск или другой носитель.</span><span class="sxs-lookup"><span data-stu-id="99f01-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="99f01-108">Установка локального хранилища конфигурации пограничного сервера, сведения о конфигурации должен быть в формате, который был экспортирован из центра управления хранения с помощью командлета Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="99f01-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="99f01-109">Выбрав соответствующий параметр, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="99f01-109">After you have selected the appropriate option, click **Next**.</span></span>
  

