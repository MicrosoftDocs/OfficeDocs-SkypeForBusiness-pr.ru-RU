---
title: Применение политики архива для пользователей в Skype для бизнеса Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: Сводка. Узнайте, как назначить политику архива пользователям в Skype для бизнеса Server.
ms.openlocfilehash: fadc2d20ce8fb83ef331feb55f5d0908b3189213
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391191"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Применение политики архива для пользователей в Skype для бизнеса Server

**Сводка:** Узнайте, как назначить политику архива пользователям в Skype для бизнеса Server.
  
Если вы создали одну или несколько политик для архива для пользователей, Skype для бизнеса Server, вы можете реализовать поддержку архива для определенных пользователей, применяя соответствующие политики к этим пользователям или группам пользователей. Например, если создается политика для поддержки архива внутренних коммуникаций, ее можно применить по крайней мере к одному пользователю или группе пользователей для поддержки архива Skype для бизнеса Server сообщений пользователя.
  
> [!NOTE]
> Если вы включили интеграцию microsoft Exchange для развертывания, политики Exchange In-Place Hold контролируют, включена ли архивация для пользователей, которые размещены в Exchange, и чтобы их почтовые ящики были In-Place Hold. Подробные сведения см. в материале [Plan for archiving in Skype для бизнеса Server](../../plan-your-deployment/archiving/archiving.md) [и Configure integration with Exchange для Skype для бизнеса Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Применение политики пользователя с помощью панели управления

Применение политики пользователя с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить. 
    
4. В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.
    
5. В **статье Изменить пользователя Lync Server в** соответствии с политикой архивного архива **выберите политику** архива, которую необходимо применить.
    
    > [!NOTE]
    > Параметры **\<Automatic\>** применяют параметры установки сервера по умолчанию. Данный параметр автоматически применяется сервером.
  
6. Нажмите кнопку **Сохранить**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Применение политики пользователя с помощью Windows PowerShell

Можно также применить политику пользователя с помощью Windows PowerShell **Grant-CsArchivingPolicy**.
  
Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Эта команда назначает политику архивизации для каждого пользователя RedmondArchivingPolicy всем пользователям, у которых учетные записи в пуле регистраторов atl-cs-001.contoso.com. Сведения о параметре Filter, используемом в этой команде, см. в документации по командлету [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) .
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Следующая команда удаляет любую политику архива для каждого пользователя, ранее назначенную Кену Myer. После удаления политики для каждого пользователя управление политикой для каждого пользователя будет автоматически управляться с помощью глобальной политики или, если она существует, его локальной политики сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Подробные сведения см. в документации по [cmdlet Grant-CsArchivingPolicy](/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
