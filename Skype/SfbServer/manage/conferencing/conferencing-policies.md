---
title: Управление политиками конференций в Skype для бизнеса Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: Сводка. Узнайте, как управлять политиками конференций в Skype для бизнеса Server.
ms.openlocfilehash: f2678c964cc56de44aff37d49aae5f3c61ebc298
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766627"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Управление политиками конференций в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять политиками conferencing в Skype для бизнеса Server.
  
В этом разделе описывается управление политиками конференций. Дополнительные сведения о планировании и развертывании конференций см. в Skype для бизнеса Server Plan [for conferencing in Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и Deploy [conferencing in Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Политики конференциации позволяют определить самые разнообразные варианты планирования и участия, начиная от того, может ли собрание включать ip-аудио и видео до максимального числа людей, которые могут присутствовать. Политики проведения собраний можно использовать для управления безопасностью, пропускной способностью и юридическими аспектами собраний.
  
Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя. Параметры применяются к конкретному пользователю от самой узкой до самой широкой области. Если назначить политику пользователю, эти параметры будут иметь приоритет. Если политика уровня пользователя не назначена, применяется политика уровня сайта. Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.
  
Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Управление политиками conferencing с помощью Skype для бизнеса Server панели управления

Управление политиками конференций с помощью Skype для бизнеса Server панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Управление политиками conferencing с помощью Skype для бизнеса Server Management Shell

Для управления собраниями с помощью Skype для бизнеса Server management Shell используйте следующие команды:
  
**Параметры политики conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках проведения конференций, используемых в вашей организации.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Назначает политику конференций на уровне пользователей.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Создает новую политику конференций в организации.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Удаляет указанную политику конференций.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Изменяет существующую политику конференции.  <br/> |
