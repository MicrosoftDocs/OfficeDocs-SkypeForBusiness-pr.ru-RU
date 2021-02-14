---
title: Настройка локального развертывания для трансляции собраний Skype
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
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: Сводка. Сведения о действиях, необходимых для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнеса Server.
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820709"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Настройка локального развертывания для трансляции собраний Skype
 
**Сводка:** Узнайте о действиях, которые необходимо выполнить для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнеса Server.
  
Трансляция собраний Skype — это веб-служба, которая входит в состав Office 365. If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic. Перед началом работы необходимо настроить среду для гибридной среды со Skype для бизнеса Online. Дополнительные сведения см. в сведениях о планировании гибридного подключения [между Skype](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) для бизнеса Server и Skype для бизнеса Online и развертывании гибридного подключения между Skype для бизнеса Server и Skype для бизнеса [Online.](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Настройка гибридной среды для трансляции собраний Skype

Для подготовки среды к трансляции собраний Skype необходимо сделать следующее:
  
- Настройка федерации с ресурсами Skype для бизнеса Online
    
- Настройка федераированных доменов SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Настройка федерации с ресурсами Skype для бизнеса Online

Чтобы включить федерацию с ресурсами Skype для бизнеса Online, необходимо настроить внешний доступ для федератного поставщика SIP. Для этого с помощью панели управления Skype для бизнеса Server выполните следующие действия.
  
1. Запустите панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.
    
2. Выберите **федеражных поставщиков SIP** и нажмите кнопку **"Новый".**
    
3. Настройте нового поставщика с помощью следующих параметров:
    
|||
|:-----|:-----|
|**В связи с этим поставщиком:** <br/> |выбрано  <br/> |
|**Имя поставщика:** <br/> |LyncOnlineResources  <br/> |
|**Служба пограничного доступа (полное доменное имя):** <br/> |sipfed.resources.lync.com  <br/> |
|**Уровень проверки по умолчанию:** <br/> |Разрешить пользователям взаимодействовать со всеми, кто использует этого поставщика.  <br/> |
   
Вы также можете включить федерацию с ресурсами Skype для бизнеса Online, выдав следующий cmdlet в оболочке управления Skype для бизнеса Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Настройка федераированных доменов SIP

Далее необходимо добавить федераированные домены SIP в список разрешенных доменов. Повторите эти действия для каждого из указанных доменов, создав 4 новых федераированных домена SIP. Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.
  
1. Запустите панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.
    
2. Выберите **федеражные домены SIP** и нажмите кнопку **"Новый".**
    
3. Для имени **домена (или FQDN):** введите домен, повторив эту процедуру для каждого из следующих доменов:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Вы также можете настроить внешний доступ для федераированных доменов SIP, задав следующие команды в оболочке управления Skype для бизнеса Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

После завершения этих действий по настройке можно приступить к использованию трансляции собраний Skype в развертывании. Дополнительные сведения о трансляции собраний Skype см. в руководстве администратора по трансляции собраний [Skype.](https://go.microsoft.com/fwlink/?LinkId=617071) [](https://go.microsoft.com/fwlink/?LinkId=617075)
  

