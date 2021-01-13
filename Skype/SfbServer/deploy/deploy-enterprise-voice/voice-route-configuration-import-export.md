---
title: Экспорт или импорт файла конфигурации маршрута голосовых вызовов в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 02ce922d-9ca8-4513-b09f-9de51f5c5bdc
description: Сводка. Узнайте, как экспортировать или импортировать файл конфигурации маршрутки голосовой почты в Skype для бизнеса Server с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: df5ca58ebc7b92fea5236b957f4819ed3602d896
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830359"
---
# <a name="export-or-import-a-voice-route-configuration-file-in-skype-for-business"></a>Экспорт или импорт файла конфигурации маршрута голосовых вызовов в Skype для бизнеса
 
**Сводка:** Learn how to export or import a voice routing configuration file in Skype for Business Server by using the Skype for Business Server Control Panel.
  
Если вы хотите сохранить конфигурацию маршрутации голосовых данных без ее публикации, выполните следующие действия, чтобы сохранить и получить снимок конфигурации маршрутации голосовых данных. 
  
When you import a voice routing configuration file (.vcfg), but changes have been made to the voice routing configuration on the server in the meantime, the pages in the **Voice Routing** group in Skype for Business Server Control Panel will indicate that there are uncommitted changes to voice routing. Эти несохраненные изменения представляют собой разницу между двумя конфигурациями, которые нуждаются в сверке.
  
Если вы влияли на параметры на любой странице группы, изменения сохраняются в экспортируемом файле конфигурации голосовой связи (VCFG). Это позволяет внести изменения в конфигурацию маршрутации голосовой связи во время нескольких сеансов перед публикацией изменений. 
  
### <a name="to-export-a-voice-routing-configuration"></a>Экспорт конфигурации маршрутизации голосовых данных

1. Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.
    
2. Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните элемент **Маршрутизация голосовых данных**.
    
4. В меню **Действия** щелкните пункт **Экспорт конфигурации**.
    
5. Укажите расположение и имя файла, а затем нажмите кнопку **Сохранить**.
    
### <a name="to-import-a-voice-routing-configuration"></a>Импорт конфигурации маршрутации голосовой почты

1. Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.
    
2. Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.
    
4. В меню **"Действия"** выберите пункт **"Импорт конфигурации".**
    
5. Найдите файл конфигурации, который нужно импортировать, и нажмите кнопку **"Открыть".**
    
6. Нажмите кнопку **Зафиксировать**, а затем нажмите кнопку **Зафиксировать все**.
    
    > [!NOTE]
    > При импорте файла конфигурации голосовой почты необходимо выполнить команду **"Зафиксировать все",** чтобы опубликовать изменение конфигурации. For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.
  

