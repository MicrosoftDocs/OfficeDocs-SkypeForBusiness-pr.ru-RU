---
title: Применение политики архива к пользователям в Skype для бизнеса Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: Сводка. Узнайте, как назначить политику архива пользователям в Skype для бизнеса Server.
ms.openlocfilehash: 8dc74fcc8befe39b424b89c77aebca683fe17586
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817769"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Применение политики архива к пользователям в Skype для бизнеса Server

**Сводка:** Learn how to assign an archiving policy to users in Skype for Business Server.
  
If you have created one or more user policies for archiving for users homed on Skype for Business Server, you can implement archiving support for specific users by applying the appropriate policies to those users or user groups. Например, если вы создаете политику для поддержки архива внутренних коммуникаций, вы можете применить ее по крайней мере к одному пользователю или группе пользователей для поддержки архива взаимодействия skype для бизнеса Server пользователя.
  
> [!NOTE]
> Если для развертывания включена интеграция с Microsoft Exchange, политики удержания exchange In-Place контролируют, включена ли архивация для пользователей, которые размещены в Exchange и для их почтовых ящиков включено In-Place удержание. For details, [see Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Применение политики пользователя с помощью панели управления

Чтобы применить политику пользователя с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить. 
    
4. В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.
    
5. В **области "Изменение пользователя Lync Server"** в политике архива **выберите** политику пользователя архива, которую необходимо применить.
    
    > [!NOTE]
    > Параметры **\<Automatic\>** применяют параметры установки сервера по умолчанию. Данный параметр автоматически применяется сервером.
  
6. Нажмите кнопку **Сохранить**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Применение политики пользователя с помощью Windows PowerShell

Вы также можете применить политику пользователя с помощью Windows PowerShell **Grant-CsArchivingPolicy.**
  
Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Эта команда назначает политику архивизации на пользователя RedmondArchivingPolicy всем пользователям, у которых учетные записи в пуле регистратора atl-cs-001.contoso.com. Подробные сведения о параметре Filter, используемом в этой команде, см. в документации по командлету [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Следующая команда удаляет любую политику архива на пользователя, ранее назначенную пользователю Ken Myer. После удаления политики на уровне пользователя пользователем Ken Myer будет автоматически управляться с помощью глобальной политики или, если она существует, локальной политики сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Подробные сведения [см. в документации полету Grant-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps)
  

