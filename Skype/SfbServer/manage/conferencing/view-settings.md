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
ms.localizationpriority: medium
ms.assetid: 932c7e2d-6de3-4176-ac6e-ec230f8230f2
description: Сводка. Сведения о просмотре параметров конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: 79a05b35d5bdac952d009445b92c9f1b30883027
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578823"
---
# <a name="view-meeting-configuration-settings-in-skype-for-business-server"></a>Просмотр параметров конфигурации собраний в Skype для бизнеса Server
 
**Сводка:** Узнайте, как просматривать параметры конфигурации собраний в Skype для бизнеса Server.
  
Параметры конфигурации собраний можно просмотреть с Skype для бизнеса Server панели управления или с помощью Skype для бизнеса Server management Shell.
  
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Просмотр параметров конфигурации собраний с помощью Skype для бизнеса Server панели управления
<a name="BKMK_ViewJoinSettings"> </a>

1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.
    
2.  Откройте панель Skype для бизнеса Server управления.
    
3. В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Конфигурация собраний**.
    
4. На странице **Meeting Configuration** (Конфигурация собраний) щелкните конфигурацию собраний, которую вы хотите просмотреть.
    
5. В **фильтре редактирования файла** выберите поле **"Сведения** о шоу".
    
    **Изменение конфигурации \<policy\> собраний —** открывает отображение параметров выбранной политики.
    
    Дополнительные сведения о настройке параметров см. в материале [Create meeting configuration settings in Skype для бизнеса Server.](create-settings.md)
    
## <a name="view-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Просмотр параметров конфигурации собраний с помощью Skype для бизнеса Server management Shell
<a name="BKMK_ViewJoinSettings"> </a>

Чтобы просмотреть сведения обо всех параметрах конфигурации собраний, используйте комлет **Get-CsMeetingConfiguration:**
  
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

Дополнительные сведения, включая полный список параметров, см. в [списке Get-CsMeetingConfiguration.](/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps)
