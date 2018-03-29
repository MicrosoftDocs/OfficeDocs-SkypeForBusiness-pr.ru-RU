---
title: Добавьте полное доменное имя пула доверенных приложений
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: Чтобы определить полное доменное имя пула доверенных приложений (FQDN), укажите следующие параметры.
ms.openlocfilehash: af21ab09797a5b81f2071a37a2668d556f0a4012
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="add-trusted-application-pool-fqdn"></a>Добавьте полное доменное имя пула доверенных приложений
 
Чтобы определить полное доменное имя пула доверенных приложений (FQDN), укажите следующие параметры.
  
Полное доменное имя сервера или пула серверов, где размещены доверенные приложения.
  
Выберите **пул на нескольких компьютерах** , если выполняется развертывание пула серверов для доверенных приложений балансировки нагрузки и обеспечения высокой доступности, или выберите **пул из одного компьютера** , если не требуется загружать Балансировка и высокой доступности.
  
> [!IMPORTANT]
> Один сервер доверенных приложений невозможно преобразовать в пуле серверов более поздней версии. Если вы думаете, что пул может потребоваться в будущем, можно развернуть несколько пула серверов, содержащий один компьютер теперь и добавьте серверы при необходимости. 
  
Для получения дополнительных сведений о пулы доверенных приложений видеть [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).
  

