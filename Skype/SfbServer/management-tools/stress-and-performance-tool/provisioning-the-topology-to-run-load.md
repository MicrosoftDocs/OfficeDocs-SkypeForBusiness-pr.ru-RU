---
title: Подготовка топологии для выполнения нагрузки в сценариях "Стресс" и "Производительность"
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype для бизнеса Server 2015 г. изменения или подготовка к работе с топологией, чтобы пользователи успешно запускали средство Stress и Performance.
ms.openlocfilehash: 1967e923bff7ed0321b3b6b59dce763ba4f448bd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771915"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Подготовка топологии для выполнения нагрузки в сценариях "Стресс" и "Производительность"
 
Skype для бизнеса Server 2015 г. изменения или подготовка к работе с топологией, чтобы пользователи успешно запускали средство Stress и Performance.
  
В зависимости от существующих параметров и конфигурации развертывания Skype для бизнеса Server 2015 г. может потребоваться внести некоторые изменения в среду. Ниже приводится список этих изменений:
  
1. Установите политику Windows PowerShell для неограниченного. Если вы не уверены в том, к чему она настроена в настоящее время, вы можете открыть Skype для бизнеса Server и запустить эту команду:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Если значение Неограниченное не возвращается, необходимо выполнить следующее:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Чтобы эффективно настроить Skype для бизнеса Server, необходимо:
    
    - Ознакомьтесь с топологией Skype для бизнеса Server 2015 г. (например, имена компьютеров, экземпляры служб, имена сайтов и политики).
    
    - Назначьте некоторых пользователей, созданных группами, например группами охоты группы реагирования (например, SIP URIs).
    
3. Чтобы запустить скрипт из командной строки, можно использовать:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Как правило, после запуска скрипта из этого пакета в файле будут храниться следы, которые будут храниться в том же пути, где запускался сценарий. Существует также формат именования, $h \<scriptname\> $m $s.txt. Если вы запустили ArchivingPolicy.ps1 в 12:15, вы получите файл журнала с именем ArchivingPolicy121500.txt.
    
5. Хотя мы и предоставили эти примеры для конфигурации сервера, вы можете изменить конфигурацию и восстановить или откатить ее после завершения тестирования нагрузки.
    

