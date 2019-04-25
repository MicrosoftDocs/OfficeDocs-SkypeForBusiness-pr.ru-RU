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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231359"
---
# <a name="verify-configuration-settings"></a>Проверка параметров настройки

Можно проверить репликации сведений о конфигурации на пограничный сервер, выполнив Скайп для командлета Business Server 2019 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором размещается центральное хранилище управления, или на любой компьютер, присоединенный к домену, на котором установлен Скайп для Business Server 2019 основные компоненты (OcsCore.msi). 
  
Начальное результатов может указывать состояние как «False» вместо «True» для репликации. Если это так, используйте командлет **Invoke-CsManagementStoreReplication** и дождитесь окончания репликации для выполнения перед запуском **Get-CsManagementStoreReplicationStatus** еще раз. 
  

