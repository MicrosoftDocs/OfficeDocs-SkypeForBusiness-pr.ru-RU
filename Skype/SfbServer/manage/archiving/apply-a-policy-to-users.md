---
title: Применение политики архивации для пользователей, Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Сводка: Узнайте, как назначение политики архивации для пользователей, Скайп для Business Server.'
ms.openlocfilehash: bc54c25a710e4e1cca44fb7311a47101f31ef7df
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985618"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Применение политики архивации для пользователей, Скайп для Business Server

**Сводка:** Узнайте, как назначение политики архивации для пользователей, Скайп для Business Server.
  
Если вы создали одну или несколько политик пользователей для архивации для пользователей, размещенных на Скайп для Business Server, вы можете реализовать поддержки архивации для конкретных пользователей путем применения соответствующих политик для этих пользователей или групп пользователей. Например если создать политику для поддержки архивации внутренних коммуникаций, можно применить их хотя бы одному пользователю или группе пользователей для поддержки архивации из Скайп пользователя для коммуникаций Business Server.
  
> [!NOTE]
> Если включена интеграция с Microsoft Exchange для вашего развертывания, управления политики хранения на месте Exchange ли архивации для пользователей, которые размещаются на сервере Exchange и установить их почтовые ящики на хранение на месте. Дополнительные сведения см [Планирование архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md) и [Настройка интеграции с хранилищем Exchange для Скайп для Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Применение политики пользователей с помощью панели управления

Чтобы применить политику пользователей с помощью панели управления, выполните следующие действия:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 
    
3. На панели навигации слева нажмите **Пользователи** и затем найдите учетную запись пользователя, которую необходимо настроить. 
    
4. В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.
    
5. В **Окне Изменение пользователя Lync Server** в поле **Политика архивация**выберите политику, которую нужно применить.
    
    > [!NOTE]
    > ** \<Автоматического\> ** параметры применяются параметры установки сервера по умолчанию. Данные параметры автоматически применяются сервером.
  
6. Нажмите **Исполнить**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Применение пользовательской политики с помощью Windows PowerShell

Также можно применить политику уровня пользователя с помощью командлета Windows PowerShell **Grant-CsArchivingPolicy** .
  
Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Эта команда назначает политику архивации на уровне пользователя RedmondArchivingPolicy всем пользователям, чьи учетные записи размещены в пуле регистраторов atl-cs-001.contoso.com. Для получения дополнительных сведений о параметр Filter, используемые в этой команде обратитесь к документации командлет [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Следующей командой удаляется любая политика архивации на уровне пользователей, ранее назначенная пользователю Ken Myer. После того как политика на уровне пользователей удалена, Ken Myer будет автоматически управляться с помощью глобальной политики или политики его локального сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Для получения дополнительных сведений обратитесь к документации командлета [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

