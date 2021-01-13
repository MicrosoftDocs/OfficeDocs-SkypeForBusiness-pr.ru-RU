---
title: Создание новой политики архива в Skype для бизнеса Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: Сводка. Узнайте, как создать новую политику архива для Skype для бизнеса Server.
ms.openlocfilehash: 3e1f538aba26025f5868a09babd3b67df36f9a3f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817649"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Создание новой политики архива в Skype для бизнеса Server

**Сводка:** Узнайте, как создать новую политику архива для Skype для бизнеса Server.
  
Новые политики архива можно создать с помощью панели управления или с помощью Windows PowerShell управления.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Создание новой политики архива с помощью панели управления

Чтобы создать новую политику архива с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **"Мониторинг** и архивации" и выберите "Политика **архивации".**
    
4. Нажмите кнопку **Создать**, а затем выполните одно из следующих действий: 
    
   - Чтобы создать политику архива на уровне сайта, щелкните "Политика сайта", а затем в области "Выбор сайта" выберите **сайт,** к которому должна применяться политика.
    
   - Чтобы создать политику архивации на уровне пользователя, щелкните **Политика пользователя**.
    
5. В разделе **Новая политика архивации** выполните следующие действия:
    
   - В разделе **Имя** укажите имя новой политики (например, externalContoso).
    
   - В разделе **Описание** приведены подробные сведения о том, что представляет собой политика (например, «Внешняя политика архивации на уровне пользователя для компании Contoso»).
    
   - Для управления архивацией операций обмена данными с внутренними пользователями установите или снимите флажок **Архивация внутренних коммуникаций**.
    
   - Для управления архивацией операций обмена данными с внешними пользователями установите или снимите флажок **Архивация внешних коммуникаций**.
    
6. Щелкните **Исполнить**.
    
    > [!IMPORTANT]
    > Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика. Дополнительные сведения см. в подмене политики [архива к пользователям Skype для бизнеса Server.](apply-a-policy-to-users.md) 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Создание новой политики архива с помощью Windows PowerShell

Вы также можете создать новые политики архива с помощью Windows PowerShell **New-CsArchivingPolicy.** Дополнительные сведения см. в разделе справки по [cmdlet New-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Создание новой политики архива на уровне сайта

Данная команда создает новую политику архивации для сайта Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Создание новой политики архива на уровне пользователя

Чтобы создать новую политику архива на уровне пользователя, просто укажите уникальное удостоверение при создании политики:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Создание новой политики архива, которая позволяет архивать сеансы внутренней связи

Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новые политики будут использовать значения по умолчанию для всех своих свойств. Чтобы создать политики, использующие другие значения свойств просто включите соответствующий параметр и его значение. Например, следующая команда создает политику архива, которая разрешает архивы внутренних сеансов обмена мгновенными сообщениями: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Создание новой политики архива, которая позволяет архивать как внутренние, так и внешние сеансы связи

Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, эта команда настраивает новую политику для архива внутренних и внешних сеансов обмена мгновенными сообщениями:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
