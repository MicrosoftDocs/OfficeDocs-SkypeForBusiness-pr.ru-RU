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
description: Мастер Define New Office Web Apps Server определяет новый сервер Office Web Apps Server в развертывании. Следует указать следующие сведения.
ms.openlocfilehash: 84ebc3b3ca7a413d81b4a36e62cc33a4f3fd91f0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095783"
---
# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps

Мастер **Define New Office Web Apps Server** определяет новый сервер Office Web Apps Server в развертывании. Следует указать следующие сведения.

 **Office Web Apps Server FQDN:** Введите полностью квалифицированное доменное имя сервера, на который будет работать сервер Office Web Apps Server.

 **URL-адрес** обнаружения сервера веб-приложений Office: Введите полный единообразный локатор ресурсов (URL-адрес) Сервера веб-приложений Office

> [!TIP]
> По умолчанию URL-адрес **обнаружения Office Web Apps Server** создает URL-адрес на основе FQDN сервера веб-приложений Office в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . В большинстве случаев нет необходимости изменять формат по умолчанию. Возможно, потребуется изменить формат по умолчанию в том случае, если URL-адрес сервера веб-приложений Office и URL-адреса обнаружения Office Web Apps Server должны быть другими. Например, сервер Office Web Apps расположен в сети периметра и будет иметь другой URL-адрес в зависимости от расположения.

 **Сервер Office Web Apps** развертывается во внешней сети (то есть периметре или Интернете). Выберите поле для проверки, если сервер Office Web Apps Расположен за пределами внутреннего брандмауэра, например сети периметра, внешней сети или другой сетевой зоны, которая не является той же, что и внутренняя сеть.

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)