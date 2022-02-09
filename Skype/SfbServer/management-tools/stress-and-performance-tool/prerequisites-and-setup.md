---
title: Необходимые условия и настройка Skype для средства стрессов и производительности Busines
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Требования или необходимые условия для Skype для бизнеса Server 2015 года. Установка или установка средства стресса и производительности.
ms.openlocfilehash: ec7e2b66427d360a9d54c38146289e4d08f9238d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399623"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a>Необходимые условия и настройка Skype для средства стрессов и производительности Busines
 
Требования или необходимые условия для Skype для бизнеса Server 2015 года. Установка или установка средства стресса и производительности.
  
У нас есть следующие разделы требований к оборудованию, программному обеспечению и конфигурации системы, которые необходимо знать перед запуском средства стресс и производительности:
  
- [Требования к оборудованию клиента](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [Требования к программному обеспечению клиента](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [Требования к конфигурации](prerequisites-and-setup.md#ConfigReqs)
    
Кроме того, ниже приведен раздел для установки средства [Skype для бизнеса Server 2015 г](prerequisites-and-setup.md#Installing).
  
## <a name="client-hardware-requirements"></a>Требования к оборудованию клиента
<a name="ClientHardwareReqs"> </a>

При запуске средства стресса и производительности Skype для бизнеса Server развертывания 2015 г. вам как минимум потребуется, чтобы эти требования к оборудованию были выполнены для каждого 4500 пользователей в тесте:
  
- 1 гигабитный сетевой адаптер
    
- ОЗУ 8 ГБ
    
- 2 двухъядерных процессора
    
## <a name="client-software-requirements"></a>Требования к программному обеспечению клиента
<a name="ClientSoftwareReqs"> </a>

Поддерживаемые операционные системы для Средства стресса и производительности:
  
- Windows Server 2012
    
- Windows Server 2008 (64-bit)
    
Кроме того, компьютеры должны соответствовать следующим требованиям программного обеспечения:
  
- Вам потребуется установить Microsoft .NET 4.5 Framework. [Скачайте .Net 4.5 Framework здесь.](https://www.microsoft.com/download/details.aspx?id=30653)
    
- Вам потребуется включить функцию Desktop Experience в Windows.
    
- Вам потребуется установить Microsoft Visual C++ 2013 (x64). [Скачайте Visual C++ 2013 здесь](https://www.microsoft.com/download/details.aspx?id=40784)
    
- Вам потребуется успешное развертывание Skype для бизнеса Server 2015 г.
    
## <a name="configuration-requirements"></a>Требования к конфигурации
<a name="ConfigReqs"> </a>

Для успешного запуска средства стресса и производительности необходимы дополнительные конфигурации:
  
- Необходимо войти на сервер в качестве члена группы домена или местного администратора.
    
- Нельзя установить средство создания Skype для бизнеса Server 2015 (UserProvisioningTool.exe) на любом интерфейсном сервере или выпуск Standard сервере, на котором будут находиться учетные записи пользователей.
    
- При многократном запуске средства создания пользователей каждый пользователь, включенный в Microsoft Unified Communications, должен иметь уникальный номер телефона.
    
- Размер файла страницы должен быть системным или в противном случае должен быть не менее чем в 1,5 раза больше объема оперативной памяти в компьютерной системе.
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Установка средства Skype для бизнеса Server 2015 г.
<a name="Installing"> </a>

Установка не может быть проще. Необходимо запустить файл Windows installer **CapacityPlanningTool.msi** на каждом клиентном компьютере, который вы собираетесь использовать для имитации пользовательского трафика, и на переднем сервере в каждом пуле, где будут создаваться пользователи и контакты.
  
Чтобы скачать .msi, а также примеры сценариев, упомянутых в других статьях, перейдите по ссылке Центр скачивания: [Skype для бизнеса Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).
  

