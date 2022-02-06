---
title: Добавление сервера Office Web Apps
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ROBOTS: 'NOINDEX, NOFOLLOW'
description: Мастер Define New Office Apps Server определяет новый Office сервер веб-приложений в развертывании. Следует указать следующие сведения.
---

# <a name="add-office-web-apps-server"></a>Добавление сервера Office Web Apps

Мастер **Define New Office Apps Server** определяет новый Office сервера веб-приложений в развертывании. Следует указать следующие сведения.

 **Office веб-приложений Server FQDN**: введите полностью квалифицированное доменное имя сервера, на который будет Office сервер веб-приложений

 **Office веб-приложения Сервер** обнаружения: Введите полный единый локатор ресурсов (URL-адрес) сервера Office веб-приложений

> [!TIP]
> По умолчанию URL Office сервера обнаружения веб **Office** веб-приложений— это создание URL-адреса на основе FQDN сервера веб Office приложений в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . В большинстве случаев нет необходимости изменять формат по умолчанию. Возможно, потребуется изменить формат по умолчанию в том случае, если Office сервера веб Office и URL-адрес обнаружения веб-приложений. Например, Office сервер веб-приложений размещен в сети периметра и будет иметь другой URL-адрес в зависимости от расположения.

 **Office сервер веб-приложений** развертывается во внешней сети (то есть периметре или Интернете): Выберите контрольный ящик, если сервер Office веб-приложений расположен за пределами внутреннего брандмауэра, например сети периметра, внешней сети или другой сетевой зоны, которая не является той же, что и внутренняя сеть.

## <a name="see-also"></a>См. также

[Компоненты и топологии для конференц-связи](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)