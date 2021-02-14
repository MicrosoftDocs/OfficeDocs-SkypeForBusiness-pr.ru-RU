---
title: Вызов установки локального хранилища конфигурации (настройка)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы начать установку базы данных, в которой будет храниться доступная только для чтения копия центрального банка управления, необходимо выбрать между искомой конфигурацией, опубликованной с помощью построщика топологий, из уже установленного и настроенного центрального банка управления или чтением определенной конфигурации с другого носитель. На компьютере, который находится во внутренней сети организации, выберите "Получить конфигурацию" автоматически из центрального банка управления.
ms.openlocfilehash: f8f9aeaccb510de4efec0020a8993d56851d0544
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801549"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="3f491-104">Вызов установки локального хранилища конфигурации (настройка)</span><span class="sxs-lookup"><span data-stu-id="3f491-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="3f491-105">Чтобы начать установку базы данных, в которой будет храниться доступная только для чтения копия центрального банка управления, необходимо выбрать между искомой конфигурацией, опубликованной с помощью построщика топологий, из уже установленного и настроенного центрального банка управления или чтением определенной конфигурации с другого носитель.</span><span class="sxs-lookup"><span data-stu-id="3f491-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="3f491-106">На компьютере, который находится во внутренней сети организации, выберите "Получить конфигурацию" автоматически **из центрального** банка управления.</span><span class="sxs-lookup"><span data-stu-id="3f491-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="3f491-107">Если реплика центрального хранилища управления устанавливается на пограничный сервер, выберите чтение экспортированной копии документа конфигурации с переносного носителя, такого как флэш-накопитель USB, жесткий диск USB, компакт-диск или другой носитель.</span><span class="sxs-lookup"><span data-stu-id="3f491-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="3f491-108">При установке локального хранения конфигурации на edge Server сведения о конфигурации должны быть в формате, экспортируемом из центрального банка управления с помощью Windows PowerShell данных:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="3f491-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="3f491-109">Выбрав подходящий параметр, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="3f491-109">After you have selected the appropriate option, click **Next**.</span></span>
  

