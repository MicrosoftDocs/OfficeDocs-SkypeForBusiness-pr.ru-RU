---
title: Добавление сервера Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'Мастер определения нового сервера Office Web Apps определяет новый сервер Office Web Apps в развертывании. You fill in the following information:'
ms.openlocfilehash: d1b36a2146d6be0addd9b66fd02665eee8de907d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275201"
---
# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps

Мастер **определения нового сервера Office Web Apps** определяет новый сервер Office Web Apps в развертывании. You fill in the following information:

 **Доменное имя сервера Office Web Apps**: введите полное доменное имя сервера, на котором будет размещен сервер Office Web Apps.

 **URL-адрес обнаружения сервера Office Web Apps**: введите полный URL-адрес сервера Office Web Apps.

> [!TIP]
> По умолчанию URL- **адрес обнаружения сервера Office Web Apps** — создание URL-адреса на основе полного доменного имени сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . In most cases you will not need to change the default format. Возможно, потребуется изменить формат по умолчанию в случае, если URL-адрес сервера Office Web Apps и веб-сайта Office Web Apps не должен отличаться. Например, сервер Office Web Apps размещается в демилитаризованной зоне, и его URL-адрес будет отличаться в зависимости от расположения.

 **Сервер Office Web Apps развернут во внешней сети (демилитаризованной зоне или Интернету)**: установите флажок, если сервер Office Web Apps входит за пределы внутреннего межсетевого экрана, например для демилитаризованной зоны, внешней сети или другой сетевой зоны. Это не то же самое, что и внутренняя сеть.

## <a name="see-also"></a>См. также

[Components and Topologies for Conferencing](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
