---
title: Удаление конфигурации архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Сводка: сведения о том, как удалить конфигурацию архивации в Skype для бизнеса Server.'
ms.openlocfilehash: 22da9464a4bb6b17c6d4b9aa63ad8990a9152c38
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992376"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Удаление конфигурации архивации в Skype для бизнеса Server

**Сводка:** Сведения о том, как удалить конфигурацию архивации в Skype для бизнеса Server.
  
Конфигурацию сайта или пула можно удалить, но удаление глобальной конфигурации невозможно. При удалении глобальной конфигурации она автоматически восстанавливает значения по умолчанию.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Удаление конфигурации архивирования с помощью панели управления

Чтобы удалить конфигурацию архивирования с помощью панели управления, выполните следующие действия:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.
    
4. В списке конфигураций архивирования нажмите конфигурацию сайта или пула, которую необходимо удалить, затем выберите **Изменить** и **Удалить**.
    
    > [!NOTE]
    > Также можно выбрать глобальную конфигурацию, но это следует делать только в том случае, если вы хотите сбросить глобальную конфигурацию к параметрам по умолчанию. 
  
5. Нажмите **Исполнить**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Удаление конфигурации архивирования с помощью Windows PowerShell

Вы также можете удалить конфигурацию архивации с помощью командлета **Remove-ксарчивингконфигуратион** .
  
Например, следующая команда удаляет параметры конфигурации архивирования, которые применены к сайту Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования.
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Следующая команда удаляет все параметры конфигурации архивирования, применяемые на уровне службы.
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Эта команда удаляет все параметры конфигурации архивирования, в которых отключена служба архивации Exchange.
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Для сброса глобальных параметров до значений по умолчанию можно также использовать командлет **Remove-CsArchivingConfiguration**. Например, предположим, что на глобальном уровне включена архивация сеанса обмена мгновенными сообщениями; следующая команда выполнит сброс значений до значения по умолчанию "Нет", что приведет к отключению архивации на глобальном уровне:
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксарчивингконфигуратион](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .
