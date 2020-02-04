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
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'Мастер определения нового сервера Office Web Apps определяет новый сервер Office Web Apps в развертывании. You fill in the following information:'
ms.openlocfilehash: 2af737d2579fb4d89c6670e016ff89a8d24f3743
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685092"
---
# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps

Мастер **определения нового сервера Office Web Apps** определяет новый сервер Office Web Apps в развертывании. You fill in the following information:

 **Доменное имя сервера Office Web Apps**: введите полное доменное имя сервера, на котором будет размещен сервер Office Web Apps.

 **URL-адрес обнаружения сервера Office Web Apps**: введите полный URL-адрес сервера Office Web Apps.

> [!TIP]
> По умолчанию URL- **адрес обнаружения сервера Office Web Apps** — создание URL-адреса на основе полного доменного имени сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . In most cases you will not need to change the default format. Возможно, потребуется изменить формат по умолчанию в случае, если URL-адрес сервера Office Web Apps и веб-сайта Office Web Apps не должен отличаться. Например, сервер Office Web Apps размещается в демилитаризованной зоне, и его URL-адрес будет отличаться в зависимости от расположения.

 **Сервер Office Web Apps развернут во внешней сети (то есть в сети периметра/Интернет)**: установите флажок, если сервер Office Web Apps размещается за пределами вашего внутреннего брандмауэра, например с демилитаризованной зоной, внешней сетью или другой сетевой зоной, не совпадающей с внутренней сетью.

## <a name="see-also"></a>См. также

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
