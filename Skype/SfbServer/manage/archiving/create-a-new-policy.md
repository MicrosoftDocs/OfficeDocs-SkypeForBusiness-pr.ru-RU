---
title: Создание новой политики архива в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: Сводка. Узнайте, как создать новую политику архива для Skype для бизнеса Server.
ms.openlocfilehash: d60ca9399681bf44fadcf7767b7be1499e99cb99
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836451"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>Создание новой политики архива в Skype для бизнеса Server

**Сводка:** Узнайте, как создать новую политику архива для Skype для бизнеса Server.
  
Вы можете создать новые политики архива с помощью панели управления или с помощью Windows PowerShell-кодлетов.
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>Создание новой политики архива с помощью панели управления

Создание новой политики архива с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните **Мониторинг** и архивации, а затем нажмите кнопку **Политика архивации**.
    
4. Нажмите кнопку **Создать**, а затем выполните одно из следующих действий: 
    
   - Чтобы создать политику архива на уровне сайта, щелкните политику сайта **и** нажмите кнопку Выберите **сайт,** щелкните сайт, на который должна применяться политика.
    
   - Чтобы создать политику архивации на уровне пользователя, щелкните **Политика пользователя**.
    
5. В разделе **Новая политика архивации** выполните следующие действия:
    
   - В разделе **Имя** укажите имя новой политики (например, externalContoso).
    
   - В разделе **Описание** приведены подробные сведения о том, что представляет собой политика (например, «Внешняя политика архивации на уровне пользователя для компании Contoso»).
    
   - Для управления архивацией операций обмена данными с внутренними пользователями установите или снимите флажок **Архивация внутренних коммуникаций**.
    
   - Для управления архивацией операций обмена данными с внешними пользователями установите или снимите флажок **Архивация внешних коммуникаций**.
    
6. Щелкните **Исполнить**.
    
    > [!IMPORTANT]
    > Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика. Дополнительные сведения [см. в материале Apply an archiving policy to users in Skype для бизнеса Server.](apply-a-policy-to-users.md) 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>Создайте новую политику архива с помощью Windows PowerShell

Вы также можете создать новые политики архива с помощью **Windows PowerShell-код New-CsArchivingPolicy.** Дополнительные сведения см. в разделе Справка для [cmdlet New-CsArchivingPolicy.](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>Создание новой политики архива на уровне сайта

Данная команда создает новую политику архивации для сайта Redmond:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>Создание новой политики архива на уровне каждого пользователя

Чтобы создать новую политику архива на уровне каждого пользователя, просто укажите уникальное удостоверение при создании политики:
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>Создание новой политики архива, которая позволяет архивать внутренние сеансы связи

Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новые политики будут использовать значения по умолчанию для всех своих свойств. Чтобы создать политики, использующие другие значения свойств просто включите соответствующий параметр и его значение. Например, следующая команда создает политику архива, которая позволяет архивовать внутренние сеансы обмена мгновенными сообщениями: 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>Создание новой политики архива, которая позволяет архивать внутренние и внешние сеансы связи

Чтобы изменить несколько значений свойств, можно включить несколько параметров. Например, эта команда настраивает новую политику для архива внутренних и внешних сеансов обмена мгновенными сообщениями:
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```