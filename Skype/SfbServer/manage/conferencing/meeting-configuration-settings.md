---
title: Управление настройками собраний в Skype для бизнеса Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: Сводка. Узнайте, как управлять настройками конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: ccbb1a43364ddd5507fb01c59000397130a9c22e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832103"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Управление настройками собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять настройками собраний в Skype для бизнеса Server.
  
В этом разделе описывается управление настройками конфигурации собраний. Дополнительные сведения о планировании и развертывании конференций см. в Skype для бизнеса Server Plan [for conferencing in Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и Deploy [conferencing in Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
  
Параметры конфигурации собраний диктуют тип собраний, которые пользователи могут создавать, в дополнение к контролю того, как (или даже если) анонимные пользователи и пользователи телефонных собраний могут присоединяться к этим собраниям. Обратите внимание, что эти параметры влияют только на запланированные собрания; они не влияют на собрания, созданные путем нажатия параметра Meet Now в Skype для бизнеса.
  
Параметры конфигурации собраний определяют следующее:
  
- попадают ли пользователи, подключающиеся из ТСОП, в зал ожидания;
    
- кто может провести презентацию;
    
- назначается ли тип конференции по умолчанию;
    
- допускаются ли анонимные (непроверенные) пользователи по умолчанию.
    
Характеристики собраний можно определить с помощью Skype для бизнеса Server панели управления или с помощью Skype для бизнеса Server управленческой оболочки. 
  
Можно указать параметры собраний на глобальном уровне (созданном по умолчанию), уровне сайта или уровне пула. По умолчанию глобальные параметры определяют процесс собрания. При создании параметров уровня пула эти параметры применяются ко всем собраниям, размещенным в этом пуле. В отсутствие параметров уровня пула применяются параметры уровня сайта (при наличии). Если параметры уровня сайта также не заданы, ко всем собраниям применяются глобальные параметры.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Управление настройками собраний с помощью Skype для бизнеса Server панели управления

Управление настройками собраний с помощью Skype для бизнеса Server панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Управление настройками собраний с помощью Skype для бизнеса Server управленческой оболочки

Для управления собраниями с помощью Skype для бизнеса Server management Shell используйте следующие команды:
  
**Параметры конфигурации собрания**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации собраний, которые в настоящее время используются в организации.  <br/> |
|[New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы.  <br/> |
|[Remove-CsMeetingConfiguration](/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров конфигурации собраний.  <br/> |
|[Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Изменяет параметры конфигурации собраний, которые в настоящее время используются в организации.  <br/> |
