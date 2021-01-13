---
title: Удаление существующей коллекции параметров конфигурации магистрали SIP в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: Сводка. Узнайте, как удалить коллекцию параметров конфигурации магистрали с помощью панели управления Skype для бизнеса Server.
ms.openlocfilehash: a9065304860a257a7787c557e59da38d03abfef0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836979"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Удаление существующей коллекции параметров конфигурации магистрали SIP в Skype для бизнеса Server
 
**Сводка:** Узнайте, как удалить коллекцию параметров конфигурации магистрали с помощью панели управления Skype для бизнеса Server.
  
Параметры конфигурации магистрали SIP определяют отношения и возможности между сервером-посредником и шлюзом телефонной сети общего параметров (PSTN), у поставщика услуг IP-Public Branch eXchange (PBX) или пограничным контроллером сеансов (SBC). Эти настройки можно использовать, чтобы определить следующие параметры:
  
- Следует ли включать обход сервера-посредника на магистралях.
    
- Условия, при которых отправляются пакеты протокола RTCP.
    
- Требуется ли шифрование SRTP для каждой магистрали.
    
При установке Skype для бизнеса Server создается глобальная коллекция параметров конфигурации магистрали SIP. Эта глобальная коллекция параметров не подлежит удалению. Однако для сброса свойств глобальной коллекции до значений по умолчанию можно использовать панель управления Skype для бизнеса Server или [remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) Например, если задать свойство Enable3pccRefer как True, то при сбросе глобальной коллекции для свойства Enable3pccRefer возвращается значение по умолчанию False.
  
Администраторы могут также создавать пользовательские параметры конфигурации магистральной линии для области сайта или службы (отдельного шлюза ТСОП); эти пользовательские параметры могут быть удалены. При удалении данных пользовательских параметров следует учитывать следующее.
  
- Если удалить параметры области службы, магистральная линия SIP, управляемая этими параметрами, будет управляться параметрами, примененными к их сайту, если эти параметры существуют. Если параметры сайта не существуют, эти магистральные линии будут управляться глобальной коллекцией параметров конфигурации магистральной линии.
    
- Если удалить параметры области сайта, любые магистральные линии SIP, управляемые этими параметрами, будут управляться глобальной коллекцией параметров конфигурации магистральной линии.
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>Удаление параметров конфигурации магистрали с помощью панели управления Skype для бизнеса Server

1. In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.
    
2. На вкладке **Настройка линии связи** выберите коллекцию параметров конфигурации магистральной линии SIP, которую следует удалить, щелкните **Изменить**, затем нажмите **Удалить**. Чтобы удалить несколько коллекций одновременно, щелкните первую удаляемую коллекцию, затем, удерживая нажатой клавишу Ctrl, щелкайте любые другие коллекции, которые следует удалить.
    
3. Свойство **Состояние** для коллекции будет обновлено до **Незафиксированные**. Чтобы зафиксировать изменения и удалить коллекцию, щелкните **Сохранить**, а затем выберите **Сохранить все**.
    
4. В диалоговом окне **Несохраненные параметры настройки голосовой связи** нажмите кнопку **ОК**.
    
5. В **диалоговом окне панели** управления Skype для бизнеса Server нажмите кнопку **"ОК".**
    
6. Если решено не удалять коллекцию, щелкните **Сохранить**, затем **Отменить все несохраненные изменения**. Когда **появится диалоговое** окно панели управления Skype для бизнеса Server, нажмите кнопку **"ОК".**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>Удаление параметров конфигурации магистрали с помощью команды skype для бизнеса Server Management Shell

You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet. Вы можете запустить этот этот cmdlet либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса в skype для бизнеса Server Management Shell.
  
### <a name="to-remove-a-specified-collection-of-settings"></a>Удаление указанной коллекции параметров

- Следующая команда удаляет параметры конфигурации магистральной линии в сайте Redmond:
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>Удаление всех коллекций, применяемых к области сайта

- Эта команда удаляет все параметры конфигурации магистральной линии, примененные на уровне службы:
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>Удаление всех коллекций, для которых включен обход мультимедиа

- Следующая команда удаляет все параметры конфигурации, где был включен обход мультимедиа.
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

Дополнительные сведения см. в разделе справки по [cmdlet Remove-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps)
  

