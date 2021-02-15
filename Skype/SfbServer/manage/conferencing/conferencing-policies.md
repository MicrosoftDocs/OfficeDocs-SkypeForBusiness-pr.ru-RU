---
title: Управление политиками conferencing в Skype для бизнеса Server
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
description: Сводка. Узнайте, как управлять политиками в Skype для бизнеса Server.
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835279"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Управление политиками conferencing в Skype для бизнеса Server
 
**Сводка:** Learn how to manage conferencing policies in Skype for Business Server.
  
В этом разделе описывается управление политиками conferencing. Дополнительные сведения о планировании и развертывании conferencing см. в дополнительных сведениях о планировании и развертывании [conferencing](../../plan-your-deployment/conferencing/conferencing.md) в Skype для бизнеса [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Политики проведения собраний позволяют определить широкий спектр параметров планирования и участия, начиная с того, может ли собрание включать IP-аудио- и видеосвязь, до максимального количества участников. Политики проведения собраний можно использовать для управления безопасностью, пропускной способностью и юридическими аспектами собраний.
  
Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя. Параметры применяются к конкретному пользователю от самой узкой до самой широкой области. При назначении политики пользователю эти параметры имеют приоритет. Если политика уровня пользователя не назначена, применяется политика уровня сайта. Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.
  
Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Manage conferencing policies by using Skype for Business Server Control Panel

To manage conferencing policies by using Skype for Business Server Control Panel:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing" (Conferencing),** а затем выберите **"Conferencing Policy" (Политика).**
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Manage conferencing policies by using Skype for Business Server Management Shell

Для управления собраниями с помощью skype for Business Server Management Shell используйте следующие команды:
  
**Параметры политики conferencing**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках проведения конференций, используемых в вашей организации.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Назначает политику конференций на уровне пользователей.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Создает новую политику конференций в организации.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Удаляет указанную политику.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Изменяет существующую политику conferencing.  <br/> |
   

