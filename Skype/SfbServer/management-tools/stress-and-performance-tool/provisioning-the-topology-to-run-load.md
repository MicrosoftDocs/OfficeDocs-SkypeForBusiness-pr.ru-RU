---
title: Подготовка топологии для запуска нагрузки в сценариях stress и Performance
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
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Изменения или подготовка топологии Skype для бизнеса Server 2015, позволяющие пользователям успешно запускать средство Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814939"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Подготовка топологии для запуска нагрузки в сценариях stress и Performance
 
Изменения или подготовка топологии Skype для бизнеса Server 2015, позволяющие пользователям успешно запускать средство Stress and Performance.
  
В зависимости от существующих параметров и конфигурации развертывания Skype для бизнеса Server 2015 может потребоваться внести некоторые изменения в среду. Ниже приводится список этих изменений.
  
1. Установите для Windows PowerShell выполнения неограниченный доступ. If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Если значение Unrestricted не возвращается, необходимо выполнить следующее:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Для эффективной настройки Skype для бизнеса Server необходимо:
    
    - Ознакомьтесь с топологией Skype для бизнеса Server 2015 (например, именами компьютеров, экземплярами служб, именами сайтов и политиками).
    
    - Назначьте некоторых пользователей, созданных группам, таким как группы ответа (например, SIP URIS).
    
3. Чтобы запустить сценарий из командной строки, можно использовать:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Как правило, после запуска скрипта из этого пакета итоговые трассировки будут храниться в файле, который находится в том же пути, где был запускаться сценарий. Также существует формат имен, \<scriptname\> $h$m$s.txt. Поэтому если вы запустили ArchivingPolicy.ps1 23:15, вы получите файл журнала с именем ArchivingPolicy121500.txt.
    
5. Несмотря на то что мы предоставили эти примеры для конфигурации сервера, вы можете изменить конфигурацию и восстановить или откатить ее после завершения тестирования нагрузки.
    

