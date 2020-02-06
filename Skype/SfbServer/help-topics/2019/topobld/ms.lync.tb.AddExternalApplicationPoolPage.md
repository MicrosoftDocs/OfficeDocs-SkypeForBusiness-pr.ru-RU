---
title: Добавление полного доменного имени надежного пула приложений
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Чтобы определить полное доменное имя для пула приложений, укажите следующее:'
ms.openlocfilehash: 52b0e10246c9c54ed5c38a44816992d2dc17e1ef
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41787739"
---
# <a name="add-trusted-application-pool-fqdn"></a>Добавление полного доменного имени надежного пула приложений
 
Чтобы определить полное доменное имя для пула приложений, укажите следующее:
  
Полное доменное имя сервера или пула серверов, на которых будут размещены доверенные приложения.
  
Если вы разворачиваете пул серверов для доверенных приложений из балансировки нагрузки и высокой доступности, выберите один пул **компьютеров** , а если балансировка нагрузки или высокий уровень доступности не требуется, выберите **отдельный пул компьютеров** .
  
> [!IMPORTANT]
> Один сервер Trusted Applications не может быть преобразован в пул серверов позже. Если вы считаете, что в будущем вам может понадобиться пул, вы можете развернуть многосерверный пул с одним компьютером сейчас и при необходимости добавить серверы. 
  
Подробные сведения о пулах Trusted Applications [кструстедаппликатионпул](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)можно найти в статьях создать.
  

