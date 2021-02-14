---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753431"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Перемещение нескольких пользователей в пилотный пул

You can move multiple users from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell.

 **Содержание**
  
[Перемещение нескольких пользователей с помощью панели управления Skype для бизнеса Server 2019](#sectionSection0)
  
[Перемещение нескольких пользователей с помощью оболочки управления Skype для бизнеса Server 2019](#sectionSection1)
  
[Перемещение всех пользователей одновременно с помощью оболочки управления Skype для бизнеса Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Перемещение нескольких пользователей с помощью панели управления Skype для бизнеса Server 2019
<a name="sectionSection0"> </a>

1. Откройте панель управления Skype для бизнеса Server.
    
2. Щелкните **"Пользователи",** **"Поиск"** и выберите **"Найти".**
    
3. Выберите двух пользователей, которые нужно переместить в пул Skype для бизнеса Server 2019. В этом примере мы переместим пользователей Chen Yang и Claus Hansen.
    
     ![Перемещение пользователей в определенный пул регистрации](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.
    
5. В выпадаемом списке выберите пул Skype для бизнеса Server 2019.
    
6. Щелкните **"Действие"** и выберите **"Переместить выбранных пользователей в пул".** Нажмите **ОК**.
    
     ![Диалоговое окно "Перемещение пользователей, пул регистратора назначения"](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Убедитесь,  что столбец пула регистратора для пользователей теперь содержит пул Skype для бизнеса Server 2019, который указывает, что пользователи были успешно перемещены. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение нескольких пользователей с помощью оболочки управления Skype для бизнеса Server 2019
<a name="sectionSection1"> </a>

1. Откройте оболочку управления Skype для бизнеса Server 2019. 
    
2. В командной строке введите следующую команду и замените **User1** и  **User2** на конкретные имена пользователей, которых необходимо переместить, и замените pool_FQDN на имя конечного пула. В этом примере мы переместим пользователей Hao Chen и Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Пример Get-CsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Введите в командной строке следующую команду: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Удостоверение **Пул регистратора** должно сейчас указывать на пул, заданный на предыдущем шаге как **pool_FQDN**. Присутствие этого удостоверения подтверждает, что пользователь успешно перемещен. Повторите шаг, чтобы **убедиться, что пользователь User2** перемещен. 
    
     ![Выходные данные powerShell Get-UsUser -Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение всех пользователей одновременно с помощью оболочки управления Skype для бизнеса Server 2019
<a name="sectionSection2"> </a>

В этом примере все пользователи возвращаются в устаревший пул (pool01.contoso.net). С помощью оболочки управления Skype для бизнеса Server 2019 мы переместим всех пользователей одновременно в пул Skype для бизнеса Server 2019 (pool02.contoso.net).
  
1. Откройте оболочку управления Skype для бизнеса Server 2019.
    
2. Введите в командной строке следующую команду: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Команды PowerShell и результаты в оболочке управления](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Запустите **get-CsUser** для одного из пилотных пользователей. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. Удостоверение **пула регистратора** для каждого пользователя теперь указывает на пул, указанный pool_FQDN **предыдущем** шаге. Наличие этого идентификатора подтверждает успешное перемещение пользователя. 
    
5. Кроме того, мы можем просмотреть список пользователей на панели управления Skype для бизнеса Server 2019 и убедиться, что значение пула регистратора указывает на пул Skype для бизнеса Server 2019.
    
     ![Список пользователей панели управления Skype для бизнеса Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

