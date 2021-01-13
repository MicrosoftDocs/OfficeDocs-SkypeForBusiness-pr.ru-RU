---
title: Изменение существующей политики архива в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: Сводка. Узнайте, как изменить политики архива для Skype для бизнеса Server.
ms.openlocfilehash: 47c9d5938c22b93db48c96265831cbf24ecc24d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817709"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Изменение существующей политики архива в Skype для бизнеса Server
 
**Сводка:** Learn how to change user archiving policies for Skype for Business Server.
  
При первом развертывании Skype для бизнеса Server необходимо настроить начальные политики архивации, определяющие реализации архивации для пользователей в развертывании. В этом разделе описывается, как управлять политиками и изменять их. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Изменение политик архива с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **"Мониторинг** и архивации" и выберите "Политика **архивации".**
    
4. В списке политик выполните одно из следующих действий: 
    
   - Чтобы изменить политику для всего развертывания, в списке политик щелкните **Global** (Глобальная), щелкните **Edit** (Изменить), а затем — **Show details** (Показать сведения).
    
   - Чтобы изменить политику для одного сайта, выберите имя сайта в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).
    
   - Чтобы изменить политику для отдельного пользователя или группы пользователей, выберите имя пользователя или группы пользователей в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).
    
5. На странице **Edit Archiving Policy** (Изменение политики архивации) выполните следующие действия:
    
   - Чтобы включить или отключить архивацию внутренних коммуникаций, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).
    
   - Чтобы включить или отключить архивацию внешних коммуникаций, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).
    
6. Щелкните **Commit** (Применить).
    
    > [!IMPORTANT]
    > Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика. Дополнительные сведения см. в сведениях о применении политики [архива к пользователям в Skype для бизнеса Server.](apply-a-policy-to-users.md) 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Изменение политик архива с помощью Windows PowerShell

Вы также можете изменить политики архива с помощью Windows PowerShell **Set-CsArchivingPolicy.**
  
### <a name="enable-archiving-policies"></a>Включить политики архива

Чтобы включить архивировать внутренние сеансы связи, установите для параметра ArchiveInternal значение True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Чтобы включить архивировать внешние сеансы связи, установите для параметра ArchiveExternal значение True ($True): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Чтобы включить архивировать как внутренние, так и внешние сеансы связи, установите для параметров ArchiveInternal и ArchiveExternal значение True: 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Отключение политик архива

Чтобы полностью отключить архивации, установите для параметров ArchiveInternal и ArchiveExternal значение False ($False): 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
