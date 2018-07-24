---
title: Удаление конфигурации архивации в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Сводка: Узнайте, как удалить конфигурации архивации в Скайп для Business Server.'
ms.openlocfilehash: f8cb64cf7523cfaec26006560b4f77f39d904ead
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018937"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>Удаление конфигурации архивации в Скайп для Business Server

**Сводка:** Узнайте, как удалить конфигурации архивации в Скайп для Business Server.
  
Конфигурацию сайта или пула можно удалить, но удаление глобальной конфигурации невозможно. При удалении глобальной конфигурации она автоматически восстанавливает значения по умолчанию.
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>Удаление конфигурации архивирования с помощью панели управления

Чтобы удалить конфигурацию архивирования с помощью панели управления, выполните следующие действия:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 
    
3. На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.
    
4. В списке конфигураций архивирования нажмите конфигурацию сайта или пула, которую необходимо удалить, затем выберите **Изменить** и **Удалить**.
    
    > [!NOTE]
    > Также можно выбрать глобальную конфигурацию, но это следует делать только в том случае, если вы хотите сбросить глобальную конфигурацию к параметрам по умолчанию. 
  
5. Нажмите **Исполнить**.
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>Удаление конфигурации архивирования с помощью Windows PowerShell

Также можно удалить конфигурации архивации с помощью командлета **Remove-CsArchivingConfiguration** .
  
Например, следующая команда удаляет параметры конфигурации архивирования, которые применены к сайту Redmond. При удалении политики, настроенной на уровне сайта, пользователи, которые раньше управлялись политикой сайта, автоматически станут управляться глобальной политикой архивирования.
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

Следующая команда удаляет все параметры конфигурации архивирования, применяемые на уровне службы.
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

Эта команда удаляет все параметры конфигурации архивирования, в которых отключена служба архивации Exchange.
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

Для сброса глобальных параметров до значений по умолчанию можно также использовать командлет **Remove-CsArchivingConfiguration**. Например, предположим, что на глобальном уровне включена архивация сеанса обмена мгновенными сообщениями; следующая команда выполнит сброс значений до значения по умолчанию "Нет", что приведет к отключению архивации на глобальном уровне:
  
```
Remove-CsArchivingConfiguration -Identity global
```

Для получения дополнительных сведений см раздел справки для командлета [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .