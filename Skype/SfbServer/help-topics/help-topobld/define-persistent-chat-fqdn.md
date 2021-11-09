---
title: Определение полного доменного имени сохраняемого чата
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFqdnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e0123fa6-008b-430e-a68b-61f0cc3fb12e
description: Вы создаете новый постоянный чат-сервер или пул постоянных чат-серверов с помощью мастера Define New Persistent Chat Pool. Выберите Пул из нескольких компьютеров или Пул из одного компьютера. Если вы выберете один пул компьютеров, а затем потребуется несколько пулов компьютеров, вам потребуется удалить пул одного компьютера, а затем определить несколько пулов компьютеров.
ms.openlocfilehash: 44d8fd7647068c98855a2d06f64a2d8f519f2da5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851323"
---
# <a name="define-persistent-chat-fqdn"></a>Определение полного доменного имени сохраняемого чата
 
Вы создаете новый постоянный чат-сервер или пул постоянных чат-серверов с помощью мастера **Define New Persistent Chat Pool.** Выберите **Пул из нескольких компьютеров** или **Пул из одного компьютера**. Если вы выберете один пул компьютеров, а затем потребуется несколько пулов компьютеров, вам потребуется удалить пул одного компьютера, а затем определить несколько пулов компьютеров.
  
Кроме того, необходимо определить **FQDN** пула для сохраняемой сервера чата или пула постоянных серверов чата. Полное доменное имя для пула из одного компьютера должно совпадать с полным доменным именем компьютера, включенного в этот пул. Для пула из нескольких компьютеров в качестве полного доменного имени должно использоваться имя, выбранное для представления этого пула и определенное в записи хоста A (и AAAA при использовании IPv6-адреса) DNS.
  
## <a name="see-also"></a>См. также

[Планирование на стойкий сервер чата в Skype для бизнеса Server 2015 г.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление постоянного сервера чата в топологию Skype для бизнеса Server 2015 г.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
