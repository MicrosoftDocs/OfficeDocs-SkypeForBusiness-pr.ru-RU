---
title: Просмотр параметров конфигурации собраний в Skype для бизнеса Server
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
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: Сводка. Сведения о просмотре параметров конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: e30543c566775d38e20e2103c4cc0f41278c1020
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827929"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Просмотр параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как просматривать параметры конфигурации собраний в Skype для бизнеса Server.
  
Параметры конфигурации собраний можно просмотреть с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Просмотр параметров конфигурации собраний с помощью панели управления Skype для бизнеса Server
<a name="BKMK_ViewJoinSettings"> </a>

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель управления Skype для бизнеса Server.
    
3. В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**
    
4. На странице **Meeting Configuration** (Конфигурация собраний) щелкните конфигурацию собраний, которую вы хотите просмотреть.
    
5. В **фильтре "Изменить файл"** выберите **"Показать сведения".**
    
    **Изменение конфигурации \<policy\> собрания -** открывает отображение параметров выбранной политики.
    
    Дополнительные сведения о настройке параметров см. в дополнительных сведениях о создании параметров конфигурации собраний [в Skype для бизнеса Server.](create-settings.md)
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Просмотр параметров конфигурации собраний с помощью skype для бизнеса Server Management Shell
<a name="BKMK_ViewJoinSettings"> </a>

Чтобы просмотреть сведения обо всех параметрах конфигурации собраний, используйте **cmdlet Get-CsMeetingConfiguration:**
  
```
Get-CsMeetingConfiguration
```

Эта команда возвращает сведения, похожие на следующие:
  
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

Дополнительные сведения, включая полный список параметров, см. в подстроке [Get-CsMeetingConfiguration.](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)
  

