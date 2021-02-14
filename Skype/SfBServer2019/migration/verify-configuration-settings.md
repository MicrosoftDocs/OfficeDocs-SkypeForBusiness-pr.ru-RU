---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Проверить репликацию сведений о конфигурации на edge-сервер можно с помощью команды Skype для бизнеса Server 2019 Get-CsManagementStoreReplicationStatus на внутреннем компьютере, на котором расположено центральное хранилище управления, или на любом компьютере, который присоединился к домену, на котором установлены основные компоненты Skype для бизнеса Server 2019 (OcsCore.msi).
ms.openlocfilehash: dd270bd54bb427cf3fc74fe0081ef2e383a58589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752151"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="f843e-103">Проверка параметров настройки</span><span class="sxs-lookup"><span data-stu-id="f843e-103">Verify configuration settings</span></span>

<span data-ttu-id="f843e-104">Проверить репликацию сведений о конфигурации на edge-сервер можно с помощью команды Skype для бизнеса Server 2019 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором расположено центральное хранилище управления, или на любом компьютере, который присоединяется к домену, на котором установлены основные компоненты Skype для бизнеса Server 2019 (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="f843e-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="f843e-105">В начальных результатах для репликации может быть указано состояние "False" вместо "True".</span><span class="sxs-lookup"><span data-stu-id="f843e-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="f843e-106">В этом случае запустите командлет **Invoke-CsManagementStoreReplication** и дайте некоторое время для завершения репликации, прежде чем повторно запускать командлет **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="f843e-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

