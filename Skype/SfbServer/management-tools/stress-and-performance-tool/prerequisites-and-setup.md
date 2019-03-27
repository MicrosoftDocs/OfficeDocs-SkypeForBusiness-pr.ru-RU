---
title: Необходимые компоненты и настройка для средства Stress and Performance Skype для бизнеса
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Требования и необходимые компоненты для средства Stress and Performance Skype для бизнеса Server 2015. Установка и настройка средства Stress and Performance.
ms.openlocfilehash: 840891a7a356866755e89a7ef63e23fb62bfa12f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895092"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Необходимые компоненты и настройка для средства Stress and Performance Skype для бизнеса
 
Требования и необходимые компоненты для средства Stress and Performance Skype для бизнеса Server 2015. Установка и настройка средства Stress and Performance.
  
Прежде чем запускать средство Stress and Performance, ознакомьтесь со следующими разделами, содержащими требования к конфигурации оборудования, программного обеспечения и системы:
  
- [требования к оборудованию клиента;](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [требования к программному обеспечению клиента;](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [требования к конфигурации.](prerequisites-and-setup.md#ConfigReqs)
    
Также ознакомьтесь с разделом [Установка средства Stress and Performance Skype для бизнеса Server 2015](prerequisites-and-setup.md#Installing).
  
## <a name="client-hardware-requirements"></a>Требования к оборудованию клиента
<a name="ClientHardwareReqs"> </a>

Для работы средства Stress and Performance в развертывании Skype для бизнеса Server 2015 на каждые 4500 пользователей, включаемых в тестирование, должны соблюдаться следующие минимальные требования к оборудованию:
  
- гигабитный сетевой адаптер;
    
- 8 ГБ ОЗУ;
    
- 2 двухъядерных процессора.
    
## <a name="client-software-requirements"></a>Требования к программному обеспечению клиента
<a name="ClientSoftwareReqs"> </a>

Средство Stress and Performance поддерживает следующие операционные системы:
  
- Windows Server 2012
    
- Windows Server 2008 (64-разрядная).
    
Кроме того, компьютеры должны удовлетворять следующим минимальным требованиям к программному обеспечению.
  
- Установленная платформа Microsoft .NET 4.5 Framework. [Загрузить .net 4.5 Framework здесь.](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- Включенная функция возможностей рабочего стола в Windows.
    
- Установленная среда Microsoft Visual C++ 2013 (x64). [Загрузите Visual C++ 2013 здесь](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- Успешное развертывание Skype для бизнеса Server 2015.
    
## <a name="configuration-requirements"></a>Требования к конфигурации
<a name="ConfigReqs"> </a>

Для работы средства Stress and Performance необходимо выполнить следующие дополнительные настройки конфигурации.
  
- Выполните вход на сервер в качестве участника домена или группы локальных администраторов.
    
- Средство создания пользователей Skype для бизнеса Server 2015 (UserProvisioningTool.exe) нельзя устанавливать на сервер переднего плана или сервер Standard Edition, где будут размещаться учетные записи пользователей.
    
- При многократном запуске средства создания пользователей каждому пользователю, для которого включена поддержка объединенных коммуникаций Майкрософт, должен быть назначен уникальный номер телефона.
    
- Размер файла подкачки должен задаваться системой или должен как минимум в 1,5 раза превышать объем ОЗУ в системе компьютера.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Установка средства Stress and Performance Skype для бизнеса Server 2015.
<a name="Installing"> </a>

Установка этого средства максимально упрощена. Запустите файл установщика Windows **CapacityPlanningTool.msi** на каждом клиентском компьютере, где планируется моделирование трафика пользователей, а также на сервере переднего плана в каждом пуле, где будут создаваться пользователи и контакты.
  
Чтобы загрузить MSI-файла, а также примеры сценариев, упомянутые в других статьях, перейдите к ссылку центра загрузки: [Скайп для Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

