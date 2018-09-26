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
# <a name="verify-configuration-settings"></a>Проверка параметров конфигурации

Можно проверить репликации сведений о конфигурации на пограничный сервер, выполнив Скайп для командлета Business Server 2019 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором размещается центральное хранилище управления, или на любой компьютер, присоединенный к домену, на котором установлен Скайп для Business Server 2019 основные компоненты (OcsCore.msi). 
  
Начальное результатов может указывать состояние как «False» вместо «True» для репликации. Если это так, используйте командлет **Invoke-CsManagementStoreReplication** и дождитесь окончания репликации для выполнения перед запуском **Get-CsManagementStoreReplicationStatus** еще раз. 
  

