---
title: Просмотр параметров конфигурации собрания в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Сводка: Узнайте, как для просмотра параметров конфигурации собрания в Скайп для Business Server 2015.'
ms.openlocfilehash: 382e50a0f41301953f4313c5019d1eb0d27804e5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Просмотр параметров конфигурации собрания в Skype для бизнеса Server 2015
 
**Сводка:** Узнайте, как для просмотра параметров конфигурации собрания в Скайп для Business Server 2015.
  
Можно просмотреть параметров конфигурации собрания с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Просмотр параметров конфигурации собрания с помощью Скайп для панели управления Business Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте Скайп для панели управления Business Server.
    
3. В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.
    
4. На странице **Конфигурация собрания** (Конфигурация собраний) щелкните конфигурацию собраний, которую требуется просмотреть.
    
5. В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.
    
    **Изменение конфигурации собрания - \<политики\> ** открывает Отображение параметров для выбранной политики.
    
    Подробные сведения о настройке параметров в разделе [Создание параметров конфигурации в Скайп для Business Server 2015 собрания](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Просмотр параметров конфигурации собрания с помощью Скайп для консоли Business Server
<a name="BKMK_ViewJoinSettings"> </a>

Для просмотра сведений обо всех параметрах конфигурации собраний выполните командлет **Get-CsMeetingConfiguration**:
  
```
Get-CsMeetingConfiguration
```

Эта команда возвращает информацию следующего вида:
  
```
Identity                        : Global
PstnCallersBypassLobby          : True
EnableAssignedConferenceType    : True
DesignateAsPresenter            : Company
AssignedConferenceTypeByDefault : True
AdmitAnonymousUsersByDefault    : True
RequireRoomSystemsAuthorization : False
LogoURL                         :
LegalURL                        :
HelpURL                         :
CustomFooterText                :
AllowConferenceRecording        : True

```

Дополнительные сведения, включая полный список параметров [Get-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)см.
  

