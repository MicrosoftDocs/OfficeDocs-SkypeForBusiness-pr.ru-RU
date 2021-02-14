---
title: Управление настройками собраний в Skype для бизнеса Server
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
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: Сводка. Сведения об управлении настройками конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828089"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a>Управление настройками собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как управлять настройками конфигурации собраний в Skype для бизнеса Server.
  
В этом разделе описывается, как управлять настройками конфигурации собраний. Дополнительные сведения о планировании и развертывании [conferencing](../../plan-your-deployment/conferencing/conferencing.md) см. в дополнительных сведениях о планировании и развертывании в Skype для бизнеса [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
  
Параметры конфигурации собраний определяют тип собраний, которые могут создавать пользователи, в дополнение к управлению тем, как анонимные пользователи и пользователи с телефонным доступом могут присоединяться к этим собраниям (или даже могут ли они присоединяться). Обратите внимание, что эти параметры влияют только на запланированные собрания; Они не влияют на нечеткие собрания, созданные с помощью параметра "Выполнить собрание" в Skype для бизнеса.
  
Параметры конфигурации собраний определяют следующее:
  
- попадают ли пользователи, подключающиеся из ТСОП, в зал ожидания;
    
- кто может провести презентацию;
    
- назначается ли тип конференции по умолчанию;
    
- допускаются ли анонимные (непроверенные) пользователи по умолчанию.
    
Характеристики собраний можно определить с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell. 
  
Параметры собраний можно указать на глобальном уровне (по умолчанию создается), на уровне сайта или на уровне пула. По умолчанию глобальные параметры определяют процесс проведения собрания. При создании параметров уровня пула эти параметры применяются ко всем собраниям, размещенным в этом пуле. В отсутствие параметров уровня пула применяются параметры уровня сайта (при наличии). Если параметры уровня сайта также не заданы, ко всем собраниям применяются глобальные параметры.
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a>Управление настройками собраний с помощью панели управления Skype для бизнеса Server

Для управления настройками собраний с помощью панели управления Skype для бизнеса Server:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a>Управление настройками собраний с помощью оболочки управления Skype для бизнеса Server

Для управления собраниями с помощью skype for Business Server Management Shell используйте следующие команды:
  
**Параметры конфигурации собрания**

|**Командлет**|**Описание**|
|:-----|:-----|
|[Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |Возвращает сведения о параметрах конфигурации собраний, которые в настоящее время используются в организации.  <br/> |
|[New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы.  <br/> |
|[Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |Удаляет существующую коллекцию параметров конфигурации собраний.  <br/> |
|[Set-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |Изменяет параметры конфигурации собраний, которые в настоящее время используются в организации.  <br/> |
   

