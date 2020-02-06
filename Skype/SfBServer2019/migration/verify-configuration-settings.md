---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы можете проверить репликацию сведений о конфигурации на пограничном сервере, запустив командлет Skype для Business Server 2019 Get-Ксманажементсторерепликатионстатус на внутреннем компьютере, на котором находится хранилище Центрального управления, или на любом компьютер, подключенный к домену, на котором установлен компонент «основные компоненты» для Skype для Business Server 2019 (Окскоре. msi).
ms.openlocfilehash: 141bb640193834316ca65f9a42db611010896034
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812757"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="107ea-103">Проверка параметров настройки</span><span class="sxs-lookup"><span data-stu-id="107ea-103">Verify configuration settings</span></span>

<span data-ttu-id="107ea-104">Вы можете проверить репликацию сведений о конфигурации на пограничном сервере, запустив командлет Skype для Business Server 2019 **Get-ксманажементсторерепликатионстатус** на внутреннем компьютере, на котором находится корневой центр управления, или на любом компьютере, подключенном к домену, на котором установлен компонент "основные компоненты" Skype для Business Server 2019 (окскоре. msi).</span><span class="sxs-lookup"><span data-stu-id="107ea-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="107ea-105">Начальные результаты могут содержать состояние "false", а не "истина" для репликации.</span><span class="sxs-lookup"><span data-stu-id="107ea-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="107ea-106">Если это так, запустите командлет **Invoke-ксманажементсторерепликатион** и разрешите время завершения репликации, прежде чем запускать командлет **Get-ксманажементсторерепликатионстатус** еще раз.</span><span class="sxs-lookup"><span data-stu-id="107ea-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

