---
title: Настройка локального развертывания для трансляции собраний Skype
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Сводка: Сведения о действиях, которые необходимо выполнить для настройки Скайп собрания вещания для вашей локальной Скайп для гибридного развертывания Business Server.'
ms.openlocfilehash: 09b99cab45b8832be34a3219a222324d199c5195
ms.sourcegitcommit: 4967c9b1010a444475dcfbdb6dd3c058494449d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/16/2019
ms.locfileid: "30069471"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**Сводка:** Узнайте о действиях, которые необходимо выполнить для настройки Скайп собрания вещания для вашей локальной Скайп для гибридного развертывания Business Server.
  
Широковещательные собрания Скайп — это сетевая служба, входящий в состав Office 365. Если выполняется Скайп для Business Server локальных и требуется использовать Скайп собрания вещания в вашей среде, то необходимо необходимо выполнить действия по настройке в этом разделе. Прежде чем начать, среде необходимо настроить для гибридной среды с Скайп для бизнеса в Интернет. Дополнительные сведения см. в разделах [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) и [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Настройте гибридную среду для вещания Скайп собрания

Вам потребуется выполните следующие действия для подготовки среды к Скайп собрания вещания:
  
- Настройка федерации с Скайп для бизнеса в Интернет ресурсы
    
- Настройка федеративных доменов SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Настройка федерации с Скайп для бизнеса в Интернет ресурсы

Чтобы включить федерацию с Скайп для бизнеса в Интернет ресурсы, необходимо настроить внешний доступ для федеративного поставщика SIP. Для этого с помощью Скайп для панели управления Business Server выполните следующие действия:
  
1. Запустите Скайп для панели управления Business Server и слева выберите **Внешний доступ** .
    
2. Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.
    
3. Задайте для нового поставщика следующие параметры.
    
|||
|:-----|:-----|
|**Разрешить взаимодействие с этим поставщиком:** <br/> |выбрано  <br/> |
|**Имя поставщика:** <br/> |LyncOnlineResources  <br/> |
|**Служба пограничного доступа (полное доменное имя):** <br/> |sipfed.online.lync.com  <br/> |
|**Уровень проверки по умолчанию:** <br/> |Разрешить пользователям взаимодействовать со всеми, кто работает с тем же поставщиком.  <br/> |
   
Можно также включить федерацию с Скайп для бизнеса в Интернет ресурсы, выполнив следующий командлет в Скайп для консоли Business Server:
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Настройка федеративных доменов SIP

Затем необходимо добавить в список разрешенных доменов SIP федеративные домены. Повторите эти шаги для каждого из четырех указанных доменов, создав четыре новых федеративных домена SIP. Включить эти домены для региональных данных центры используется в Скайп для бизнеса в Интернет.
  
1. Запустите Скайп для панели управления Business Server и слева выберите **Внешний доступ** .
    
2. Выберите **Федеративные поставщики SIP** и нажмите кнопку **Создать**.
    
3. В поле **Имя домена (или полное доменное имя)** введите домен, повторив этот шаг для каждого из указанных ниже доменов.
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Можно также настроить внешнего доступа для федеративных доменов SIP, выполнив следующие командлеты в Скайп для консоли Business Server:
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

После выполнения этих действий можно начать с помощью Скайп собрания вещания в вашем развертывании. Дополнительные сведения о Скайп вещания собрания можно [возможности собраний Скайп, широковещательного?](https://go.microsoft.com/fwlink/?LinkId=617071) и [Руководстве вещания администратора Скайп собрания](https://go.microsoft.com/fwlink/?LinkId=617075).
  

