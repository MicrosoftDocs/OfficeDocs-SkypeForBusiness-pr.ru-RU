---
title: Проверка параметров конфигурации
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно проверить, запустив Скайп для командлета Business Server 2019 Get-CsManagementStoreReplicationStatus на внутренний компьютере, на котором расположен центрального хранилища управления, или на любом репликации сведений о конфигурации на пограничный сервер компьютер, на котором установлена Скайп для Business Server 2019 основные компоненты (OcsCore.msi), присоединенный к домену.
ms.openlocfilehash: 23a5b4c3af8ac02ebfd620d3bbc46ddcba5bea11
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027811"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="4c0d5-103">Проверка параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="4c0d5-103">Verify configuration settings</span></span>

<span data-ttu-id="4c0d5-104">Можно проверить репликации сведений о конфигурации на пограничный сервер, выполнив Скайп для командлета Business Server 2019 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором размещается центральное хранилище управления, или на любой компьютер, присоединенный к домену, на котором установлен Скайп для Business Server 2019 основные компоненты (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="4c0d5-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="4c0d5-105">Начальное результатов может указывать состояние как «False» вместо «True» для репликации.</span><span class="sxs-lookup"><span data-stu-id="4c0d5-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="4c0d5-106">Если это так, используйте командлет **Invoke-CsManagementStoreReplication** и дождитесь окончания репликации для выполнения перед запуском **Get-CsManagementStoreReplicationStatus** еще раз.</span><span class="sxs-lookup"><span data-stu-id="4c0d5-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

