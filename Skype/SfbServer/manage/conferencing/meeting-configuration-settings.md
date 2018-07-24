---
title: Управление параметров конфигурации собрания в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Сводка: Сведения об управлении параметров конфигурации собрания в Скайп для Business Server.'
ms.openlocfilehash: 28f0dc37579f762b8ae3b0ac8ac58440c6ce5e24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966068"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Управление параметров конфигурации собрания в Скайп для Business Server
 
**Сводка:** Сведения об управлении параметров конфигурации собрания в Скайп для Business Server.
  
В этом разделе рассматривается задание параметров конфигурации собраний. Дополнительные сведения о планировании и развертывании конференц-связи видеть [план для конференц-связи в Скайп для Business Server](../../plan-your-deployment/conferencing/conferencing.md) и [Развертывание конференц-связи в Скайп для Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Параметры конфигурации собраний определяют тип собраний, которые могут создаваться пользователями, а также возможность и способ присоединения к собраниям анонимных пользователей и пользователей, подключающихся по телефонной линии. Обратите внимание на то, что эти параметры влияют только на запланированные собрания; они не влияют на незапланированных собраний, нажав кнопку «провести собрание» в Скайп для бизнеса.
  
С помощью параметров конфигурации собраний задаются следующие характеристики:
  
- может ли пользователь, выполняющий вызов из ТСОП, переходить в зал;
    
- кто может быть докладчиком;
    
- назначается ли тип конференции по умолчанию;
    
- допускаются ли анонимные (непроверенные) пользователи по умолчанию.
    
Вы можете определить характеристики собраний с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server. 
  
Можно указать собрания параметры на глобальном уровне (создаваться по умолчанию), веб-сайтов уровне или уровне пула. По умолчанию взаимодействие с пользователями определяется глобальными параметрами. Параметры, заданные на уровне пула, применяются ко всем собраниям, размещенным в этом пуле. При отсутствии параметров уровня пула применяются параметры уровня сайта, если они заданы. Если на уровне сайта параметры также не заданы, ко всем собраниям применяются глобальные параметры.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Управление параметрами собрания с помощью Скайп для панели управления Business Server

Для управления параметрами собрания с помощью Скайп для панели управления Business Server:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Управление параметрами собрания с помощью Скайп для консоли Business Server

Для управления встречами с помощью Скайп для консоли Business Server, используйте следующие командлеты:
  
**Параметры конфигурации собрания**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации собраний, в настоящее время используемых в организации.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию параметров конфигурации собраний на уровне сайта или службы.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров конфигурации собраний.  <br/> |
|[SET-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Изменение параметров конфигурации собраний, действующих в организации на данный момент.  <br/> |
   

