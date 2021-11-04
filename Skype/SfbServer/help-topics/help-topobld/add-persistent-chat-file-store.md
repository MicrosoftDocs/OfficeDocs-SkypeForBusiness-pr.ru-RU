---
title: Добавление файлового хранилища сохраняемого чата
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
ms.openlocfilehash: d061ff6e3bd084fef4ebf80c84c5e14a127afa91
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747835"
---
# <a name="add-persistent-chat-file-store"></a>Добавление файлового хранилища сохраняемого чата
 
Необходимо указать общий файловый ресурс, который будет использоваться в качестве хранилища файлов для сервера Standard Edition или пула переднего плана Enterprise Edition. В качестве хранилища файлов можно использовать существующий общий файловый ресурс. Кроме того, можно добавить новый общий файловый ресурс, указав полное доменное имя файлового сервера, на котором расположен общий файловый ресурс, и имя папки для нового общего файлового ресурса.
  
> [!IMPORTANT]
> Доля файлов для Skype для бизнеса Server не может быть расположена на выпуск Enterprise сервере, но может быть расположена на выпуск Standard сервере. 
  
> [!IMPORTANT]
> Вы можете определить общую папку файлов в построителе топологий перед ее созданием, однако вам следует поместить эту папку в расположение, заданное до публикации топологии. 
  
> [!IMPORTANT]
> При добавлении в топологию пула сохраняемой системы чата или сохраняемой системы чат-серверов топологии строитель топологии должен иметь возможность настроить хранилище файлов и настроить дискреционные списки управления доступом (DACLs) в файлообмеще, который будет использоваться для хранения файлов. При запуске построителя топологии для публикации новой топологии необходимо войти в систему с использованием учетной записи с полными правами на управление (чтение/запись/изменение) для общего файлового ресурса. 
  
## <a name="see-also"></a>См. также

[Планирование на стойкий сервер чата в Skype для бизнеса Server 2015 г.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Добавление постоянного сервера чата в топологию Skype для бизнеса Server 2015 г.](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Требования к оборудованию и программному обеспечению для постоянного сервера чата в Skype для бизнеса Server 2015 г.](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Требования к серверу для Skype для бизнеса Server 2015 г.](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Основы топологии для Skype для бизнеса Server 2015 г.](../../plan-your-deployment/topology-basics/topology-basics.md)
