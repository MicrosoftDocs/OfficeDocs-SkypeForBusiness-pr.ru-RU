---
title: Перемещение нескольких пользователей в пул пилотов
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Вы можете переместить несколько пользователей из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 г., используя панель управления Skype для бизнеса Server 2019 или Skype для бизнеса Server 2019.
ms.openlocfilehash: fc4d14d26a76ff4dbfc690fc7517aba77afd253f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726318"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Перемещение нескольких пользователей в пул пилотов

Вы можете переместить несколько пользователей из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 г., используя панель управления Skype для бизнеса Server 2019 или Skype для бизнеса Server 2019.

 **Содержание**
  
[Перемещение нескольких пользователей с помощью панели управления Skype для бизнеса Server 2019 г.](#sectionSection0)
  
[Перемещение нескольких пользователей с помощью Skype для бизнеса Server 2019](#sectionSection1)
  
[Одновременное перемещение всех пользователей с помощью Skype для бизнеса Server 2019](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Перемещение нескольких пользователей с помощью панели управления Skype для бизнеса Server 2019 г.
<a name="sectionSection0"> </a>

1. Откройте панель Skype для бизнеса Server управления.
    
2. Щелкните **Пользователи,** **щелкните Поиск,** а затем нажмите **кнопку Найти**.
    
3. Выберите двух пользователей, которые необходимо переместить в Skype для бизнеса Server 2019 г. В этом примере мы переместим пользователей Chen Yang и Claus Hansen.
    
     ![Перемещение пользователей в определенный пул реестра.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.
    
5. Из выпадаемого списка выберите пул Skype для бизнеса Server 2019 г.
    
6. Щелкните **Действие,** а затем **нажмите кнопку Переместить выбранных пользователей для пула**. Нажмите кнопку **ОК**.
    
     ![Перемещение пользователей, диалоговое окно пула регистратора назначения.](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Убедитесь,  что столбец пула регистратора для пользователей теперь содержит пул Skype для бизнеса Server 2019, что указывает на успешное перемещение пользователей. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение нескольких пользователей с помощью Skype для бизнеса Server 2019
<a name="sectionSection1"> </a>

1. Откройте оболочку Skype для бизнеса Server 2019. 
    
2. В командной строке введите следующую строку и замените **User1** и **User2** определенными именами пользователей, которые необходимо переместить, и **замените** pool_FQDN имя пула назначения. В этом примере мы переместим пользователей Hao Chen и Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Пример powerShell Get-CsUser.](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Введите в командной строке следующую команду: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Удостоверение **Пул регистратора** должно сейчас указывать на пул, заданный на предыдущем шаге как **pool_FQDN**. Присутствие этого удостоверения подтверждает, что пользователь успешно перемещен. Повторите шаг, чтобы **убедиться в перемещении пользователя 2.** 
    
     ![Вывод комлета PowerShell Get-UsUser Identity.](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Одновременное перемещение всех пользователей с помощью Skype для бизнеса Server 2019
<a name="sectionSection2"> </a>

В этом примере все пользователи были возвращены в устаревший пул (pool01.contoso.net). Используя Skype для бизнеса Server 2019, мы будем перемещать всех пользователей одновременно в пул Skype для бизнеса Server 2019 (pool02.contoso.net).
  
1. Откройте оболочку Skype для бизнеса Server 2019.
    
2. Введите в командной строке следующую команду: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![Cmdlet PowerShell и приводит к управленческой оболочке.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Запустите **Get-CsUser для** одного из пилотных пользователей. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. Удостоверение **пула регистраторов** для каждого пользователя теперь указывает на пул, указанный pool_FQDN **на** предыдущем шаге. Наличие этого идентификатора подтверждает успешное перемещение пользователя. 
    
5. Кроме того, мы можем просмотреть список пользователей в панели управления Skype для бизнеса Server 2019 г. и убедиться, что значение пула регистраторов указывает на пул Skype для бизнеса Server 2019 г.
    
     ![Skype для бизнеса Server панели управления 2019.](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

