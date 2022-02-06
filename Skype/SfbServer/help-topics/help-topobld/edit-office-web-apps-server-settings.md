---
title: Изменение параметров сервера Office Web Apps
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: Вы редактируете свойства настраиваемого Office сервера веб-приложений. Для редактирования доступны следующие свойства.
---

# <a name="edit-office-web-apps-server-settings"></a>Изменение параметров сервера Office Web Apps

Вы редактируете свойства настраиваемого Office сервера веб-приложений. Для редактирования доступны следующие свойства.

 **Office веб-приложений Server FQDN**. Это свойство определяет полностью квалифицированное доменное имя сервера веб-приложений Office и должно соответствовать записи системы доменных имен (DNS) с записью A или AAAA (если используется IPv6).

 **Office веб-приложения** Сервер обнаружения: единый локатор ресурсов (URL)для доступа клиента к серверу Office веб-приложений, возможно, потребуется изменить этот адрес по умолчанию, если сервер находится в другой сетевой зоне, кроме внутренней сети для развертывания.

Установите флажок **Сервер Office Web Apps развернут во внешней сети**, если этот сервер развернут в сети периметра или в другой сетевой зоне за пределами внутреннего брандмауэра, разделяющего сеть периметра, сети без доверия и Интернет от внутреннего развертывания.

![Office веб-приложения Параметры expander.](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)