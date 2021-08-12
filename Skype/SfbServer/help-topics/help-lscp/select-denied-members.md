---
title: Выбор запрещенных участников
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.SelectDeniedMembers
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c626b6b4-15f3-4a59-bb1d-55dc8c60f5cb
description: Постоянный администратор чата может создавать и управлять категориями комнат чата. В рамках создания и управления категориями комнат чата администратор сохраняемого чата может настраивать директоров (группы/контейнеры/пользователи active Directory Domain Services), которые имеют доступ к членам или создателям комнат чатов определенной категории. Администратор сохраняемой беседы также может добавлять DeniedMembers в категорию, и они становятся явными исключениями в разрешенный список. DeniedMembers переопределяют то, что есть в AllowedMembers.
ms.openlocfilehash: 2e4927532e6991565095693d7c087bcdf5b826d47aaf3fa101e30cecced7664a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331571"
---
# <a name="select-denied-members"></a>Выбор запрещенных участников

Постоянный администратор чата может создавать и управлять категориями комнат чата. В рамках создания и управления категориями комнат чата администратор сохраняемого чата может настраивать директоров (группы/контейнеры/пользователи active Directory Domain Services), которые имеют доступ к членам или создателям комнат чатов определенной категории. Администратор сохраняемой беседы также может добавлять DeniedMembers в категорию, и они становятся явными исключениями в разрешенный список. DeniedMembers переопределяют то, что есть в AllowedMembers.

## <a name="tasks-that-you-can-perform"></a>Задачи, которые вы можете выполнить

На странице **Выберите запрещенных участников** можно выполнить следующие задачи:

- [Настройка категорий](/previous-versions/office/lync-server-2013/lync-server-2013-configure-categories)

- [Новые функции сервера сохраняемого чата](/previous-versions/office/lync-server-2013/lync-server-2013-new-persistent-chat-server-features)

Сведения о различных процедурах, которые можно выполнить с помощью панели управления Skype для бизнеса Server, см. в Skype для бизнеса Server [2015](../../manage/manage.md)г.

## <a name="to-configure-categories-for-chat-rooms"></a>Настройка категорий для комнат чата

В **разделе Членство**, в разделе **Отказано в членстве** добавьте или удалите пользователей и других директоров Active Directory, связанных с тем, что участникам отказано в доступе из комнаты.


Подробные сведения о возможностях и возможностях сохраняемого сервера чата см. в обзоре сохраняемого сервера [чата](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-persistent-chat-server) в документации по планированию. Подробные сведения о работе с настойчивыми конфигурациями сервера чата см. в материале Настройка стойких серверов чата в документации по развертыванию и управление [Lync Server 2013, Persistent Chat Server](/previous-versions/office/lync-server-2013/managing-lync-server-2013-persistent-chat-server) в документации по операциям. [](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-persistent-chat-server)

## <a name="see-also"></a>См. также

[Общие сведения о членстве в сохраняемом чате](/previous-versions/office/lync-server-2013/understanding-persistent-chat-membership)