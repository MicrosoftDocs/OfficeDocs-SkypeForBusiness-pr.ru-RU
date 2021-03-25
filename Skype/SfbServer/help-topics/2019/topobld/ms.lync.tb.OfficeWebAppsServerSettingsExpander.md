---
title: Изменение параметров сервера Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: Вы редактируете свойства настроенного Сервера веб-приложений Office. Для редактирования доступны следующие свойства.
ms.openlocfilehash: 0c5dbff11d6cc2f6b25f3afa77cfe12e1e511a8a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121082"
---
# <a name="edit-office-web-apps-server-settings"></a>Изменение параметров сервера Office Web Apps

Вы редактируете свойства настроенного Сервера веб-приложений Office. Для редактирования доступны следующие свойства.

 **Office Web Apps Server FQDN.** Это свойство определяет полностью квалифицированное доменное имя Сервера веб-приложений Office и должно соответствовать записи системы доменных имен (DNS) хоста A или AAAA (если используется IPv6).

 URL-адрес обнаружения Office Web **Apps Server.** Единый локатор ресурсов (URL-адрес) для клиентского доступа к серверу Office Web Apps, возможно, потребуется изменить этот адрес по умолчанию, если сервер находится в другой сетевой зоне, кроме внутренней сети для развертывания.

Установите флажок **Сервер Office Web Apps развернут во внешней сети**, если этот сервер развернут в сети периметра или в другой сетевой зоне за пределами внутреннего брандмауэра, разделяющего сеть периметра, сети без доверия и Интернет от внутреннего развертывания.

![Расширение параметров веб-приложений Office](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)