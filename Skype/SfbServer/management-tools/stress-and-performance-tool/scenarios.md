---
title: Сценарии производительности для средства "Нагрузка и производительность Skype для бизнеса Server 2015"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Задачи, необходимые для настройки Skype для бизнеса Server 2015 для выполнения тестирования производительности и загрузки с помощью средства Stress and Performance Tool.
ms.openlocfilehash: 3edc945f09ef5b2c7c6ecdefcbc66166f0945aec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814709"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Сценарии производительности для средства "Нагрузка и производительность Skype для бизнеса Server 2015"
 
Задачи, необходимые для настройки Skype для бизнеса Server 2015 для выполнения тестирования производительности и загрузки с помощью средства Stress and Performance Tool.
  
To run the Skype for Business Server 2015 Stress and Performance Tool (LyncPerfTool), the Skype for Business Server 2015 topology must first be configured for scenarios relevant to you. If Skype for Business Server 2015 isn't configured, or is configured incorrectly, your load simulation is very likely to fail. В средстве Skype для бизнеса Server 2015 Stress and Performance Tool мы предоставляем примеры сценариев оболочки управления Skype для бизнеса Server и базовых файлов ресурсов в рамках скачивания [средства.](https://www.microsoft.com/download/details.aspx?id=50367) Их можно использовать в качестве отправной точки для настройки развертывания Skype для бизнеса Server. В этой статье описываются Windows PowerShell примеры.
  
> [!NOTE]
> В этом разделе не описывается, как настроить Skype для бизнеса Server 2015 в целом. Для этого у нас есть другие разделы по планированию и развертыванию. Дополнительные сведения о работе с Windows PowerShell в Skype для бизнеса Server 2015 см. в документации по skype для бизнеса Server Management Shell на веб-вкладке "Вставка". 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>О запуске сценариев оболочки управления Skype для бизнеса Server

Мы предоставляем примеры сценариев PowerShell, которые можно использовать для подготовки к имитации загрузки. Так как эти сценарии предназначены для моделирования нагрузки, они будут простыми и неумещенными. Возможно, это не подходит для вашей производственной среды. Опять же, мы подчеркиваем, что эти сценарии являются примерами, вам потребуется просмотреть их и во многих случаях внести изменения, релевантные для вашей среды, прежде чем использовать их на практике. Как минимум, предполагается, что вам потребуется изменить скрипт группы ответа (RSG) с учетом топологии (чтобы указать агентов, которые назначены группам агентов). Но это не требуется, если это не требуется.
  
> [!CAUTION]
> Внимательно просмотрите эти примеры и понимайте их. При запуске сценарии переопишут все существующие параметры в топологии. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Названия версий клиентов средства stress and Performance Tool

Вам может потребоваться настроить политику проверки версий клиентов, если вы ранее изменили параметры со значений по умолчанию. Если вы не уверены в этом, проверьте документацию по проверке [версий клиентов.](https://msdn.microsoft.com/vsto/jj923060)
  
Средство stress and Performance использует следующие версии агента пользователя по умолчанию при связи со Skype для бизнеса Server 2015:
  
- LSPT/15.0.0.0 (Skype for Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Для клиента Mobility (UCWA) в LyncPerfTool:
  
- UCWA Perf Tool/Web Conference
    
- UCWA Perf Tool/Mobile
    

