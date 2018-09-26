---
title: Перемещение нескольких пользователей в пилотный пул
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно переместить несколько пользователей из устаревшего пула для вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server.
ms.openlocfilehash: e96ef658f566f0e069f4db6e4f2f08e0410ea260
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028658"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Перемещение нескольких пользователей в пилотный пул

Можно переместить несколько пользователей из устаревшего пула для вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server.

 **В этой статье**
  
[Перемещение нескольких пользователей с помощью Скайп для панели управления 2019 Business Server](#sectionSection0)
  
[Перемещение нескольких пользователей с помощью Скайп для консоли 2019 Business Server](#sectionSection1)
  
[Перемещение всех пользователей в то же время с помощью Скайп для консоли 2019 Business Server](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>Перемещение нескольких пользователей с помощью Скайп для панели управления 2019 Business Server
<a name="sectionSection0"> </a>

1. Откройте Скайп для панели управления Business Server.
    
2. Щелкните элемент **Пользователи**, щелкните **Поиск**и нажмите кнопку **Найти**.
    
3. Выберите два пользователя, которые необходимо переместить в Скайп для пула Business Server 2019. В этом примере мы будут перемещаться Янг Чен и Клаус Хансен пользователей.
    
     ![Перемещение пользователей в пул регистра](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. В меню **Действие** выберите **переместить выбранных пользователей в пул**.
    
5. В раскрывающемся списке выберите Скайп для пула Business Server 2019.
    
6. Щелкните **Действие**и выберите команду **переместить выбранных пользователей в пул**. Нажмите **ОК**.
    
     ![Перемещение пользователей, диалоговое окно пул регистратора назначения](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Убедитесь, что столбец **пул регистратора** для пользователей теперь содержит Скайп для пула Business Server 2019, это означает, что пользователи были успешно перемещены. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение нескольких пользователей с помощью Скайп для консоли 2019 Business Server
<a name="sectionSection1"> </a>

1. Откройте Скайп для консоли Business Server 2019. 
    
2.  В командной строке введите следующую команду и **User1** и **Пользователь2** заменить имена определенного пользователя, которую требуется переместить и замените **pool_FQDN** имя пула, назначения. В этом примере мы будут перемещаться Чен Хао и Екатериной Иордания пользователей. 
    
  ```
  Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
  ```

     ![Пример командлет PowerShell Get-CsUser](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. В командной строке введите следующую команду: 
    
  ```
  Get-CsUser -Identity "User1"
  ```

4. Удостоверение **Пула регистратора** теперь должны указывать в пул, указанное в качестве **pool_FQDN** на предыдущем шаге. Наличие это удостоверение подтверждает, что пользователь успешно перемещен. Повторите шаг, чтобы убедиться, что **Пользователь2** был перемещен. 
    
     ![Выходные данные PowerShell Get-UsUser-Identity командлета](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение всех пользователей в то же время с помощью Скайп для консоли 2019 Business Server
<a name="sectionSection2"> </a>

В этом примере все пользователи были возвращены в устаревшем пуле (pool01.contoso.net). Использование Скайп для консоли 2019 Business Server, мы будет переместить всех пользователей в то же время в Скайп для пула Business Server 2019 (pool02.contoso.net).
  
1. Откройте Скайп для консоли Business Server 2019.
    
2. В командной строке введите следующую команду: 
    
  ```
  Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
  ```

     ![Командлет PowerShell и результатов в командной консоли](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Выполните **Командлет Get-CsUser** для одного из пробных пользователей. 
    
  ```
  Get-CsUser -Identity "Hao Chen"
  ```

4. Удостоверение **Пула регистратора** для каждого пользователя теперь указывает на пул, указанное в качестве **pool_FQDN** на предыдущем шаге. Наличие это удостоверение подтверждает, что пользователь успешно перемещен. 
    
5. Кроме того мы можно просмотреть список пользователей в Скайп для панели управления 2019 Business Server и убедитесь, что пул регистратора значение указывает на Скайп для пула Business Server 2019.
    
     ![Скайп для списка пользователей панели управления 2019 Business Server](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

