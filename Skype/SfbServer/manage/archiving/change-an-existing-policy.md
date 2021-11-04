---
title: Измените существующую политику архива в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: Сводка. Сведения об изменении политик архива пользователей для Skype для бизнеса Server.
ms.openlocfilehash: 555a8822ddf563b8ddce88ed94d56f153c93c795
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767963"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Измените существующую политику архива в Skype для бизнеса Server
 
**Сводка:** Узнайте, как изменить политики архива пользователей для Skype для бизнеса Server.
  
При первом развертывании Skype для бизнеса Server настройка политик начального архивации, определяющих реализацию архивации для пользователей в развертывании. В этом разделе описывается, как управлять политиками и изменять их. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Изменение политик архива с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните **Мониторинг** и архивации, а затем нажмите кнопку **Политика архивации**.
    
4. В списке политик выполните одно из следующих действий: 
    
   - Чтобы изменить политику для всего развертывания, в списке политик щелкните **Global** (Глобальная), щелкните **Edit** (Изменить), а затем — **Show details** (Показать сведения).
    
   - Чтобы изменить политику для одного сайта, выберите имя сайта в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).
    
   - Чтобы изменить политику для отдельного пользователя или группы пользователей, выберите имя пользователя или группы пользователей в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).
    
5. На странице **Edit Archiving Policy** (Изменение политики архивации) выполните следующие действия:
    
   - Чтобы включить или отключить архивацию внутренних коммуникаций, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).
    
   - Чтобы включить или отключить архивацию внешних коммуникаций, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).
    
6. Щелкните **Commit** (Применить).
    
    > [!IMPORTANT]
    > Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика. Дополнительные сведения [см. в материале Apply an archiving policy to users in Skype для бизнеса Server.](apply-a-policy-to-users.md) 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Изменение политик архива с помощью Windows PowerShell

Вы также можете изменить политики архива с помощью Windows PowerShell **set-CsArchivingPolicy.**
  
### <a name="enable-archiving-policies"></a>Включить политики архива

Чтобы включить архивации внутренних сеансов связи, установите значение параметра ArchiveInternal true ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Чтобы включить архивировать внешние сеансы связи, установите значение параметра ArchiveExternal true ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Чтобы включить архивации внутренних и внешних сеансов связи, установите значение параметров ArchiveInternal и ArchiveExternal значение True: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Отключение политик архива

Чтобы полностью отключить архивации, установите значение параметров ArchiveInternal и ArchiveExternal false ($False): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
