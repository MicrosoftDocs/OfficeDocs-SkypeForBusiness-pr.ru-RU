---
title: Настройка локального развертывания для трансляции собраний Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Сводка: Узнайте, какие действия необходимо выполнить, чтобы настроить трансляцию собраний Skype для локального гибридного развертывания Skype для бизнеса Server.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002809"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Сводка:** Узнайте, какие действия необходимо выполнить, чтобы настроить трансляцию собраний Skype для локального гибридного развертывания Skype для бизнеса Server.
  
Трансляция собрания Skype — это веб-служба, которая входит в состав Office 365. Если вы используете локальную версию Skype для бизнеса Server и хотите использовать трансляцию собраний Skype в своей среде, необходимо выполнить действия по настройке, описанные в этой статье. Прежде чем приступить к работе, необходимо настроить гибридную среду в Skype для бизнеса Online. Дополнительные сведения см. в разделах [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Настройка гибридной среды для трансляции собраний Skype

Для подготовки среды для трансляции собраний Skype вам потребуется выполнить следующие действия:
  
- Настройка Федерации с помощью ресурсов Skype для бизнеса Online
    
- Настройка федеративных доменов SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Настройка Федерации с помощью ресурсов Skype для бизнеса Online

Чтобы включить федерацию для ресурсов Skype для бизнеса Online, вам нужно настроить внешний доступ для поставщика федерации SIP. Чтобы сделать это с помощью панели управления Skype для бизнеса Server, выполните указанные ниже действия.
  
1. Откройте панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.
    
2. Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.
    
3. Задайте для нового поставщика следующие параметры.
    
|||
|:-----|:-----|
|**Включите связь с этим поставщиком:** <br/> |выбрано  <br/> |
|**Имя поставщика:** <br/> |LyncOnlineResources  <br/> |
|**Служба пограничного доступа (полное доменное имя):** <br/> |sipfed.online.lync.com  <br/> |
|**Уровень проверки по умолчанию:** <br/> |Разрешить пользователям взаимодействовать со всеми, кто работает с тем же поставщиком.  <br/> |
   
Вы также можете включить федерацию с ресурсами Skype для бизнеса Online, выполнив следующий командлет в командной консоли управления Skype для бизнеса Server:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Настройка федеративных доменов SIP

Затем необходимо добавить федеративные домены SIP в список разрешенных доменов. Повторите эти шаги для каждого из четырех указанных доменов, создав четыре новых федеративных домена SIP. Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.
  
1. Откройте панель управления Skype для бизнеса Server и выберите **внешний доступ** слева.
    
2. Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.
    
3. В поле **Имя домена (или полное доменное имя)** введите домен, повторив этот шаг для каждого из указанных ниже доменов.
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Вы также можете настроить внешний доступ для федеративных доменов SIP, выполнив следующие командлеты в командной консоли управления Skype для бизнеса Server:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

После выполнения этих шагов настройки вы сможете начать использование трансляции собраний Skype в развертывании. Дополнительные сведения о трансляции собраний Skype можно найти [в статье что такое трансляция собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617071) и [Руководство администратора трансляции собраний Skype](https://go.microsoft.com/fwlink/?LinkId=617075).
  

