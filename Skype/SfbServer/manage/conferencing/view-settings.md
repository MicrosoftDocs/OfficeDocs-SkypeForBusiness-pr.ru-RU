---
title: Просмотр параметров конфигурации собраний в Skype для бизнеса Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: 'Сводка: сведения о том, как просматривать параметры конфигурации собрания в Skype для бизнеса Server.'
ms.openlocfilehash: 858d1a3d786cb9fe3c6b33daaca8667cab2390f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818460"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Просмотр параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Сведения о том, как просматривать параметры конфигурации собрания в Skype для бизнеса Server.
  
Параметры конфигурации собраний можно просматривать с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Просмотр параметров конфигурации собрания с помощью панели управления Skype для бизнеса Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.
    
4. На странице **Конфигурация собрания** (Конфигурация собраний) щелкните конфигурацию собраний, которую требуется просмотреть.
    
5. В окне **Изменение фильтра файлов** установите флажок **Показать подробности**.
    
    Диалоговое окно " ** \<изменение\> конфигурации собрания** ", в котором отображаются параметры выбранной политики.
    
    Дополнительные сведения о настройке параметров можно найти [в разделе Создание параметров конфигурации собраний в Skype для бизнеса Server](create-settings.md).
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Просмотр параметров конфигурации собрания с помощью командной консоли Skype для бизнеса Server
<a name="BKMK_ViewJoinSettings"> </a>

Для просмотра сведений обо всех параметрах конфигурации собраний выполните командлет **Get-CsMeetingConfiguration**:
  
```
Get-CsMeetingConfiguration
```

Эта команда возвращает информацию следующего вида:
  
<pre>
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
</pre>

Дополнительные сведения, включая полный список параметров, можно найти в [статьях Get-ксмитингконфигуратион](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps).
  

