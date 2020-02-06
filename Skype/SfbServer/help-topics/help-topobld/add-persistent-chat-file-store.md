---
title: Добавление файлового хранилища сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: f11443f8c10db35d5ffb8bfdbfc03d9826700b7c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820681"
---
# <a name="add-persistent-chat-file-store"></a>Добавление файлового хранилища сохраняемого чата
 
Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
  
> [!IMPORTANT]
> Общий доступ к файлам в Skype для бизнеса Server не может располагаться на сервере переднего плана Enterprise Edition, но его можно найти на сервере Standard Edition. 
  
> [!IMPORTANT]
> Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии. 
  
> [!IMPORTANT]
> При добавлении в топологию сервера сохраняемого или сохраняемого пула серверов чата приложение Topology Builder должно иметь возможность настроить хранилище файлов и настроить избирательные списки управления доступом (DACL) в общей папке, которые будут использоваться для хранения файлов. При запуске построителя топологии для публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса. 
  
## <a name="see-also"></a>См. также

[Планирование для сервера сохраняемого чата в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление постоянного сервера чата в топологию 2015 в Skype для бизнеса Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Требования к оборудованию и программному обеспечению для сервера сохраняемого чата в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Основы топологии для Skype для бизнеса Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
