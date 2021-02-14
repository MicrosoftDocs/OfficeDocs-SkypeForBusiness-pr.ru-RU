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
# <a name="verify-configuration-settings"></a>Проверка параметров настройки

Проверить репликацию сведений о конфигурации на edge-сервер можно с помощью команды Skype для бизнеса Server 2019 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором расположено центральное хранилище управления, или на любом компьютере, который присоединяется к домену, на котором установлены основные компоненты Skype для бизнеса Server 2019 (OcsCore.msi). 
  
В начальных результатах для репликации может быть указано состояние "False" вместо "True". В этом случае запустите командлет **Invoke-CsManagementStoreReplication** и дайте некоторое время для завершения репликации, прежде чем повторно запускать командлет **Get-CsManagementStoreReplicationStatus**. 
  

