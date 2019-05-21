---
title: Управление политиками конференций в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Сводка: сведения о том, как управлять политиками конференций в Skype для бизнеса Server.'
ms.openlocfilehash: d835c4760ef3e77bc36f21e64cb80aeb618526ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289057"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a>Управление политиками конференций в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как управлять политиками конференций в Skype для бизнеса Server.
  
В этом разделе описывается, каким образом можно управлять политиками конференц-связи. Дополнительные сведения о планировании и развертывании конференций можно найти [в разделе Планирование конференций в Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и [развертывание конференций в Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Политика конференц-связи позволяет определить широкий спектр параметров расписания и участия, от возможности включения в собрание IP-аудио и видео, до максимального количества участников. Политики конференц-связи можно использовать для управления безопасностью, пропускной способностью и правовыми аспектами собраний.
  
Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя. Параметры применяются к конкретному пользователю от самой узкой до самой широкой области. Политика уровня пользователя имеет наивысший приоритет. Если политика не назначена, применяется политика уровня сайта. Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.
  
Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Управление политиками конференц-связи с помощью панели управления Skype для бизнеса Server

Чтобы управлять политиками конференц-связи с помощью панели управления Skype для бизнеса Server:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Управление политиками конференц-связи с помощью командной консоли Skype для бизнеса Server

Для управления собраниями с помощью командной консоли Skype для бизнеса Server используйте следующие командлеты:
  
**Параметры политики конференц-связи**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |Возвращает сведения о политиках проведения конференций, используемых в вашей организации.  <br/> |
|[Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |Назначает политику конференций на уровне пользователей.  <br/> |
|[New-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |Создает новую политику конференций в организации.  <br/> |
|[Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |Удаляет выбранную политику конференц-связи.  <br/> |
|[Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |Изменяет существующую политику конференц-связи.  <br/> |
   

