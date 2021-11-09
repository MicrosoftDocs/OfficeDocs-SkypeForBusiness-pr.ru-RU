---
title: Изменение параметров сервера Office Web Apps
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
ROBOTS: NOINDEX, NOFOLLOW
description: Вы редактируете свойства настраиваемого Office сервера веб-приложений. Для редактирования доступны следующие свойства.
ms.openlocfilehash: 89c4676a5bd8e26ff269698ca4c7688c6a5c1c05
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831193"
---
# <a name="edit-office-web-apps-server-settings"></a>Изменение параметров сервера Office Web Apps

Вы редактируете свойства настраиваемого Office сервера веб-приложений. Для редактирования доступны следующие свойства.

 **Office веб-приложения Server FQDN:** это свойство определяет полностью квалифицированное доменное имя сервера веб-приложений Office и должно соответствовать системе доменных имен (DNS) с записью A или AAAA (если используется IPv6).

 **Office веб-приложения** Сервер обнаружения : Единый локатор ресурсов (URL) для клиентского доступа к серверу веб-приложений Office, возможно, потребуется изменить этот адрес по умолчанию, если сервер находится в другой сетевой зоне, кроме внутренней сети для развертывания.

Установите флажок **Сервер Office Web Apps развернут во внешней сети**, если этот сервер развернут в сети периметра или в другой сетевой зоне за пределами внутреннего брандмауэра, разделяющего сеть периметра, сети без доверия и Интернет от внутреннего развертывания.

![Office Веб-приложения Параметры расширятель.](../../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)