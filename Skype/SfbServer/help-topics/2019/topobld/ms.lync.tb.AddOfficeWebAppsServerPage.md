---
title: Добавление сервера Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: Мастер определения нового сервера Office Web Apps определяет новый сервер Office Web Apps в развертывании. Следует указать следующие сведения.
ms.openlocfilehash: dc82ea7b6b846940ab1975d93b70fbcb4dd9e983
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807729"
---
# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps

Мастер **определения нового сервера Office Web Apps** определяет новый сервер Office Web Apps в развертывании. Следует указать следующие сведения.

 **Полное доменное имя** сервера Office Web Apps: введите полное доменное имя сервера, на который будет работать сервер Office Web Apps

 **URL-адрес обнаружения Сервера Office Web Apps:** введите полный URL-адрес сервера Office Web Apps

> [!TIP]
> По умолчанию URL-адрес обнаружения **Сервера Office Web Apps** создается на основе FQDN сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . В большинстве случаев нет необходимости изменять формат по умолчанию. Вам может потребоваться изменить формат по умолчанию, если сервер Office Web Apps и URL-адрес обнаружения Сервера Office Web Apps должны быть другими. Например, сервер Office Web Apps помещается в сеть периметра и будет иметь другой URL-адрес в зависимости от расположения.

 **Сервер Office Web Apps** развертывается во внешней сети (то есть в периметре или Интернете). Если сервер Office Web Apps расположен за пределами внутреннего брандмауэра, например сети периметра, внешней сети или другой зоны сети, которая не является той же, что и внутренняя сеть.

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
