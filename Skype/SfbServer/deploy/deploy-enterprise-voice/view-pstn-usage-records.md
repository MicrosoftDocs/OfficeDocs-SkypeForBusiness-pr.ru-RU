---
title: Просмотр записей использования ТСОП в Скайп для бизнеса
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Сводка: Узнайте, как для просмотра записей использования ТСОП Скайп для или с помощью панели управления сервера Business Скайп для консоли Business Server.'
ms.openlocfilehash: c5775f619c1da1e94ff6aad0b4794e686611ab92
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967145"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Просмотр записей использования ТСОП в Скайп для бизнеса
 
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
    
<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>См. также

[Создание или изменение политики голосовой связи и Настройка записей использования ТСОП в Скайп для бизнеса](voice-policy-and-pstn-usage-records.md)

