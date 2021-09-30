---
title: Настройка локального развертывания для Skype трансляции собраний
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: Сводка. Сведения о действиях, которые необходимо выполнить для настройки Skype для локального Skype для бизнеса Server гибридного развертывания.
ms.openlocfilehash: 99ba1733dc8c353dc17f9a4c9a51a9ed00410d27
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013713"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Настройка локального развертывания для Skype трансляции собраний
 
**Сводка:** Узнайте о действиях, которые необходимо выполнить для настройки Skype для локального Skype для бизнеса Server гибридного развертывания.
  
Skype Передача собраний — это онлайн-служба, которая является частью Office 365. Если вы работаете Skype для бизнеса Server локально и хотите использовать Skype в среде, необходимо следовать шагам по настройке в этом разделе. Перед началом работы необходимо настроить среду для гибридного Skype для бизнеса Online. Дополнительные сведения см. в сайте [Plan hybrid connectivity between Skype для бизнеса Server и Skype для бизнеса Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) и Deploy hybrid [connectivity between Skype для бизнеса Server и Skype для бизнеса Online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Настройка гибридной среды для Skype вещания собраний

Для подготовки среды к трансляции Skype собрания необходимо сделать следующее.
  
- Настройка федерации с помощью ресурсов Skype для бизнеса Online
    
- Настройка федераированных доменов SIP
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Настройка федерации с помощью ресурсов Skype для бизнеса Online

Чтобы включить федерацию с Skype для бизнеса интернет-ресурсами, необходимо настроить внешний доступ для поставщика SIP Federated. Для этого с помощью панели управления Skype для бизнеса Server выполните следующие действия:
  
1. Запустите панель Skype для бизнеса Server и выберите **внешний доступ** слева.
    
2. Выберите **поставщиков SIP Federated и** нажмите **кнопку New**.
    
3. Настройка нового поставщика с помощью следующих параметров:
    
   - **Включить связь с этим поставщиком:** Выбранный
   - **Имя поставщика:** LyncOnlineResources
   - **Служба Access Edge (FQDN): sipfed.resources.lync.com**
   - **Уровень проверки по умолчанию:** Разрешить пользователям общаться со всеми пользователями с помощью этого поставщика. 
   
Вы также можете включить федерацию с Skype для бизнеса интернет-ресурсами, заняв следующие команды в Skype для бизнеса Server управленческой оболочки:
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>Настройка федераированных доменов SIP

Далее необходимо добавить федераированные домены SIP в разрешенный список доменов. Повторите эти действия для каждого из перечисленных доменов, создав 4 новых федераированных домена SIP. Эти домены относятся к региональным центрам обработки данных, используемым в Skype для бизнеса Online.
  
1. Запустите панель Skype для бизнеса Server и выберите **внешний доступ** слева.
    
2. Выберите **SIP федераированные домены** и нажмите **кнопку New**.
    
3. Для имени **домена (или FQDN):** введите домен, повторив эту процедуру для каждого из следующих доменов:
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Вы также можете настроить внешний доступ для федератированных доменов SIP, заняв следующие команды в Skype для бизнеса Server Management Shell:
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

После завершения этих действий по настройке можно приступить к использованию Skype в развертывании. Дополнительные сведения о Skype трансляции собраний см. в Skype трансляции [собрания?](https://go.microsoft.com/fwlink/?LinkId=617071) и Skype руководство по администрированию [вещания](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)собрания.
