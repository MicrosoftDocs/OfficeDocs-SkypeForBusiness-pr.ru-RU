---
title: Включение и отключение архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Сводка: сведения о том, как включать и отключать архивацию в Skype для бизнеса Server.'
ms.openlocfilehash: 0e4ef4dde27ffa5856f2b73b69ffbadc24399c59
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286146"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>Включение и отключение архивации в Skype для бизнеса Server

**Сводка:** Сведения о том, как включать и отключать архивацию в Skype для бизнеса Server.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Включение и отключение архивации с панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.
    
4. Выберите в списке конфигураций архивации подходящую глоабальную конфигурацию либо конфигурацию сайта или пула, щелкните **Правка**, **Подробнее**, затем выполните следующие действия.
    
   - Чтобы включить архивирование только для сеансов обмена мгновенными сообщениями, нажмите **Архивировать сеансы мгновенных сообщений**.
    
   - Если требуется архивировать как сеансы обмена мгновенными сообщениями, так и конференции, щелкните **Архивировать сеансы мгновенных сообщений и веб-конференций**.
    
   - Если для данной конфигурации архивация не требуется, щелкните **Отключить архивацию**.
    
5. Нажмите **Исполнить**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Включение и отключение архивации с помощью Windows PowerShell

Можно также включить или отключить архивацию с помощью командлета **Set-CsArchivingConfiguration**. Например, следующая команда позволяет изменить все параметры конфигурации архивации таким образом, что архивироваться будут только сеансы обмена мгновенными сообщениями. При выполнении этой команды вызывается командлет **Get-CsArchivingConfiguration** без параметров, возвращающий все параметры конфигурации архивации, которая на данный момент применяется в организации. Затем эта коллекция передается командлету **Where-Object** для отбора только тех параметров, в которых свойству EnableArchiving присвоено значение (-eq) "ImAndWebConf". После этого отфильтрованная коллекция передается командлету **Set-CsArchivingConfiguration**, в результате чего для каждого элемента в коллекции значение свойства EnableArchiving изменяется на "ImOnly":
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
