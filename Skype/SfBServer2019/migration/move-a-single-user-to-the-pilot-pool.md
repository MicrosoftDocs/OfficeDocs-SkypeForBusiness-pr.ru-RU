---
title: Перемещение одного пользователя в пилотный пул
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
description: You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell. В примере ниже в столбце пула регистратора pool01.contoso.net является устаревшим пулом, и все шесть из этих пользователей подключены к этому пулу. Используйте следующие процедуры для перемещения пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и skype для бизнеса Server Management Shell.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752511"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Перемещение одного пользователя в пилотный пул

You can move a user from your legacy pool to your Skype for Business Server 2019 pilot pool using Skype for Business Server 2019 Control Panel or Skype for Business Server 2019 Management Shell. В примере ниже  в столбце пула регистратора pool01.contoso.net **является** устаревшим пулом, и все шесть из этих пользователей подключены к этому пулу. Используйте следующие процедуры для перемещения пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и оболочки управления Skype для бизнеса Server. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Перемещение пользователя с помощью панели управления Skype для бизнеса Server 2019
  
1. Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.
    
2. Откройте **панель управления Skype для бизнеса Server.**
    
3. Щелкните **"Пользователи",** **"Поиск"** и выберите **"Найти".**
    
4. Выберите пользователя, который будет переходить в пул Skype для бизнеса Server 2019. В данном примере мы перемещаем пользователя с именем Sara Davis.
    
5. В меню **Действие** выберите команду **Переместить выбранных пользователей в пул**.
    
6. В выпадаемом списке выберите пул Skype для бизнеса Server 2019.
    
7. Щелкните **"Действие"** и выберите **"Переместить выбранных пользователей в пул".** Нажмите **ОК**.
  
8. Убедитесь,  что столбец пула регистратора для пользователя теперь содержит пул Skype для бизнеса Server 2019, который указывает, что пользователь успешно перемещен. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение пользователя с помощью оболочки управления Skype для бизнеса Server 2019

1. Откройте оболочку управления Skype для бизнеса Server.
    
2. В командной строке введите следующую команду: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Затем в командной строке введите следующую команду: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. Удостоверение **RegistrarPool** теперь указывает на пул Skype для бизнеса Server 2019. Наличие этого идентификатора подтверждает успешное перемещение пользователя. 

    > [!NOTE]
    > Для получения подробных сведений о cmdlet **Get-CsUser,** запустите: **Get-Help Get-CsUser -Detailed**
  

