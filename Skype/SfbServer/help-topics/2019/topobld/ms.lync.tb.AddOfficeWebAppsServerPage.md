---
title: Добавление сервера Office Web Apps
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'Мастер определения нового сервера Office Web Apps определяется новый сервер Office Web Apps в вашем развертывании. Заполните следующие сведения:'
ms.openlocfilehash: df8f2ba98215a597e9532e636b022edf9cb1ec19
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps
 
Мастер **Определения нового сервера Office Web Apps** определяется новый сервер Office Web Apps в вашем развертывании. Заполните следующие сведения:
  
 **Office Web Apps Server полное доменное имя**: Введите полное доменное имя сервера, на котором будет размещен сервер Office Web Apps
  
 **URL-адрес обнаружения сервера Office Web Apps**: Введите полный URL-адреса сервера Office Web Apps
  
> [!TIP]
> — Это поведение по умолчанию **URL-адрес обнаружения сервера Office Web Apps** для создания URL-адрес, основан на полное доменное имя сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . В большинстве случаев не нужно изменить формат по умолчанию. Может потребоваться изменить формат по умолчанию, в случае, если сервер Office Web Apps и URL-адрес обнаружения сервера Office Web Apps должны быть разными. К примеру сервера Office Web Apps размещается в демилитаризованной зоне и будет иметь другой URL-адрес на основе местоположения.
  
 **Сервер Office Web Apps развернут во внешней сети (то есть в периметре/Интернете)**: установите флажок, если сервер Office Web Apps размещен за пределами внутреннего брандмауэра, например, в сети периметра, внешней сети или другие зоны сети Это не совпадает с вашей внутренней сети.
  
## <a name="see-also"></a>См. также

#### 

[Компоненты и топологии для конференц-связи](http://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)

