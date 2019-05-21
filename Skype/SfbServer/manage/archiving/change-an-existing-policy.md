---
title: Изменение существующей политики архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 'Сводка: сведения о том, как изменить политики архивации пользователей в Skype для бизнеса Server.'
ms.openlocfilehash: 4a3da0bfe403d1a00807865cd07762111b59b540
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282023"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>Изменение существующей политики архивации в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как изменить политики архивации пользователей в Skype для бизнеса Server.
  
При первом развертывании сервера Skype для бизнеса вы настраиваете начальные политики архивации, определяющие способ реализации архивации для пользователей в вашем развертывании. В этом разделе описываются способы управления политиками и их изменения. 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>Изменение политик архивации с помощью панели управления

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
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
    > Параметры политики пользователя применяются только к тем пользователям и группам пользователей, к которым применяется политика. Подробнее смотрите в разделе [применение политики архивации для пользователей в Skype для бизнеса Server](apply-a-policy-to-users.md). 
  
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

Чтобы включить архивацию внутренних и внешних сеансов связи, установите для параметров Арчивеинтернал и Арчивикстернал значение true: 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>Отключение политик архивации

Чтобы полностью отключить архивацию, присвойте параметрам ArchiveInternal и ArchiveExternal значение False ($False): 
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
