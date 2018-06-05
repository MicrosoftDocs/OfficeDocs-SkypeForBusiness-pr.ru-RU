---
title: Изменение существующей политики архивации в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Сводка: Узнайте, как для изменения политик архивации для Скайп для Business Server 2015 пользователя.'
ms.openlocfilehash: 21774eaff8b58c585b347e1f657aa7afcc3b6106
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569409"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server-2015"></a>Изменение существующей политики архивации в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как для изменения политик архивации для Скайп для Business Server 2015 пользователя.
  
При первом развертывании Скайп для Business Server 2015, Настройка начальной политик архивации, определяющие способ реализации архивации для пользователей в развертывании. В этом разделе описываются способы управления политиками и их изменения. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Изменение политик архивации с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Политика архивации**.
    
4. В списке политик выполните одно из следующих действий: 
    
   - Чтобы изменить политику для всего развертывания, в списке политик щелкните **Global** (Глобальная), щелкните **Edit** (Изменить), а затем — **Show details** (Показать сведения).
    
   - Чтобы изменить политику для одного сайта, выберите имя сайта в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).
    
   - Чтобы изменить политику для отдельного пользователя или группы пользователей, выберите имя пользователя или группы пользователей в списке политик, щелкните **Edit** (Изменить) и затем щелкните **Show details** (Показать сведения).
    
5. На странице **Edit Archiving Policy** (Изменение политики архивации) выполните следующие действия:
    
   - Чтобы включить или отключить архивацию внутренних коммуникаций, установите или снимите флажок **Archive internal communications** (Архивировать внутренние коммуникации).
    
   - Чтобы включить или отключить архивацию внешних коммуникаций, установите или снимите флажок **Archive external communications** (Архивировать внешние коммуникации).
    
6. Нажмите **Исполнить**.
    
    > [!IMPORTANT]
    > Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика. Дополнительные сведения см [Применить политики архивации для пользователей, Скайп для Business Server 2015](apply-a-policy-to-users.md). 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>Изменение политик архивации с помощью Windows PowerShell

Политики архивации можно изменить, используя командлет Windows PowerShell **Set-CsArchivingPolicy**.
  
### <a name="enable-archiving-policies"></a>Включение политик архивации

Чтобы включить архивацию внутренних сеансов связи, присвойте параметру ArchiveInternal значение True ($True): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

Чтобы включить архивацию внешних сеансов связи, присвойте параметру ArchiveExternal значение True ($True): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

Чтобы включить архивацию сеансов внутренней и внешней связи, задайте значение параметра свойствам ArchiveInternal и ArchiveExternal значение True: 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Отключение политик архивации

Чтобы полностью отключить архивацию, присвойте параметрам ArchiveInternal и ArchiveExternal значение False ($False): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```