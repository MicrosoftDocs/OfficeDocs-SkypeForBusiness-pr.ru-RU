---
title: Изменение параметров конфигурации собрания в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 'Сводка: Узнайте, как для изменения параметров конфигурации собрания в Скайп для Business Server.'
ms.openlocfilehash: b4b8307711fcf7b120c867debe5ab3e2978f6ef7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978969"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>Изменение параметров конфигурации собрания в Скайп для Business Server
 
**Сводка:** Узнайте, как для изменения параметров конфигурации собрания в Скайп для Business Server.
  
Вы можете изменить параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Изменение параметров конфигурации собрания с помощью Скайп для панели управления Business Server

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.
    
4. В списке конфигураций собрания выберите конфигурацию, которую необходимо изменить, щелкните **Изменить**, а затем выберите **Показать подробности**.
    
5. В области **Изменение конфигурации собрания** можно изменить любые параметры конфигурации, за исключением имени конфигурации, которое не подлежит изменению.
    
6. Нажмите **Исполнить**.
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Изменение параметров конфигурации собрания с помощью Скайп для консоли Business Server

Для изменения параметров конфигурации собрания используется командлет **Set-CsMeetingConfiguration**.
  
Приведенная в примере ниже команда изменяет назначенные сайту Redmond (-Identity site:Redmond) параметры конфигурации собраний. В данном случае свойству DesignateAsPresenter задается значение Everyone.
  
```
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Дополнительные сведения, включая полный список параметров [Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)см.
  

