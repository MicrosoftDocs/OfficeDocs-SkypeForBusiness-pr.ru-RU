---
title: Управление политиками конференциинга в Skype для бизнеса Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: Сводка. Узнайте, как управлять политиками конференций в Skype для бизнеса Server.
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099105"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Управление политиками конференциинга в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять политиками конференций в Skype для бизнеса Server.
  
В этом разделе описывается управление политиками конференций. Дополнительные сведения о планировании и развертывании конференций см. в веб-сведениях Plan [for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) и Deploy [conferencing in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Политики конференциации позволяют определить самые разнообразные варианты планирования и участия, начиная от того, может ли собрание включать ip-аудио и видео до максимального числа людей, которые могут присутствовать. Политики проведения собраний можно использовать для управления безопасностью, пропускной способностью и юридическими аспектами собраний.
  
Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя. Параметры применяются к конкретному пользователю от самой узкой до самой широкой области. Если назначить политику пользователю, эти параметры будут иметь приоритет. Если политика уровня пользователя не назначена, применяется политика уровня сайта. Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.
  
Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Управление политиками конференций с помощью панели управления Skype для бизнес-серверов

Управление политиками конференций с помощью панели управления Skype для бизнес-серверов:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнес-серверов.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Управление политиками конференциинга с помощью оболочки управления Skype для бизнес-серверов

Для управления собраниями с помощью skype for Business Server Management Shell используйте следующие команды:
  
**Параметры политики conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingPolicy](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках проведения конференций, используемых в вашей организации.  <br/> |
|[Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Назначает политику конференций на уровне пользователей.  <br/> |
|[New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Создает новую политику конференций в организации.  <br/> |
|[Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Удаляет указанную политику конференций.  <br/> |
|[Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Изменяет существующую политику конференции.  <br/> |
