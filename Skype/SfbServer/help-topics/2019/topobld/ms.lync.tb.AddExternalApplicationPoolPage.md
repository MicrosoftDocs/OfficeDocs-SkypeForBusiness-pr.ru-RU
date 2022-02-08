---
title: Добавление полного доменного имени надежного пула приложений
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: Чтобы определить полное доменное имя пула доверенных приложений, укажите следующие параметры.
ms.openlocfilehash: f0420271b2ae0b2cea5134ca9ea2ace7014168b9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389531"
---
# <a name="add-trusted-application-pool-fqdn"></a>Добавление полного доменного имени пула доверенных приложений
 
Чтобы определить полное доменное имя пула доверенных приложений, укажите следующие параметры.
  
Полное доменное имя сервера или пула серверов, где размещены доверенные приложения.
  
Выберите параметр **Пул с несколькими компьютерами** при развертывании пула серверов для доверенных приложений с поддержкой балансировки нагрузки и высокой доступности или выберите **Отдельный пул компьютеров**, если нет необходимости в балансировки нагрузки или высокой доступности.
  
> [!IMPORTANT]
> Отдельный сервер доверенных приложений не может быть преобразован в пул серверов. Если в будущем может понадобиться пул, можно развернуть на данном этапе пул серверов, состоящий только из одного сервера, а впоследствии добавить в него серверы. 
  
Дополнительные сведения о пуле доверенных приложений см. в разделе [New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
