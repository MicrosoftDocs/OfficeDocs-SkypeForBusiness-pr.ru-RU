---
title: Добавление файлового хранилища сохраняемого чата
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: 76b116d469bf6369174815d6b396a64149518f17
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="add-persistent-chat-file-store"></a>Добавление файлового хранилища сохраняемого чата
 
Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
  
> [!IMPORTANT]
> Файловый ресурс для Скайп для Business Server не может быть расположена на сервере переднего плана Enterprise Edition, но может быть найдена на сервере Standard Edition. 
  
> [!IMPORTANT]
> Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии. 
  
> [!IMPORTANT]
> При добавлении серверов сохраняемого чата или серверов сохраняемого чата пула в топологию, Topology Builder должны иметь возможность создать файл хранения и настройка управления доступом список (доступом) в общей папке, которое будет использоваться для хранения файла. При запуске построителя топологии для публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса. 
  
## <a name="see-also"></a>См. также

#### 

[Планирование для сервера сохраняемого чата в Скайп Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Аппаратные и программные требования для сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Требования к серверу для Скайп для Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Основные сведения о топологии для Скайп для Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)

