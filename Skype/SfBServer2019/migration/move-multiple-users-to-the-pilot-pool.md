---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Вы можете переместить нескольких пользователей из устаревшего пула в Skype для бизнеса Server 2019 для пилотного пула с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.
ms.openlocfilehash: abaffea04ff190b2ae99639484f63b564fd7784a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988954"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Перемещение нескольких пользователей в пилотный пул

Вы можете переместить нескольких пользователей из устаревшего пула в Skype для бизнеса Server 2019 для пилотного пула с помощью панели управления Skype для бизнеса Server 2019 или консоли управления Skype для бизнеса Server 2019.

 **В этой статье**
  
[Перемещение нескольких пользователей с помощью панели управления "Skype для бизнеса Server 2019"](#sectionSection0)
  
[Перемещение нескольких пользователей с помощью управляющей оболочки Skype для бизнеса Server 2019](#sectionSection1)
  
[Перемещение всех пользователей одновременно с помощью управляющей оболочки Skype для бизнеса Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Перемещение нескольких пользователей с помощью панели управления "Skype для бизнеса Server 2019"
<a name="sectionSection0"> </a>

1. Откройте панель управления Skype для бизнеса Server.
    
2. Нажмите кнопку **Пользователи**, нажмите **Поиск**, а затем — **найти**.
    
3. Выберите двух пользователей, которых вы хотите переместить в пул 2019 в Skype для бизнеса Server. В этом примере мы перейдем пользователей Чена Маслов и предложения Хансен.
    
     ![Перемещение пользователей в определенную группу регистров](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. В меню **действия** выберите пункт **переместить выбранных пользователей в пул**.
    
5. В раскрывающемся списке выберите пул 2019 в Skype для бизнеса Server.
    
6. Нажмите кнопку **действие**и выберите пункт **переместить выбранных пользователей в пул**. Нажмите кнопку **ОК**.
    
     ![Перемещение пользователей, диалоговое окно «пул конечных регистраторов»](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Убедитесь в том, что столбец **пула регистратора** для пользователей теперь содержит пул Skype для бизнеса Server 2019, указывающий на то, что пользователи успешно перемещены. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение нескольких пользователей с помощью управляющей оболочки Skype для бизнеса Server 2019
<a name="sectionSection1"> </a>

1. Откройте консоль управления Skype для бизнеса Server 2019. 
    
2. В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** именами пользователей, которых вы хотите переместить, и замените **pool_FQDN** именем целевого пула. В этом примере мы перейдем пользователей Хао Чен и Katie Иордания. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Пример командлета Get-CsUser PowerShell](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. В командной строке введите следующую команду: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Удостоверение **пула регистратора** теперь должно указывать на пул, который вы указали, как **pool_FQDN** на предыдущем шаге. Присутствие этого удостоверения подтверждает, что пользователь успешно переместился. Повторите действия, чтобы убедиться, что **Пользователь2** перемещен. 
    
     ![Вывод командлета PowerShell Get-Усусер-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение всех пользователей одновременно с помощью управляющей оболочки Skype для бизнеса Server 2019
<a name="sectionSection2"> </a>

В этом примере все пользователи возвращены в пул устаревших версий (pool01.contoso.net). С помощью командной консоли Skype для бизнеса Server 2019 все пользователи одновременно будут переноситься в пул "Skype для бизнеса Server 2019" (pool02.contoso.net).
  
1. Откройте консоль управления Skype для бизнеса Server 2019.
    
2. В командной строке введите следующую команду: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Командлет PowerShell и результаты в командной консоли](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Запустите **Get-CsUser** для одного из пилотных пользователей. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. Удостоверение **пула регистраторов** для каждого пользователя теперь указывает на пул, указанный в предыдущем действии, **pool_FQDN** . Присутствие этого удостоверения подтверждает, что пользователь успешно переместился. 
    
5. Кроме того, мы можем просмотреть список пользователей на панели управления Skype для бизнеса Server 2019 и убедиться, что значение пула регистратора теперь указывает на пул Skype для бизнеса Server 2019.
    
     ![Список пользователей панели управления Skype для бизнеса Server 2019](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

