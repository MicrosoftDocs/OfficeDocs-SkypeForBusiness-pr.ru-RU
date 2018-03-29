---
title: Просмотр записей использования ТСОП в Skype для бизнеса 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Сводка: Узнайте, как для просмотра записей использования ТСОП Скайп для или с помощью панели управления сервера Business Скайп для консоли Business Server.'
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a>Просмотр записей использования ТСОП в Skype для бизнеса 2015
 
**Сводка:** Узнайте, как просматривать записи использования ТСОП Скайп для или с помощью панели управления сервера Business Скайп для консоли Business Server.
  
Запись режима работы с общей переключения телефонной сети общего пользования (PSTN) задает класс вызовов (например, внутренний, локальный или междугородных), которые могут выполняться разными пользователями или группами пользователей в организации. Дополнительные сведения см в документации по планированию [Работы с ТСОП](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) .
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>Просмотр записи об использовании ТСОП с помощью Скайп для панели управления Business Server

1. Откройте Скайп для панели управления Business Server.
    
2. На левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем — **Использование ТСОП**.
    
3. На странице **Использование ТСОП** выделите запись об использовании ТСОП, которую необходимо просмотреть, щелкните **Правка**, а затем щелкните **Показать подробности**. 
    
    > [!NOTE]
    > На доступной только для чтения странице выбранной записи об использовании ТСОП отображаются связанные маршруты и политики голосовой связи. 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>Чтобы просмотреть сведения об использовании ТСОП с помощью Скайп для командлетов командной консоли Business Server

- Чтобы просмотреть сведения об использовании ТСОП, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:
    
  ```
  Get-CsPstnUsage
  ```

    Этой командой возвращается информация, аналогичная следующим сведениям:
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a>См. также

#### 

[Создание или изменение политики голосовой связи и Настройка записей использования ТСОП в Скайп для бизнеса 2015](voice-policy-and-pstn-usage-records.md)

