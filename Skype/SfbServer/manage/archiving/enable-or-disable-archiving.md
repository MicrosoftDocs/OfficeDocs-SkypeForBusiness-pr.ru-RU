---
title: Включение или отключение архивации в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 'Сводка: Узнайте, как включить или отключить архивацию в Скайп Business Server 2015.'
ms.openlocfilehash: ef4e24025d0f1c27b0249b4ea237a579882e74c2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server-2015"></a>Включение или отключение архивации в Skype для бизнеса Server 2015

**Сводка:** Узнайте, как включить или отключить архивацию в Скайп Business Server 2015.
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>Включение и отключение архивации с панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.
    
4. Выберите в списке конфигураций архивации подходящую глоабальную конфигурацию либо конфигурацию сайта или пула, щелкните **Правка**, **Подробнее**, затем выполните следующие действия.
    
   - Чтобы включить архивирование только для сеансов обмена мгновенными сообщениями, нажмите **Архивировать сеансы мгновенных сообщений**.
    
   - Если требуется архивировать как сеансы обмена мгновенными сообщениями, так и конференции, щелкните **Архивировать сеансы мгновенных сообщений и веб-конференций**.
    
   - Если для данной конфигурации архивация не требуется, щелкните **Отключить архивацию**.
    
5. Нажмите **Исполнить**.
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>Включение и отключение архивации с помощью Windows PowerShell

Можно также включить или отключить архивацию с помощью командлета **Set-CsArchivingConfiguration**. Например, следующая команда позволяет изменить все параметры конфигурации архивации таким образом, что архивироваться будут только сеансы обмена мгновенными сообщениями. Команда вызывает командлет **Get-CsArchivingConfiguration** без параметров для возврата всех параметров конфигурации архивации в настоящее время используемых в организации. Этот набор затем передается в командлет **Where-Object** , который выбирает только параметры, где свойство EnableArchiving равно (-eq) «ImAndWebConf». Отфильтрованный набор затем передается в командлет **Set-CsArchivingConfiguration** , который принимает каждого элемента в коллекции и изменяет значение EnableArchiving «ImOnly»:
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```