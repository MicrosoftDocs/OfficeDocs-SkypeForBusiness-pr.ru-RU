---
title: Вызов установки локального хранилища конфигурации (настройка)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Чтобы приступить к установке базы данных, в которой будет храниться локальная копия центрального хранилища, предназначенная только для чтения, выбери определенную конфигурацию, опубликованную с помощью построителя топологии из уже установленного и настроенного централизованного центра администрирования. Управление хранилищем или чтение определенных конфигураций из других носителей. Для компьютера, который находится в внутренней сети организации, выберите пункт загрузить конфигурацию автоматически из хранилища центрального управления.
ms.openlocfilehash: 7638ab56e2ddcc8951ae989de11e72e0817a20bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823643"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="eb1fa-104">Вызов установки локального хранилища конфигурации (настройка)</span><span class="sxs-lookup"><span data-stu-id="eb1fa-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="eb1fa-105">Чтобы приступить к установке базы данных, в которой будет храниться локальная копия центрального хранилища, предназначенная только для чтения, выбери определенную конфигурацию, опубликованную с помощью построителя топологии из уже установленного и настроенного централизованного центра администрирования. Управление хранилищем или чтение определенных конфигураций из других носителей.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="eb1fa-106">Для компьютера, который находится в внутренней сети организации, выберите пункт **загрузить конфигурацию автоматически из хранилища центрального управления**.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="eb1fa-107">Если вы устанавливаете реплику центрального хранилища на пограничном сервере, вы выбираете прочитать экспортированную копию документа конфигурации с переносного носителя, например USB-устройства флэш-памяти, жесткого диска USB или другого носителя.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="eb1fa-108">Если вы устанавливаете локальное хранилище конфигураций на пограничном сервере, сведения о конфигурации должны быть в формате, который был экспортирован из хранилища для централизованного управления с помощью командлета Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="eb1fa-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="eb1fa-109">После выбора нужного параметра нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="eb1fa-109">After you have selected the appropriate option, click **Next**.</span></span>
  

