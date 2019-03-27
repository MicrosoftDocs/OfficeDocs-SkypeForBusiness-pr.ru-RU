---
title: Сценарии производительности для Скайп для Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d972382f-971e-4fa7-b7ee-8ab9d3a5c11d
description: Задачи, которые необходимо выполнить для настройки Скайп для 2015 Business Server для выполнения нагрузочного тестирования производительности и с помощью Stress and Performance Tool.
ms.openlocfilehash: 53504b714304b4b3cd18e44397ce0f06fcc59b63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874593"
---
# <a name="performance-scenarios-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Сценарии производительности для Скайп для Business Server 2015 Stress and Performance Tool
 
Задачи, которые необходимо выполнить для настройки Скайп для 2015 Business Server для выполнения нагрузочного тестирования производительности и с помощью Stress and Performance Tool.
  
Чтобы запустить Скайп для Business Server 2015 Stress and Performance Tool (LyncPerfTool), Скайп для Business Server 2015 топологии необходимо настроить для сценариев, относящиеся к вам. Если Скайп для Business Server 2015 не настроены или настроены неправильно, скорее всего, могут быть вашей моделирование нагрузки. С помощью Скайп для Business Server 2015 Stress and Performance Tool мы предлагаем пример Скайп скрипты консоли Business Server и основных файлов как часть [загрузить средство](https://www.microsoft.com/download/details.aspx?id=50367). Их можно использовать в качестве отправной точки для настройки вашей Скайп для развертывания Business Server. В этой статье описываются примеры Windows PowerShell, предоставляемые.
  
> [!NOTE]
> В этом разделе не позволит описывается настройка Скайп для Business Server 2015, как правило, у нас есть другие разделы, планирование и развертывание, которые. Для получения дополнительных сведений о работе с Windows PowerShell в Скайп для Business Server 2015 видеть Скайп для консоли Business Server документации по вставки введения. 
  
## <a name="about-running-skype-for-business-server-management-shell-scripts"></a>О запуске Скайп сценариев командной консоли для управления Business Server

Мы предлагаем примеры скриптов PowerShell, которые можно использовать для подготовки для нагрузочного моделирования. Так как эти сценарии, предназначены для моделирования нагрузки, вы найдете простой и Нестрогое их. Который может оказаться подходящую для производственной среды. Еще раз внимание, что эти сценарии, примеры, вам потребуется просмотреть их и во многих случаях внести изменения относится к вашей среде прежде чем приступать к практическим использовать их. Как минимум хотели бы, что необходимо изменить сценарий службы группы ответа (RSG) в топологии в виду (для указания агенты, назначенные группы агентов). Однако не нужно выполнить, если вам не нужно.
  
> [!CAUTION]
> Следует соблюдать осторожность в поиске и общие сведения об этих примеров. Скрипты будут перезаписаны все существующие параметры в топологии при запуске. 
  
## <a name="stress-and-performance-tool-client-version-names"></a>Имена версии клиента Stress and Performance Tool

Может потребоваться настроить политику проверки версии клиента, если ранее было изменено параметры из значения по умолчанию. Если вы не уверены в том об этом, обратитесь к [документации проверка версии клиента](https://msdn.microsoft.com/en-us/vsto/jj923060).
  
Stress and Performance Tool используется в следующих версиях агента пользователя по умолчанию при взаимодействии с Скайп для Business Server 2015:
  
- LSPT/15.0.0.0 (Скайп для Business Server 2015 Stress and Performance Tool)
    
- OCPHONE/.0.522
    
Для клиентских мобильных устройств (UCWA) в LyncPerfTool:
  
- UCWA средство производительности и веб-конференции
    
- Средство производительности UCWA/Mobile
    

