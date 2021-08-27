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
ms.localizationpriority: medium
description: Вы можете переместить пользователя из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 г., используя панель управления Skype для бизнеса Server 2019 или Skype для бизнеса Server 2019. В приведенной ниже статье в столбце пула регистратора pool01.contoso.net является устаревшим пулом, и все шесть из этих пользователей подключены к этому пулу. Используйте следующие процедуры для перемещения пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и Skype для бизнеса Server Management Shell.
ms.openlocfilehash: 987eeec96d28257b995b5e27ce02e282df019980
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596163"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Перемещение одного пользователя в пилотный пул

Вы можете переместить пользователя из устаревшего пула в пилотный пул Skype для бизнеса Server 2019 г., используя панель управления Skype для бизнеса Server 2019 или Skype для бизнеса Server 2019. В приведенной ниже  статье в столбце пула регистратора pool01.contoso.net является устаревшим пулом, и все шесть из этих пользователей подключены к этому пулу.  Используйте следующие процедуры для перемещения пользователя в пул Skype для бизнеса Server 2019 с помощью панели управления Skype для бизнеса Server 2019 и Skype для бизнеса Server Management Shell. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Перемещение пользователя с помощью панели управления Skype для бизнеса Server 2019 г.
  
1. Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.
    
2. Откройте **панель Skype для бизнеса Server управления**.
    
3. Щелкните **Пользователи,** **щелкните Поиск,** а затем нажмите **кнопку Найти**.
    
4. Выберите пользователя, который должен перейти в пул Skype для бизнеса Server 2019 г. В данном примере мы перемещаем пользователя с именем Sara Davis.
    
5. В меню **Действие** выберите команду **Переместить выбранных пользователей в пул**.
    
6. Из выпадаемого списка выберите пул Skype для бизнеса Server 2019 г.
    
7. Щелкните **Действие,** а затем **нажмите кнопку Переместить выбранных пользователей для пула**. Нажмите кнопку **ОК**.
  
8. Убедитесь,  что столбец пула регистратора для пользователя теперь содержит пул Skype для бизнеса Server 2019, что указывает на успешное перемещение пользователя. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Перемещение пользователя с помощью Skype для бизнеса Server 2019

1. Откройте оболочку Skype для бизнеса Server управления.
    
2. В командной строке введите следующую команду: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Затем в командной строке введите следующую команду: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. Идентификатор **RegistrarPool** теперь указывает на Skype для бизнеса Server 2019 года. Наличие этого идентификатора подтверждает успешное перемещение пользователя. 

    > [!NOTE]
    > Для получения сведений о **комлете Get-CsUser** запустите: **Get-Help Get-CsUser-Detailed**
  

