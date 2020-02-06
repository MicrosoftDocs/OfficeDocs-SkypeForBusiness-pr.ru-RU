---
title: Управление параметрами конфигурации собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Сводка: сведения о том, как управлять параметрами конфигурации собраний в Skype для бизнеса Server.'
ms.openlocfilehash: cefdf304d8cf5ed6ff4560dd5416283d733c3db2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818530"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Управление параметрами конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как управлять параметрами конфигурации собраний в Skype для бизнеса Server.
  
В этом разделе рассматривается задание параметров конфигурации собраний. Дополнительные сведения о планировании и развертывании конференций можно найти [в разделе Планирование конференций в Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и [развертывание конференций в Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Параметры конфигурации собраний определяют тип собраний, которые могут создаваться пользователями, а также возможность и способ присоединения к собраниям анонимных пользователей и пользователей, подключающихся по телефонной линии. Обратите внимание, что эти параметры влияют только на запланированные собрания; они не влияют на нерегламентированные собрания, созданные с помощью команды "провести собрание" в Skype для бизнеса.
  
С помощью параметров конфигурации собраний задаются следующие характеристики:
  
- может ли пользователь, выполняющий вызов из ТСОП, переходить в зал;
    
- кто может быть докладчиком;
    
- назначается ли тип конференции по умолчанию;
    
- допускаются ли анонимные (непроверенные) пользователи по умолчанию.
    
Вы можете определить характеристики собраний с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server. 
  
Вы можете указать параметры собрания на глобальном уровне (создан по умолчанию), на уровне сайта или на уровне пула. По умолчанию взаимодействие с пользователями определяется глобальными параметрами. Параметры, заданные на уровне пула, применяются ко всем собраниям, размещенным в этом пуле. При отсутствии параметров уровня пула применяются параметры уровня сайта, если они заданы. Если на уровне сайта параметры также не заданы, ко всем собраниям применяются глобальные параметры.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Управление параметрами собраний с помощью панели управления Skype для бизнеса Server

Управление параметрами собраний с помощью панели управления Skype для бизнеса Server.
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Управление параметрами собраний с помощью командной консоли Skype для бизнеса Server

Для управления собраниями с помощью командной консоли Skype для бизнеса Server используйте следующие командлеты:
  
**Параметры конфигурации собрания**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Возвращение сведений о параметрах конфигурации собраний, действующих в организации на данный момент.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров конфигурации собраний.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Изменение параметров конфигурации собраний, действующих в организации на данный момент.  <br/> |
   

