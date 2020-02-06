---
title: Применение к пользователям политики архивации в Skype для бизнеса Server
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
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 'Сводка: сведения о назначении политики архивации пользователям в Skype для бизнеса Server.'
ms.openlocfilehash: 7be62aaf5b2b70108cb67a36559b242377d26117
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819011"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>Применение к пользователям политики архивации в Skype для бизнеса Server

**Сводка:** Сведения о назначении пользователям политики архивации в Skype для бизнеса Server.
  
Если вы создали одну или несколько политик пользователей для архивации для пользователей, размещенных на сервере Skype для бизнеса Server, вы можете реализовать поддержку архивации для определенных пользователей, применяя соответствующие политики к этим пользователям или группам пользователей. Например, если вы создаете политику для поддержки архивации внутренних данных, вы можете применить ее по крайней мере к одному пользователю или группе пользователей для поддержки архивации данных пользователя в Skype для бизнеса Server.
  
> [!NOTE]
> Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange, и почтовые ящики, которые помещаются на хранение на месте. Подробности можно найти [в разделе Планирование архивации в Skype для бизнеса Server](../../plan-your-deployment/archiving/archiving.md) и [Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>Применение политики пользователей с помощью панели управления

Чтобы применить политику пользователей с помощью панели управления, выполните следующие действия:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. На панели навигации слева нажмите **Пользователи** и затем найдите учетную запись пользователя, которую необходимо настроить. 
    
4. В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.
    
5. В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика архивации**выберите политику архивации пользователей, которую вы хотите применить.
    
    > [!NOTE]
    > Для ** \<параметров\> автоматической** настройки применяются параметры установки сервера по умолчанию. Данные параметры автоматически применяются сервером.
  
6. Нажмите **Исполнить**.
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>Применение политики пользователей с помощью Windows PowerShell

Вы также можете применить политику пользователей с помощью командлета **Grant-Ксарчивингполици** Windows PowerShell.
  
Следующей командой пользователю Ken Myer назначается политика архивации RedmondArchivingPolicy на уровне пользователей.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

Эта команда назначает политику архивации на уровне пользователя RedmondArchivingPolicy всем пользователям, чьи учетные записи размещены в пуле регистраторов atl-cs-001.contoso.com. Дополнительные сведения о параметре фильтрации, используемом в этой команде, можно найти в документации по командлету [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) .
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

Следующей командой удаляется любая политика архивации на уровне пользователей, ранее назначенная пользователю Ken Myer. После того как политика на уровне пользователей удалена, Ken Myer будет автоматически управляться с помощью глобальной политики или политики его локального сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

Дополнительные сведения можно найти в документации по командлету [Grant-ксарчивингполици](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) .
  

