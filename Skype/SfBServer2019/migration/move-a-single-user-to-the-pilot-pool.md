---
title: Перемещение одного пользователя в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно переместить пользователя из устаревшего пула в вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server. В следующем примере, в столбец пул регистратора pool01.contoso.net является устаревшего пула и все шесть из этих пользователей подключения в этот пул. Используйте следующие процедуры для перехода пользователя к вашей Скайп для пула Business Server 2019, с помощью Скайп для панели управления 2019 Business Server и Скайп для консоли Business Server.
ms.openlocfilehash: 94896ce2ea05a3102d5a7643e3f26430e74bfe19
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880251"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Перемещение одного пользователя в пилотный пул

Можно переместить пользователя из устаревшего пула в вашей Скайп для Business Server 2019 пилотного пула с помощью Скайп для панели управления 2019 Business Server или Скайп для консоли 2019 Business Server. В следующем примере, в столбце **пул регистратора** **pool01.contoso.net** является устаревшего пула и все шесть из этих пользователей подключения в этот пул. Используйте следующие процедуры для перехода пользователя к вашей Скайп для пула Business Server 2019, с помощью Скайп для панели управления 2019 Business Server и Скайп для консоли Business Server. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Перемещение пользователя с помощью Скайп для панели управления 2019 Business Server
  
1. Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.
    
2. Откройте **Скайп для панели управления Business Server**.
    
3. Щелкните элемент **Пользователи**, щелкните **Поиск**и нажмите кнопку **Найти**.
    
4. Выберите пользователя, который требуется переместить в Скайп для пула Business Server 2019. В данном примере мы будем перемещать пользователя Sara Davis.
    
5. В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.
    
6. В раскрывающемся списке выберите Скайп для пула Business Server 2019.
    
7. Щелкните **Действие**и выберите команду **переместить выбранных пользователей в пул**. Нажмите **ОК**.
  
8. Убедитесь, что столбец **пул регистратора** для пользователя теперь содержит Скайп для пула Business Server 2019, это означает, что пользователь успешно перемещен. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение пользователя с помощью Скайп для консоли 2019 Business Server

1. Откройте Скайп для консоли Business Server.
    
2. В командной строке введите следующую команду: 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. После этого в командной строке введите следующую команду: 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. Идентификатор **RegistrarPool** теперь указывает на Скайп для пула Business Server 2019. Наличие это удостоверение подтверждает, что пользователь успешно перемещен. 

    > [!NOTE]
    > Для сведений о командлет **Get-CsUser** выполните следующую команду: **Get-Help Get-CsUser-подробные**
  

