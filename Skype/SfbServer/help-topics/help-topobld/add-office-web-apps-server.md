---
title: Добавление сервера Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: Мастер определения нового сервера Office Web Apps определяет новый сервер Office Web Apps в развертывании. Следует указать следующие сведения.
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218730"
---
# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps

Мастер **определения нового сервера Office Web Apps** определяет новый сервер Office Web Apps в развертывании. Следует указать следующие сведения.

 ПОЛНОЕ доменное имя **сервера Office Web Apps**: введите полное доменное имя сервера, на котором будет размещаться сервер Office Web Apps.

 **URL-адрес обнаружения сервера Office Web Apps**: введите полный URL-адрес сервера Office Web Apps (URL-адрес)

> [!TIP]
> По умолчанию URL- **адрес обнаружения сервера Office Web Apps** используется для создания URL-адреса на основе полного доменного имени сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . В большинстве случаев нет необходимости изменять формат по умолчанию. Возможно, потребуется изменить формат по умолчанию в случае, если сервер Office Web Apps и URL-адрес обнаружения сервера Office Web Apps должны различаться. Например, сервер Office Web Apps размещается в сети периметра и будет иметь другой URL-адрес на основе расположения.

 **Сервер Office Web Apps развернут во внешней сети (периметр/Интернет)**: Установите этот флажок, если сервер Office Web Apps размещен за пределами внутреннего брандмауэра, такого как демилитаризованная зона, внешняя сеть или другая зона сети, не совпадающую с внутренней сетью.

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
