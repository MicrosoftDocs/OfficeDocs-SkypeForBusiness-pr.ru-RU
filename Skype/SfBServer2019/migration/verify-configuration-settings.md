---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно проверить, запустив Скайп для командлета Business Server 2019 Get-CsManagementStoreReplicationStatus на внутренний компьютере, на котором расположен центрального хранилища управления, или на любом репликации сведений о конфигурации на пограничный сервер компьютер, на котором установлена Скайп для Business Server 2019 основные компоненты (OcsCore.msi), присоединенный к домену.
ms.openlocfilehash: 1b64569ffbdce3d7f41e7f6c54815d051848cfd1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889678"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="f6899-103">Проверка параметров настройки</span><span class="sxs-lookup"><span data-stu-id="f6899-103">Verify configuration settings</span></span>

<span data-ttu-id="f6899-104">Можно проверить репликации сведений о конфигурации на пограничный сервер, выполнив Скайп для командлета Business Server 2019 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором размещается центральное хранилище управления, или на любой компьютер, присоединенный к домену, на котором установлен Скайп для Business Server 2019 основные компоненты (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="f6899-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="f6899-105">Начальное результатов может указывать состояние как «False» вместо «True» для репликации.</span><span class="sxs-lookup"><span data-stu-id="f6899-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="f6899-106">Если это так, используйте командлет **Invoke-CsManagementStoreReplication** и дождитесь окончания репликации для выполнения перед запуском **Get-CsManagementStoreReplicationStatus** еще раз.</span><span class="sxs-lookup"><span data-stu-id="f6899-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

