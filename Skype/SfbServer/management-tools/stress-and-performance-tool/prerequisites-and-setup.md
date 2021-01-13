---
title: Prerequisites and setup for the Skype for Busines Stress and Performance Tool
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Требования или необходимые условия для средства Stress and Performance Skype для бизнеса Server 2015. Установка или настройка средства Stress and Performance.
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814959"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Необходимые условия и настройка средства "Нагрузка и производительность Skype для шин"
 
Требования или необходимые условия для средства Stress and Performance Skype для бизнеса Server 2015. Установка или настройка средства Stress and Performance.
  
У нас есть следующие разделы требований к оборудованию, программному обеспечению и конфигурации системы, которые необходимо знать перед запуском средства Stress and Performance.
  
- [Требования к оборудованию клиента](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Требования к программному обеспечению клиента](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Требования к конфигурации](prerequisites-and-setup.md#ConfigReqs)
    
Кроме того, ниже приведен раздел об установке средства [Stress and Performance Skype для бизнеса Server 2015](prerequisites-and-setup.md#Installing)
  
## <a name="client-hardware-requirements"></a>Требования к оборудованию клиента
<a name="ClientHardwareReqs"> </a>

При запуске средства Stress and Performance в развертывании Skype для бизнеса Server 2015 вам, как минимум, потребуется, чтобы эти требования к оборудованию были выполнены для каждого 4500 пользователей в тесте:
  
- 1 гигабитный сетевой адаптер
    
- ОЗУ 8 ГБ
    
- 2 двухъядерных ЦП
    
## <a name="client-software-requirements"></a>Требования к программному обеспечению клиента
<a name="ClientSoftwareReqs"> </a>

Поддерживаемые операционные системы для средства Stress and Performance:
  
- Windows Server 2012
    
- Windows Server 2008 (64-битная версия)
    
Кроме того, компьютеры должны соответствовать следующим требованиям к программному обеспечению:
  
- Вам потребуется установить Microsoft .NET 4.5 Framework. [Скачайте .Net 4.5 Framework здесь.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Вам потребуется включить функцию "Возможности рабочего стола" в Windows.
    
- Вам потребуется установить Microsoft Visual C++ 2013 (x64). [Скачайте Visual C++ 2013 здесь](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Вам потребуется успешное развертывание Skype для бизнеса Server 2015.
    
## <a name="configuration-requirements"></a>Требования к конфигурации
<a name="ConfigReqs"> </a>

Для успешного запуска средства Stress and Performance вам потребуется выполнить указанные дополнительные настройки.
  
- Необходимо войти на сервер в качестве члена группы "Домен" или "Локальный администратор".
    
- Средство создания пользователей Skype для бизнеса Server 2015 (UserProvisioningTool.exe) нельзя установить на любом сервере переднего интерфейса или сервере Standard Edition, на котором будут находиться учетные записи пользователей.
    
- При многократном запуске средства создания пользователей у каждого пользователя, включенного в единую систему связи Майкрософт, должен быть уникальный номер телефона.
    
- Размер файла страницы должен управляться системами или должен быть по крайней мере в 1,5 раза больше объема ОЗУ в компьютерной системе.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Установка средства stress and performance Skype для бизнеса Server 2015
<a name="Installing"> </a>

Установка не может быть проще. Необходимо запустить файл установщика Windows **CapacityPlanningTool.msi** на каждом клиентский компьютер, который будет использовать для имитации пользовательского трафика, и на сервере переднего интерфейса в каждом пуле, где будут создаваться пользователи и контакты.
  
Чтобы скачать MSI-файл, а также примеры сценариев, упомянутые в других статьях, перейдите по ссылке Центра загрузки: Skype для бизнеса [Server 2015, stress and Performance Tool.](https://www.microsoft.com/download/details.aspx?id=50367)
  

