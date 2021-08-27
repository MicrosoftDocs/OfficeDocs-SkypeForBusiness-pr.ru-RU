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
ms.localizationpriority: medium
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: Мастер Define New Office Apps Server определяет новый Office сервер веб-приложений в развертывании. Следует указать следующие сведения.
ms.openlocfilehash: 09ce8e0db72fdcd4dfcc4ce668302e89c40b9281
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605308"
---
# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps

Мастер **define new Office Apps Server** определяет новый Office сервера веб-приложений в развертывании. Следует указать следующие сведения.

 **Office веб-приложений Server FQDN:** Введите полное доменное имя сервера, на который будет Office веб-сервер приложений

 **Office веб-приложения Сервер** обнаружения : Введите полный единый локатор ресурсов (URL-адрес) сервера веб Office приложений

> [!TIP]
> По умолчанию URL Office сервера обнаружения **веб Office,** создает URL-адрес на основе FQDN сервера веб Office приложений в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . В большинстве случаев нет необходимости изменять формат по умолчанию. Возможно, потребуется изменить формат по умолчанию в том случае, если Office сервера веб Office и URL-адрес обнаружения веб-приложений. Например, Office сервер веб-приложений размещен в сети периметра и будет иметь другой URL-адрес в зависимости от расположения.

 Office сервер веб-приложений развертывается во внешней сети (то есть периметре или **Интернете)**: Выберите контрольный ящик, если сервер Office веб-приложений расположен за пределами внутреннего брандмауэра, например сети периметра, внешней сети или другой сетевой зоны, которая не является той же, что и внутренняя сеть.

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)