---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы можете проверить репликацию сведений о конфигурации на пограничном сервере, запустив командлет Skype для Business Server 2019 Get-Ксманажементсторерепликатионстатус на внутреннем компьютере, на котором находится хранилище Центрального управления, или на любом компьютер, подключенный к домену, на котором установлен компонент «основные компоненты» для Skype для Business Server 2019 (Окскоре. msi).
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307037"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="35711-103">Проверка параметров настройки</span><span class="sxs-lookup"><span data-stu-id="35711-103">Verify configuration settings</span></span>

<span data-ttu-id="35711-104">Вы можете проверить репликацию сведений о конфигурации на пограничном сервере, запустив командлет Skype для Business Server 2019 **Get-ксманажементсторерепликатионстатус** на внутреннем компьютере, на котором находится хранилище центра управления, или на любом компьютере, подключенном к домену, на котором установлен компонент "основные компоненты" Skype для Business Server 2019 (Окскоре. msi).</span><span class="sxs-lookup"><span data-stu-id="35711-104">You can validate the replication of configuration information to the Edge server by running the Skype for Business Server 2019 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain-joined computer on which Skype for Business Server 2019 Core Components (OcsCore.msi) is installed.</span></span> 
  
<span data-ttu-id="35711-105">Начальные результаты могут содержать состояние "false", а не "истина" для репликации.</span><span class="sxs-lookup"><span data-stu-id="35711-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="35711-106">Если это так, запустите командлет **Invoke-ксманажементсторерепликатион** и разрешите время завершения репликации, прежде чем запускать командлет **Get-ксманажементсторерепликатионстатус** еще раз.</span><span class="sxs-lookup"><span data-stu-id="35711-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span> 
  

