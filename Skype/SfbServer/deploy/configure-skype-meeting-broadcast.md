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
description: Сводка. Сведения о действиях, которые необходимо выполнить для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнес-сервера.
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103695"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Настройка локального развертывания для трансляции собраний Skype
 
**Сводка:** Узнайте о действиях, которые необходимо выполнить для настройки трансляции собраний Skype для локального гибридного развертывания Skype для бизнес-сервера.
  
Skype Meeting Broadcast — это онлайн-служба, которая является частью Office 365. Если вы работаете на локальном сервере Skype для бизнеса и хотите использовать трансляцию собраний Skype в вашей среде, необходимо следовать шагам по настройке в этом разделе. Перед началом работы необходимо настроить среду для гибридного приложения Skype для бизнеса в Интернете. Дополнительные сведения см. в сайте Plan [hybrid connectivity between Skype for Business Server и Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) и Deploy hybrid [connectivity between Skype for Business Server and Skype for Business Online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Настройка гибридной среды для трансляции собраний Skype

Чтобы подготовить среду для трансляции собраний Skype, необходимо сделать следующее:
  
- Настройка федерации с помощью ресурсов Skype для бизнеса Online
    
- Настройка федераированных доменов SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Настройка федерации с помощью ресурсов Skype для бизнеса Online

Чтобы включить федерацию с помощью ресурсов Skype для бизнеса Online, необходимо настроить внешний доступ для поставщика SIP Federated. Для этого с помощью панели управления Skype для бизнес-серверов выполните следующие действия:
  
1. Запустите панель управления Skype для бизнес-серверов и выберите **внешний** доступ слева.
    
2. Выберите **поставщиков SIP Federated и** нажмите **кнопку New**.
    
3. Настройка нового поставщика с помощью следующих параметров:
    
|||
|:-----|:-----|
|**Включить связь с этим поставщиком:** <br/> |выбрано  <br/> |
|**Имя поставщика:** <br/> |LyncOnlineResources  <br/> |
|**Служба пограничного доступа (полное доменное имя):** <br/> |sipfed.resources.lync.com  <br/> |
|**Уровень проверки по умолчанию:** <br/> |Разрешить пользователям общаться со всеми пользователями с помощью этого поставщика.  <br/> |
   
Вы также можете включить федерацию с помощью ресурсов Skype для бизнеса Online, заняв следующие команды в оболочке управления серверами Skype для бизнеса:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Настройка федераированных доменов SIP

Далее необходимо добавить федераированные домены SIP в разрешенный список доменов. Повторите эти действия для каждого из перечисленных доменов, создав 4 новых федераированных домена SIP. Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.
  
1. Запустите панель управления Skype для бизнес-серверов и выберите **внешний** доступ слева.
    
2. Выберите **SIP федераированные домены** и нажмите **кнопку New**.
    
3. Для имени **домена (или FQDN):** введите домен, повторив эту процедуру для каждого из следующих доменов:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Вы также можете настроить внешний доступ для федераированных доменов SIP, заняв следующие команды в оболочке управления Skype для бизнес-серверов:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

После завершения этих действий по настройке можно приступить к использованию Skype Meeting Broadcast в развертывании. Дополнительные сведения о трансляции собраний Skype см. [](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)в руководстве по администрированию собраний [Skype.](https://go.microsoft.com/fwlink/?LinkId=617071)
